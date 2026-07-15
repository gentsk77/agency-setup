---
name: coding-handoff
description: Conventions for writing and executing coding handoffs. Section structure, per-commit gates, verification discipline. Use when writing a handoff doc, implementing one, or reviewing whether handoff work is done.
---

# Coding handoff: writing and executing

Handoffs live at `docs/handoffs/<slug>.md`; shipped ones move to `docs/archive/`.

## Writing a handoff

- **Dependency-ordered sections**, slowest-feedback-loop work first.
- Each section: what and why (one line), numbered steps with `file:line` pointers, explicit acceptance criteria, test expectations.
- Reference tracker items so commits can close them.
- **Out-of-scope guard at the bottom:** list what must NOT be built, especially anything that presumes an unruled ⚖ question.
- Flag known judgment calls as such; the implementer investigates and may disprove the handoff's hypothesis. Deviating is fine if flagged for a one-line maintainer veto in the journal.

## Executing one

0. **Branch first:** create `feat/<handoff-slug>` off the trunk; handoff work never commits to the trunk directly. Section commits land on the branch; the PR squash-merges so the trunk gets one clean commit (title = handoff summary, body carries every tracker close).
1. **One commit per section**, message referencing the section and the item it ships.
2. **Per-commit gates:** `{{TEST_COMMAND}}` green and `{{TYPECHECK_COMMAND}}` clean. Never move on across a red gate.
3. **Verify in the running system**, not just in tests. If a check can only be done by a human on real hardware or a real account, say so explicitly instead of claiming it (evidence or no verdict).
4. **Migrations:** anything touching live data gets an idempotent, one-time, gated migration with a pre-migration backup.

## The PR

- **Title = the squash commit subject on the trunk.** Grammar: `type: summary`, types `feat | fix | docs | design`.
- **Body:** what and why, tracker references, how to review, gates.
- **How to review is mandatory:** where to look, in what order, what needs judgment versus what is mechanical.
- **Gates are human-judgment only** (CI owns the mechanical ones). Delete lines that do not apply; never tick N/A.

## Done means

All sections committed, gates green, tracker items closed, deviations journaled, `docs/STATE.md` refreshed to describe the reality the merge produces (as the final commit before the squash, never "awaiting merge" phrasing that the merge itself falsifies).
