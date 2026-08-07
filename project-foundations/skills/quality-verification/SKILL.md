---
name: quality-verification
description: Plan and perform proportionate verification for project changes. Use when diagnosing, implementing, reviewing, testing, building, deploying, publishing, or reporting whether software, content, configuration, or an integration works.
---

# Quality verification

## Verify the claim that matters

Identify what changed, what could regress, and the strongest practical evidence for the requested outcome. Reproduce suspected problems before treating them as facts. Prefer narrow checks while implementing, then run the relevant regression or end-to-end checks before a full review or release.

Match evidence to the environment. A static check does not prove runtime behaviour; a local build does not prove a deployed release; a simulator does not prove physical-device behaviour. Inspect the actual rendered, executed, or published result when that is the requested outcome.

## Keep verification proportionate

Check errors, edge cases, accessibility-relevant interactions, and the changed user flow. Avoid tests that merely duplicate implementation details. Do not report a result as verified when a prerequisite, test, or release step failed.

## Report evidence

State the commands, tests, environments, and user-visible flows checked. Distinguish pass, failure, untested areas, and inferred conclusions. Include enough evidence for another person to understand the confidence boundary.
