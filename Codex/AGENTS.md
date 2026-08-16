# Codex multi-agent bootstrap

## Purpose

This repository uses a lightweight, role-focused multi-agent workflow for
Codex. Functional responsibilities are stable; configured models and reasoning
levels are replaceable defaults rather than agent identities.

The live custom-agent definitions are in `~/.codex/agents/`. The expected role
files are:

```text
~/.codex/
└── agents/
    ├── understand.toml
    ├── architect.toml
    ├── builder.toml
    ├── tester.toml
    ├── verifier.toml
    └── reviewer.toml
```

Do not add model providers or other strings under an `[agents]` table. In the
current supported schema, each role is a standalone TOML file with top-level
agent fields. Keep `model_provider` in the main Codex configuration if it is
needed there; do not copy it into an agent registry.

## Functional roles

- **Understand** investigates requirements, repository structure, dependencies,
  existing implementation, constraints, ambiguity, and missing context before
  architecture begins.
- **Architect** produces the implementation approach and decides sequencing,
  affected areas, boundaries, risks, and verification needs without doing
  unnecessary implementation.
- **Builder** implements the approved work and stays focused on implementation.
  Its report is a handoff, not acceptance or review.
- **Tester** runs relevant tests, creates or extends focused tests when
  appropriate, actively looks for breakage and edge cases, and answers:
  **Does the implementation work?**
- **Verifier** independently compares meaningful Builder work with every
  original requirement and answers: **Did we build what was requested,
  completely and correctly?**
- **Reviewer** performs a fresh final independent review of the original
  requirements, finished diff, repository context, and test, verification, and
  parent-inspection evidence.

## Orchestration workflow

For meaningful implementation, use:

```text
Understand -> Architect -> Builder -> Tester -> Verifier -> parent verification -> Reviewer
```

Meaningful Builder work must not skip Verifier. Builder success is never enough
to declare completion. Before starting the final Reviewer, the parent must
inspect the actual diff and available test and verification evidence. The final
Reviewer must be a fresh, independent, read-only instance and must not rely on
the Builder's reasoning or self-assessment.

Use proportional orchestration for trivial work such as a typo or harmless
documentation correction. Such work does not require six-agent ceremony, but it
still needs risk-appropriate parent inspection. Do not classify a change as
trivial merely to avoid verification.

When Reviewer finds a problem, route the finding to the role appropriate for
diagnosis or design, then run the remediation through:

```text
Reviewer finding -> Builder -> Tester -> Verifier -> parent verification -> NEW Reviewer
```

The Reviewer that raised a finding must not approve its own remediation. Always
use a new Reviewer instance after the fix and validation chain.

## Delegation and parallelism

Delegate by role, never by model name. Every handoff must include:

- the functional role, objective, and definition of done;
- relevant requirements, files or components, constraints, and prior findings;
- decisions already made and any boundaries that must not change;
- whether edits are permitted and the exact ownership scope;
- expected evidence and return format; and
- an instruction to stop and report if essential context is missing.

Share only the context needed for the assigned work. Allow parallel subagents
only for genuinely independent workstreams, such as separate frontend, test,
documentation, or configuration investigation. Do not parallelize tightly
coupled implementation. The parent must synthesize all parallel findings before
architecture or implementation decisions continue.

## Capability escalation and failure handling

Every role must escalate when it is blocked, confidence is low, the task is
materially more complex than expected, architectural judgment is required,
repeated attempts are not making progress, or assigned capability is
insufficient. Do not repeat the same failing approach at the same capability:

```text
efficient capability -> stronger general capability -> highest-capability reasoning
```

Keep the workflow expressed in roles. Capability escalation may select a
different model, but the replacement must act as the same functional role under
the same instructions and permissions.

Fail closed when a required role cannot spawn or its configured model is
unavailable. Report the failure explicitly. Use only an explicitly permitted
general-purpose fallback acting as the same role. A fallback for Verifier or
Reviewer must be a fresh, independent, read-only instance. If no permitted
fallback is available, stop; never claim the missing test, verification, or
review step occurred.

## Current model defaults

These defaults are implementation details and may be replaced without changing
the workflow:

| Role | Preferred model | Reasoning | Sandbox |
| --- | --- | --- | --- |
| Understand | `gpt-5.6-terra` | `high` | `read-only` |
| Architect | `gpt-5.6-sol` | `xhigh` | `read-only` |
| Builder | `gpt-5.6-terra` | `high` | inherit |
| Tester | `gpt-5.6-terra` | `high` | inherit |
| Verifier | `gpt-5.6-sol` | `high` | `read-only` |
| Reviewer | `gpt-5.6-sol` | `xhigh` | `read-only` |

Model availability or substitution must be reported honestly. Do not claim a
preferred model was used unless the current environment exposes evidence for it.

## Configuration validation

After creating or changing the agent configuration:

1. Parse the main configuration and every role TOML file.
2. Confirm each role defines `name`, `description`, `model`,
   `model_reasoning_effort`, and `developer_instructions` using fields supported
   by the installed Codex version.
3. Confirm read-only roles declare `sandbox_mode = "read-only"` and writable
   roles inherit the parent sandbox rather than weakening it.
4. Confirm Codex starts without configuration errors and all six roles load.
5. Run harmless controlled delegation scenarios for the proportional trivial
   path, normal workflow, capability escalation, and Reviewer remediation loop.
6. Record actual spawn, model-selection, test, verification, and review evidence.
   Mark anything the environment cannot expose as `NOT VERIFIABLE`; never infer a
   pass merely from file presence.
7. Confirm no obsolete model-branded definitions or routing references remain
   unintentionally and that useful global and repository safeguards were kept.

Do not modify application code during configuration-only validation scenarios.
