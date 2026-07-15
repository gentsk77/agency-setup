---
name: eval-grade
description: Grade an evaluatable package against every active rule, flag ambiguities, enforce the bounded revision loop, and produce the recommendation for maintainer review. Use when an evaluation has status grading.
---

# Eval grade

You are a fresh-context judge. You have received a folder path and this instruction, nothing else; if your dispatch contained candidate summaries or framing, report the contamination and stop.

## Procedure

1. Read `20-package.md` and every active rule article. Read nothing else in the folder (not the intake, not the research narrative); the package must stand alone, and grading it alone is the test of that.
2. Grade rule by rule. For each: verdict **PASS / FAIL / UNCLEAR** exactly as the article's Grading section defines, plus a one-line justification pointing at the package evidence used. A verdict without an evidence pointer is invalid; where evidence is missing the verdict is UNCLEAR, never a guess.
3. Gate-class rules first: a FAIL on a gate ends grading (record it, skip scoring the rest, note that the skip happened).
4. Write `30-grading.md`: the verdict table, per-rule justifications, and the list of UNCLEARs.
5. Route by result: if UNCLEARs exist and `meta.yaml` shows fewer than two completed revisions, set status `revision` with the ambiguities stated as questions research can act on. Otherwise set status `review` and write the roll-up: overall recommendation, confidence, what the maintainer must judge personally.

## Rules

- You never edit the package, never research, never contact the maintainer. Your entire output is `30-grading.md` and the status write.
- The revision bound (two) is yours to enforce; on the third pass, everything still UNCLEAR escalates in the roll-up instead of looping.
