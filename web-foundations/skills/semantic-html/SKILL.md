---
name: semantic-html
description: Build and review semantic, accessible HTML. Use when creating or changing page structure, content hierarchy, forms, navigation, dialogs, controls, metadata, or any browser-rendered document.
---

# Semantic HTML

## Start with the document model

Describe the content, landmarks, headings, relationships, and user tasks before choosing elements. Use one meaningful `h1` for the page topic and keep heading levels in a logical outline. Use landmarks such as `header`, `nav`, `main`, `aside`, and `footer` only when they represent those regions.

Prefer native elements that express the intended meaning and behavior: buttons for actions, links for navigation, lists for collections, tables for two-dimensional data, and form controls for input. Do not replace native controls with generic elements unless the required behavior and accessibility are deliberately implemented.

## Build forms for people and browsers

Associate every input with a visible label. Use `fieldset` and `legend` for related choices, suitable input types and `autocomplete` tokens, and programmatic error messages that explain how to recover. Keep validation state, required status, and disabled state truthful in both markup and behavior.

Use ARIA only to supply semantics HTML cannot express. Do not add redundant roles or ARIA attributes that contradict native behavior. When custom interaction is unavoidable, provide keyboard behavior, focus management, names, states, and values equivalent to the native pattern.

## Keep markup durable

Keep structure independent of visual styling and JavaScript hooks. Use classes for styling and `data-*` attributes for behavior; avoid selecting elements in scripts by text content or presentation-only structure. Keep repeated content and controls consistently shaped so that styles and behavior have stable targets.

Use comments only to explain a non-obvious structural decision, browser limitation, or accessibility workaround. Do not use comments to narrate obvious markup or compensate for unclear structure; improve the markup instead.

Set document language, an informative title, responsive viewport metadata, and a meaningful page structure. Supply useful alternative text for informative images and omit or empty-mark decorative images according to their role.

## Check the rendered result

Inspect the rendered page, not only the source. Exercise keyboard navigation and the changed form or interaction flow. Confirm that headings, labels, errors, and focus order still communicate the intended task. Use the project's broader accessibility and verification practices for full review evidence.
