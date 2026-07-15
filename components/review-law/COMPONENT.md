# Component: review-law

- **Version:** 1.0.0
- **Requires:** dev-lanes
- **Installs to:** `REVIEW.md` at the target repo root, `.claude/agents/reviewer.md`, `.github/pull_request_template.md`
- **Placeholders:** `{{PROJECT_NAME}}`

## What it installs

A review constitution every PR review reads, a reviewer charter, and a PR template. The pattern: reviews are law-driven, not vibe-driven; severity is calibrated in writing; volume is capped so reviews converge instead of nitpicking forever.

| Template | Target |
|---|---|
| `templates/REVIEW.md` | `REVIEW.md` |
| `templates/agents/reviewer.md` | `.claude/agents/reviewer.md` |
| `templates/pull_request_template.md` | `.github/pull_request_template.md` |

## Install notes

- REVIEW.md ships with structure and calibration language but an empty "standing law" list; the target repo fills it as its own decisions accumulate. Amend REVIEW.md via PR like any law.
- The flow this enables: a lane marks its PR ready, the gateway (or a reviewer lane) reviews against REVIEW.md before the maintainer looks. The maintainer reviews last and merges.
- For local-only repos: keep REVIEW.md and the charter; "PR review" becomes a review of the branch diff recorded in the journal.

## Changelog

- 1.0.0 (2026-07-14): initial release.
