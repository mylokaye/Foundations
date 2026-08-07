# Project Foundations authoring rules

Each first-level package directory is a plugin root. Keep its portable Agent Plugins manifest at `plugin.json` and Codex adapter metadata at `.codex-plugin/plugin.json`.

Each portable skill belongs in an immediate `skills/<skill-name>/` directory and requires a `SKILL.md` file with only `name` and `description` YAML frontmatter. Keep instructions concise, actionable, technology-neutral, and free from project-specific secrets or infrastructure assumptions.

Add scripts, references, assets, MCP servers, and client extensions only when a concrete reusable workflow needs them. Never introduce a dependency from one plugin to another; duplicate the minimum binding guidance needed for an independently useful specialist plugin.

Update this repository README whenever its package inventory or release policy changes. Record material package changes in the affected package's `CHANGELOG.md`. Keep portable and Codex manifest versions aligned. Validate the Agent Plugin manifest and every modified skill before handoff. Do not describe a package as installed, tested, or published without direct evidence.
