---
name: eval-intake
description: Grill the maintainer about a raw {{SUBJECT}} until it is articulated enough to research, then create the evaluation folder. Use at the intake stage of eval-run, or standalone.
---

# Eval intake

Turn a raw {{SUBJECT}} into an articulated candidate a researcher can work on. The output is `evaluations/<YYYY-MM-slug>/00-intake.md` plus `meta.yaml` at status `research`.

## Procedure

1. Listen to the maintainer's whole description first.
2. Read `rules/coverage.md` for the active rulebook. For each rule whose Evidence-required section names a fact only the maintainer can supply, that fact is an intake question.
3. Grill **one question at a time, recommendation first**, until every maintainer-only fact is captured and the candidate is stated crisply enough that a stranger could research it: what it is, for whom, why now, what would count as success.
4. Check hard gates early: if the candidate clearly violates a gate-class rule (or a blacklist, if the repo keeps one), stop, show the maintainer the violated rule, and set status `rejected` on their confirmation. Do not spend research on dead candidates.
5. Write `00-intake.md`: the articulated candidate, the maintainer-supplied facts (attributed as "maintainer statement"), and the questions research must answer. Never pad with guesses; unknowns are listed as unknowns.
6. Set `meta.yaml` status to `research`.

## Rules

- Never answer your own questions. Never file vague. If the maintainer cannot answer a question, record it as an open unknown for research, not as an assumed answer.
