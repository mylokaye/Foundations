---
name: project-documentation
description: Establish and maintain accurate project documentation. Use when starting, changing, reviewing, or handing off a software or product project; when setup, architecture, data handling, testing, deployment, or limitations need to be documented.
---

# Project documentation

## Establish the baseline

Read the existing documentation and setup before making material changes. Identify the project's purpose, users, architecture, local setup, data boundaries, validation approach, deployment path, and known limitations. Do not claim any of these are true without evidence.

Keep the main README useful to someone opening the project for the first time. Put durable technical decisions in the closest appropriate documentation rather than leaving them only in a conversation or commit message.

Maintain a brief root `CHANGELOG.md` for material project changes. Add a dated entry when behaviour, public interfaces, configuration, privacy, accessibility, release status, or a migration changes. State what changed and any action a user or maintainer must take. Do not add entries for purely internal, non-behavioural cleanup unless the project explicitly requires exhaustive release notes.

## Maintain truthfulness

Update documentation when behaviour, interfaces, configuration, data handling, validation, testing, or release procedures change. Remove stale instructions rather than adding a contradictory note beside them.

Distinguish clearly between intended behaviour, local behaviour, tested behaviour, and deployed behaviour. Record limitations and deferred work without presenting them as complete.

## Handoff

Summarize the purpose of the change, files changed, behavioural impact, and verification performed. State what was not tested and why.
