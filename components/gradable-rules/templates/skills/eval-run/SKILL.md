---
name: eval-run
description: Orchestrate one {{SUBJECT}} end to end through the evaluation pipeline. Conduct intake, dispatch researcher and grader subagents with isolation, manage the bounded revision loop, present the graded package for maintainer review. Use when the maintainer brings a {{SUBJECT}} to evaluate.
---

# Eval run (orchestrator)

You are the orchestrator, the maintainer's single interface to the pipeline. You run intake through grading; the maintainer rules at review.

## Procedure

1. **Resume check:** if the evaluation folder already exists, read its `meta.yaml` and enter at the step matching its status; never re-run intake or overwrite an existing folder.
2. **Intake:** execute the `eval-intake` skill yourself, in this session. Interactive grilling cannot be delegated.
3. **Research:** dispatch a researcher subagent to execute `eval-research` on the folder. Check the returned package for completeness (every rule's evidence section addressed), never for verdicts.
4. **Grading:** dispatch a grader subagent in a **fresh context**. The dispatch prompt contains the folder path plus the instruction to execute `eval-grade`, nothing else: no candidate content, no summaries, no researcher framing. Never grade inline; this session held the intake and cannot judge it.
5. **Revision loop:** on status `revision`, dispatch the researcher in revision mode, check that every sent-back ambiguity is addressed, then dispatch a **new** grader subagent (fresh context again, same content-free dispatch). The loop is bounded at two revisions; you never override the bound.
6. **Review handoff:** at status `review`, present the grading roll-up, the escalated ambiguities, and any rules reserved for human judgment. The maintainer's verdict goes in `40-review.md`; acceptance is the maintainer's alone.

## Rules

- Ask the maintainer whenever a stage needs a judgment call; never answer intake questions on the maintainer's behalf.
- Maintainer answers flow into research artifacts via the researcher, never into a grader dispatch.
- One candidate per run.
- If a subagent returns an incomplete artifact, re-dispatch once with the gap named; a grader gap is named structurally (which section is missing), never with candidate content. Still incomplete after that: stop and ask the maintainer.
- Stage skills own their `meta.yaml` status writes; you write it only to set `parked`.

## Stop conditions

Status reaches `review`, or the run stops early: a hard gate fails at intake (`rejected`), or the maintainer parks the candidate (`parked`).
