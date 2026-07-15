# CLAUDE.md: {{PROJECT_NAME}}

{{PROJECT_DESCRIPTION}} The repo, not conversation history, is the project's memory; this file is its constitution.

## Session start

1. Read `docs/STATE.md` (one screen: orientation, next actions, blockers).
2. Read further only as the task demands: the `docs/decisions.md` index and `docs/open-questions.md` before proposing anything strategic; the active spec before building.

## Repo map

| Path | Role | Mutation rule |
|---|---|---|
| `docs/STATE.md` | Handoff note, one screen | Overwrite freely; current whenever work lands on the trunk |
| `docs/journal.md` | Session log | Append-only |
| `docs/decisions.md` | Rulings D1, D2, ... (index at top) | Append-only; supersede via a new D; sole edit on old entries: a status stamp |
| `docs/open-questions.md` | Question queue | Check off with a pointer |
<!-- installer: add rows here for the paths other installed components create (skills, REVIEW.md, rules/), and for the project's own source directories -->

## Invariants

- **Git:** {{GIT_POSTURE}}
- **Register:** roles (maintainer, contributors), never named individuals; no personal specifics in committed docs.
- **Decisions are settled** unless the maintainer reopens them; never build against an open ⚖ question.
<!-- installer: keep this list short; a rule earns entry only after the same mistake happens twice -->

## Session end

When a session materially changes thinking, files, or direction: refresh `docs/STATE.md`, append a `docs/journal.md` entry, route durables to their homes (decisions, open questions, spec).

## Maintaining this file

Budget {{WORD_BUDGET}} words. A rule earns entry only after the same mistake happens twice; procedure lives in `.claude/skills/`, rationale in `docs/decisions.md`. Prune by the deletion test: would removing this line cause mistakes? Prefer a mechanized gate over new prose.
