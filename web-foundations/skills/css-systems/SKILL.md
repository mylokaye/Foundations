---
name: css-systems
description: Build and review maintainable, responsive CSS. Use when creating or changing visual systems, layout, component styling, responsive behavior, interaction states, typography, color, spacing, or motion.
---

# CSS systems

## Establish a small visual system

Define shared values as custom properties for color, type, spacing, radius, elevation, borders, and motion. Name tokens by their role rather than by a one-off component or raw value. Keep global foundations small and let components consume the shared tokens.

Choose class names that describe stable component and state roles. Keep selectors shallow, specific enough to be intentional, and independent of incidental DOM nesting. Avoid `!important`, repeated magic numbers, and overrides that depend on source-order accidents; refactor the owning rule or shared token instead.

## Compose layout deliberately

Use normal document flow, flexbox, grid, and intrinsic sizing before absolute positioning. Set sensible width constraints, allow content to grow, and test with real long text and small viewports. Treat responsive design as a continuous range: add a breakpoint only when the layout needs a structural change.

Separate layout, appearance, and state where that makes changes clearer. Give hover, focus, disabled, invalid, loading, and selected states deliberate visual treatment. Keep focus visible and respect reduced-motion preferences for nonessential motion.

## Keep styling easy to change

Centralize rules the product treats as shared. Make a component's variants explicit instead of cloning a base rule and drifting it over time. Remove dead selectors and obsolete overrides when changing an area, but do not perform unrelated rewrites.

Check the computed result at representative viewport sizes and interaction states. Verify overflow, contrast, focus indicators, content wrapping, and motion behavior in the actual browser. Use the project's broader design, accessibility, and verification practices for final evidence.
