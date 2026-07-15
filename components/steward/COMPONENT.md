# Component: steward

- **Version:** 1.0.0
- **Requires:** memory-core
- **Installs to:** `.claude/skills/process-steward/SKILL.md`
- **Placeholders:** none

## What it installs

A recurring process audit: the mechanism that keeps the installed process honest over time. Checks the memory core for drift (stale STATE, index gaps, unstamped supersessions), the instruction layer for budget rot, and the skills for skill-vs-practice divergence. Output is one proposal-shaped change set for the maintainer, never silent fixes to law.

## Install notes

- Run cadence is the maintainer's call: weekly scheduled run, or on demand after heavy process churn. The skill works either way.
- On repos with PRs, the steward's output is one `docs:` PR per run. On local-only repos, it is one branch (or one journal-logged change set) presented for approval.
- Pairs naturally with ci-gates: the steward proposes judgment changes, CI enforces the mechanical ones (P07).

## Changelog

- 1.0.0 (2026-07-14): initial release.
