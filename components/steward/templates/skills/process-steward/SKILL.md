---
name: process-steward
description: Recurring process audit. Instruction budgets, decisions-index integrity, STATE currency, tracker and branch hygiene, skill-vs-practice drift, open-questions drift. Produces one proposal-shaped change set. Use on a schedule, when asked to run the steward, or at session end after heavy process churn.
---

# Process steward: the recurring audit

Output contract: **one change set per run** (branch `docs/steward-<yyyy-mm-dd>`), presented as a one-screen report of what was checked, what was fixed mechanically, and what is proposed for judgment. The steward never merges; the maintainer gate applies to it like any lane.

## Checks

1. **Instruction budget:** is CLAUDE.md within its stated budget? Beyond the number, flag deletion-test candidates: lines whose removal would cause no mistakes.
2. **Decisions index integrity:** numbering gaps or duplicates, entries missing from the index, superseded entries missing their status stamp, placeholder numbers that survived a merge.
3. **STATE currency:** did the newest trunk change that materially altered orientation carry a STATE refresh? Compare STATE's content against what that change did, not calendar dates.
4. **Tracker and branch hygiene:** ready PRs with red CI or no review, drafts idle beyond a week, branches with no PR, shipped-but-open tracker items.
5. **Skill-vs-practice drift:** for each `.claude/skills/*/SKILL.md`, does recent merged work contradict the written procedure? Cite the work as evidence; propose amending the skill or the practice, never both.
6. **Open-questions drift:** resolved-but-unchecked items, ⚖ questions missing a recommendation, questions whose subject already shipped.

## Procedure

1. Sweep read-only first; collect all findings before touching anything.
2. Fix mechanical findings directly on the steward branch (stamps, index rows, checkbox pointers, word trims that pass the deletion test).
3. Anything requiring judgment (rewording law, retiring a skill section, closing an item as not-planned) goes in the report as a proposal; do not change it.
4. Present the change set titled `docs: steward pass <yyyy-mm-dd>`; the body is the report.
