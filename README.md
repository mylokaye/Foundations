# Project Foundations Agent Plugin Library

Portable, opinionated Agent Plugins for consistent project delivery and future plugin authoring.

[Repository](https://github.com/mylokaye/project-foundations) · [MIT License](LICENSE)

## Packages

| Package | Purpose | Source |
| --- | --- | --- |
| [`project-foundations`](project-foundations/) | Technology-neutral practices for documentation, design, accessibility, privacy, verification, and scoped delivery. | [GitHub](https://github.com/mylokaye/project-foundations/tree/main/project-foundations) |
| [`agent-plugin-authoring`](agent-plugin-authoring/) | A focused workflow for creating, validating, and releasing portable Agent Plugins. | [GitHub](https://github.com/mylokaye/project-foundations/tree/main/agent-plugin-authoring) |

The packages intentionally keep universal practices separate from platform-specific implementation. They do not prescribe a frontend framework, native UI toolkit, cloud provider, or deployment system.

## Release status

| Check | `project-foundations` | `agent-plugin-authoring` |
| --- | --- | --- |
| Package structure validated | Complete | Complete |
| License | MIT | MIT |
| Fresh-client installation smoke test | Pending | Pending |
| Published release | Pending | Pending |

These packages are available from this repository, but neither has yet been installed in a fresh supported client or published to a plugin catalog. Do not treat the GitHub source URL as a compatibility or publication claim until the pending smoke test has been completed.

## Use from source

Clone the repository, then select the individual package directory in the supported client's Git/source installation flow:

```sh
git clone https://github.com/mylokaye/project-foundations.git
```

Install one package at a time from either `project-foundations/` or `agent-plugin-authoring/`. The client-specific installation command will be added after it has been verified in a fresh client context.

## Included skills

### `project-foundations`

- `project-documentation` — establish and maintain useful project documentation and brief changelogs.
- `design-principles` — apply clear, adaptable, consistent interface design.
- `accessibility` — build and verify inclusive experiences.
- `privacy-and-data` — protect data, secrets, consent, and diagnostics.
- `quality-verification` — choose proportionate evidence for changes.
- `change-delivery` — make scoped changes and report their state honestly.

### `agent-plugin-authoring`

- `author-agent-plugins` — create and maintain portable Agent Plugins, including package boundaries, portable and Codex manifests, validation, and release readiness.

## Scope and package boundaries

Use `project-foundations` as the shared foundation. Create separate plugins for platform or domain conventions, such as web development, iOS development, or a deployment environment. A specialist plugin must remain useful on its own because the portable Agent Plugins format does not define cross-plugin dependencies.

## Versioning and contribution

- Keep portable and Codex manifest versions aligned for each package.
- Use Semantic Versioning: patch for compatible corrections, minor for compatible skills or capabilities, and major for breaking changes.
- Add material changes to the package's `CHANGELOG.md` under `Unreleased`; move them into a dated release section when its version is published.
- Before release, validate the portable manifest, Codex manifest, and every changed skill.
- Before claiming compatibility, install the package in a fresh client context and exercise a representative skill.
- State whether a package is local, installed, tested, published, or unverified in every handoff.

## License

Copyright © 2026 Mylo Kaye. This repository and both packages are released under the [MIT License](LICENSE).
