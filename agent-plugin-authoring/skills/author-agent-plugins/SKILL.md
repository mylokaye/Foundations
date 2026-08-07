---
name: author-agent-plugins
description: Create, restructure, validate, and prepare portable Agent Plugins for release. Use when packaging reusable Agent Skills or MCP servers, creating plugin manifests, adding Codex-specific metadata, reviewing plugin layout, or preparing an Agent Plugin installation and compatibility check.
---

# Author Agent Plugins

## Define the smallest useful package

Identify the reusable workflow, the users who need it, and the concrete prompts that should trigger it. Create a separate plugin when its domain, release cycle, or technical assumptions differ materially from existing packages.

Use skills for instruction-driven workflows. Add an MCP server only when a reusable tool integration is required. Do not add empty component directories, bundled dependencies, client extensions, or client-specific behaviour merely as scaffolding.

## Build the portable core

Place one `plugin.json` at the plugin root. Use the canonical Agent Plugins schema identifier, a lowercase valid name, and only portable manifest fields. Keep all package-supplied paths inside the plugin root.

Place each skill in an immediate `skills/<skill-name>/SKILL.md` directory. Give every skill precise frontmatter that states its purpose and trigger conditions. Keep instructions concise, imperative, and self-contained. Place optional scripts, references, and assets inside the owning skill only when they directly support repeated work.

Place optional MCP configuration only in root `mcp.json`; never put server configuration or secrets in the portable manifest. Use a root-relative path for a bundled executable and never embed credentials in package files or remote-server headers.

## Add a client adapter deliberately

Keep Codex-specific metadata in `.codex-plugin/plugin.json`. Match its name and version to the portable manifest. Keep the portable `plugin.json` authoritative for portable components; do not use a client adapter to replace or contradict the portable core.

Add other client extensions only under their stable reverse-domain namespace and only when that client documents the behaviour. Ensure the package remains useful when another client ignores those extensions.

## Release and validate

Maintain a package `CHANGELOG.md` with an `Unreleased` section. Keep versions in both manifests aligned and use Semantic Versioning. Validate the portable manifest, the client manifest, and every changed skill before release.

Install the package in a fresh supported client context and exercise representative skills before claiming it is compatible or ready to share. Report structural validation, installation, functional testing, and publication as separate facts.
