---
name: eval-research
description: Research an intaken {{SUBJECT}}, build the evidence base, and assemble the evaluatable package. Also handles revision loops when grading sends a package back. Use at the research stage, or on status revision.
---

# Eval research

Turn an articulated candidate into an evaluatable package. Outputs: `10-research.md` (the evidence, cited) and `20-package.md` (the package a grader reads), status to `grading`.

## Procedure

1. Read `00-intake.md` and the active rulebook (`rules/coverage.md`, then each active article).
2. For every active rule, gather the evidence its Evidence-required section names. Every claim in the research doc carries a source: a citation, a dataset, a named analog, or an explicit "maintainer statement" attribution.
3. Distinguish three epistemic levels in writing: **found** (cited), **inferred** (reasoned from cited facts, reasoning shown), **unknown** (stated as unknown). Never promote an inference to a finding.
4. Assemble `20-package.md`: one section per active rule, containing exactly the evidence that rule needs, plus a candidate summary a fresh reader can grade from. The package must stand alone; a grader reads nothing else.
5. List remaining open questions at the bottom of `10-research.md`. Set status `grading`.

## Revision mode

On status `revision`: read the grader's sent-back ambiguities in `30-grading.md`, address each one explicitly in the package (new evidence, or an honest "cannot be resolved, here is why"), append a revision note to `10-research.md`, and set status `grading`. Never argue with the grade itself; resolve the ambiguity or declare it unresolvable.
