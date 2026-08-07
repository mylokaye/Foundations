# Foundations Agent Plugin Library

Portable, opinionated Agent Plugins for consistent project delivery and future plugin authoring.

[Repository](https://github.com/mylokaye/project-foundations) · [MIT License](LICENSE)

## Packages

| Package | Purpose | Source |
| --- | --- | --- |
| [`foundations.project`](project/) | Technology-neutral practices for documentation, design, accessibility, privacy, verification, and scoped delivery. | [GitHub](https://github.com/mylokaye/project-foundations/tree/main/project) |
| [`foundations.authoring`](authoring/) | A focused workflow for creating, validating, and releasing portable Agent Plugins. | [GitHub](https://github.com/mylokaye/project-foundations/tree/main/authoring) |
| [`foundations.web`](web/) | Framework-neutral HTML, CSS, and browser JavaScript practices for maintainable web interfaces. | [GitHub](https://github.com/mylokaye/project-foundations/tree/main/web) |

The packages intentionally keep universal practices separate from platform-specific implementation. They do not prescribe a frontend framework, native UI toolkit, cloud provider, or deployment system.

## Release status

| Check | `foundations.project` | `foundations.authoring` | `foundations.web` |
| --- | --- | --- | --- |
| Package structure validated | Complete | Complete | Complete |
| License | MIT | MIT | MIT |
| Fresh-client installation smoke test | Pending | Pending | Pending |
| Published release | Pending | Pending | Pending |

These packages are available from this repository, but neither has yet been installed in a fresh supported client or published to a plugin catalog. Do not treat the GitHub source URL as a compatibility or publication claim until the pending smoke test has been completed.

## Use from source

Clone the repository, then select the individual package directory in the supported client's Git/source installation flow:

```sh
git clone https://github.com/mylokaye/project-foundations.git
```

Install one package at a time from `project/`, `authoring/`, or `web/`. The client-specific installation command will be added after it has been verified in a fresh client context.

## Included skills

### `foundations.project`

- `project-documentation` — establish and maintain useful project documentation and brief changelogs.
- `design-principles` — apply clear, adaptable, consistent interface design.
- `accessibility` — build and verify inclusive experiences.
- `privacy-and-data` — protect data, secrets, consent, and diagnostics.
- `quality-verification` — choose proportionate evidence for changes.
- `change-delivery` — make scoped changes and report their state honestly.

### `foundations.authoring`

- `author-agent-plugins` — create and maintain portable Agent Plugins, including package boundaries, portable and Codex manifests, validation, and release readiness.

### `foundations.web`

- `semantic-html` — build accessible, resilient document and form structure with native HTML first, using comments only for non-obvious decisions.
- `css-systems` — create maintainable responsive CSS through tokens, composition, and predictable states.
- `browser-javascript` — organize browser-side behavior with explicit state, safe asynchronous work, and proportionate verification.

## Scope and package boundaries

Use `foundations.project` as the shared, technology-neutral base. Use `foundations.web` for browser-specific work and `foundations.authoring` for plugin packaging. Create separate plugins for other platform or domain conventions, such as iOS development or a deployment environment. A specialist plugin must remain useful on its own because the portable Agent Plugins format does not define cross-plugin dependencies.

## Versioning and contribution

- Keep portable and Codex manifest versions aligned for each package.
- Use Semantic Versioning: patch for compatible corrections, minor for compatible skills or capabilities, and major for breaking changes.
- Add material changes to the package's `CHANGELOG.md` under `Unreleased`; move them into a dated release section when its version is published.
- Before release, validate the portable manifest, Codex manifest, and every changed skill.
- Before claiming compatibility, install the package in a fresh client context and exercise a representative skill.
- State whether a package is local, installed, tested, published, or unverified in every handoff.

## License

Copyright © 2026 Mylo Kaye. This repository and both packages are released under the [MIT License](LICENSE).
