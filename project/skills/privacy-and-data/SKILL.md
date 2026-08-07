---
name: privacy-and-data
description: Set safe defaults for data, privacy, consent, credentials, and diagnostics. Use when a project collects, displays, stores, transmits, logs, enriches, validates, or otherwise handles user, customer, operational, or secret data.
---

# Privacy and data

## Decide before collecting

Identify what data a feature needs, why it is needed, where it travels, who can access it, and how long it persists. Collect and retain the minimum necessary. Do not add tracking, analytics, cookies, local storage, or identifiers without explicit scope and appropriate consent.

Keep consent separate from unrelated actions. Make user-facing data handling understandable and do not imply validation, identity confirmation, or security guarantees that the system does not provide.

## Keep secrets and diagnostics safe

Keep credentials, tokens, and private configuration outside client-visible source and version control. Use an appropriate server-side or platform-managed boundary for privileged work.

Do not log personal, sensitive, or secret values. Make diagnostics generic by default and expose more detail only through an approved, access-controlled path. Treat URLs, error reports, screenshots, and test fixtures as potential data-bearing artifacts.

## Check the boundary

Review the actual request paths, configuration, logs, and generated artifacts before handoff. State the remaining privacy or security limitations plainly.
