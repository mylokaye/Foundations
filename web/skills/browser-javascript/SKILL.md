---
name: browser-javascript
description: Build and review reliable browser-side JavaScript. Use when creating or changing DOM behavior, forms, validation, client state, asynchronous requests, storage, browser APIs, or user-visible interaction flows.
---

# Browser JavaScript

## Model state before wiring events

Identify the smallest state needed for the user-visible behavior, who owns each value, and which events can change it. Keep state transitions explicit and update the DOM from current state rather than accumulating scattered, conflicting mutations. Group related behavior behind small functions with clear inputs and outputs.

Use stable `data-*` hooks for behavior. Query the DOM defensively, scope listeners to the feature that owns them, and avoid reliance on presentation-only markup or exact displayed text. Preserve native browser behavior where it already solves the task.

## Make asynchronous work safe

For requests driven by changing input, define loading, success, empty, timeout, failure, and cancellation behavior before implementation. Cancel superseded work where possible, use timeouts, and guard against stale responses with a request identifier or input snapshot. Never let an older response overwrite the result of a newer user action.

Validate untrusted values at the boundary and render them safely. Keep credentials and privileged logic off the client; call a server-side route when a secret, protected integration, or trusted decision is required. Store only the minimum browser data needed, and make persistence and reset behavior deliberate.

## Make interactions recoverable

Provide clear busy, error, and retry states without losing user input. Keep validation messages synchronized with actual values and browser constraints. Ensure focus moves intentionally after meaningful transitions and that keyboard users can complete the same flow.

Verify the changed flow in a real browser, including a failure or stale-response path where asynchronous work is involved. Run the project's relevant static, unit, and end-to-end checks, and report the environment and behavior actually verified.
