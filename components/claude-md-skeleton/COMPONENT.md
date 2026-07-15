# Component: claude-md-skeleton

- **Version:** 1.0.0
- **Requires:** memory-core
- **Installs to:** `CLAUDE.md` at the target repo root
- **Placeholders:** `{{PROJECT_NAME}}`, `{{PROJECT_DESCRIPTION}}`, `{{WORD_BUDGET}}`, `{{GIT_POSTURE}}`

## What it installs

One file: a budgeted constitution skeleton (P03). The installing agent fills placeholders from interview answers, deletes the sections marked for profiles the repo did not take, and deletes every `<!-- installer: ... -->` comment before finishing.

## Placeholder guidance

- `{{WORD_BUDGET}}`: default 400 for minimal/docs-research repos, 900 for full-dev. The budget is a ceiling, not a target; a new repo's constitution should start far under it.
- `{{GIT_POSTURE}}`: one sentence from the interview, e.g. "Branch per work item; every change to the trunk goes through a PR; never push unasked" or "No commit without in-the-moment maintainer approval".

## Install notes

- The skeleton deliberately starts small. Rules earn entry after the same mistake happens twice (P03); do not pre-populate invariants the project has not needed.
- If ci-gates is installed, wire the budget number there too (one home for the number is the CI config; CLAUDE.md may state that the budget exists and where it is enforced).

## Changelog

- 1.0.0 (2026-07-14): initial release.
