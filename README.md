# Agent Plugin Library

This repository contains portable, opinionated Agent Plugins for consistent project delivery and future plugin authoring.

The packages keep universal practices separate from platform-specific implementation plugins. They do not prescribe a frontend framework, native UI toolkit, cloud provider, or release system.

## Packages

### `project-foundations`

The reusable, technology-neutral foundation for project work. It contains:

- `plugin.json` — portable Agent Plugins v1 manifest.
- `.codex-plugin/plugin.json` — Codex-specific presentation metadata.
- `skills/` — independently discoverable Agent Skills.

## Included skills

- `project-documentation` — establish and maintain useful project documentation and brief changelogs.
- `design-principles` — apply clear, adaptable, consistent interface design.
- `accessibility` — build and verify inclusive experiences.
- `privacy-and-data` — protect data, secrets, consent, and diagnostics.
- `quality-verification` — choose proportionate evidence for changes.
- `change-delivery` — make scoped changes and report their state honestly.

### `agent-plugin-authoring`

The specialist package for creating and maintaining portable Agent Plugins. Its `author-agent-plugins` skill covers package boundaries, portable and Codex manifests, skill structure, validation, and release readiness.

## Scope

Use `project-foundations` as a shared foundation. Create separate plugins for platform or domain conventions, such as web development, iOS development, or a deployment environment. A specialist plugin must remain useful on its own because the portable Agent Plugins format does not define cross-plugin dependencies.

## Ownership and licensing

The package manifests identify `Project Foundations contributors` as the current owner. This repository and both packages are released under the [MIT License](LICENSE).

## Versioning and release

- Keep portable and Codex manifest versions aligned for each package.
- Use Semantic Versioning: patch for compatible corrections, minor for compatible skills or capabilities, and major for breaking changes.
- Add material changes to the package's `CHANGELOG.md` under `Unreleased`; move them into a dated release section when its version is published.
- Before release, validate the portable manifest, Codex manifest, and every changed skill.
- Before claiming compatibility, install the package in a fresh client context and exercise a representative skill. This smoke test remains pending for both packages.
- State whether a package is local, installed, tested, published, or unverified in every handoff.

## Development

Keep each skill in an immediate `skills/<skill-name>/SKILL.md` directory. Do not add MCP configuration, assets, scripts, or client extensions unless a concrete skill needs them. Validate the package and every changed skill before release.
