---
name: javascript-static-review
description: Review JavaScript, TypeScript, React, Next.js, and browser extension changes. Use when building, editing, debugging, or reviewing JS/TS frontend, Node, React component, Next.js app/router, or browser extension files for runtime bugs, type/lint/test/build failures, security issues, unsafe DOM access, async races, invalid React state usage, broken imports, unreachable code, and browser compatibility problems.
---

# JavaScript Static Review

Perform a focused static review of JavaScript-family changes. Prioritize defects that can cause runtime failures, incorrect behavior, security exposure, or material maintainability risk. Ignore purely stylistic issues unless they materially affect maintainability.

## Verify proportionately

Inspect `package.json` to identify available scripts and the package manager convention. Run applicable checks in this order: lint, typecheck, tests, then build. Use the repository's package manager and skip a check only when its script is absent or clearly inapplicable.

Read enough surrounding code to understand call sites and data flow. Keep any requested fixes scoped to validated findings and nearby supporting tests.

## Review for concrete failures

Check for runtime errors, null or undefined access, broken imports or exports, invalid path aliases, unreachable code, swallowed errors, and server/client boundary violations in Next.js.

Check asynchronous work for stale closures, missing cancellation or cleanup, out-of-order updates, and incomplete loading, timeout, error, or retry behavior.

For React, check hook rules, effect dependencies, derived state, and mutation of state. For browser and extension code, check unsafe DOM access, unsafe HTML insertion, selector assumptions, API guards, `postMessage` validation, extension-context compatibility, and browser support.

Check security boundaries for injection, XSS, token leakage, unsafe redirects, SSRF-prone fetches, prototype pollution, insecure storage, and missing authorization.

## Report findings clearly

Order findings by severity: Critical, High, Medium, then Low. For each finding, provide the severity, exact file and line reference where available, what can fail and why, and the smallest direct fix.

If no issues are found, say so clearly, list checks run or skipped, and identify residual test gaps or assumptions.
