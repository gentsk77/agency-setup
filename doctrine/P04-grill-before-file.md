# P04: Grill before filing

## Statement

Ambiguous input is interrogated before it is recorded: one question at a time, each question led by a recommendation the maintainer can accept or veto. Nothing enters the decision log, the spec, or the backlog while still vague.

## Rationale

A maintainer braindump is raw material, not law. Filing it verbatim launders ambiguity into authority: once a vague sentence sits in the decision log, later sessions treat it as settled and build on whichever reading they happen to take. Questions asked one at a time get answered; a wall of ten questions gets skimmed. Leading with a recommendation converts each question from an open-ended essay prompt into a cheap accept/veto, which respects the maintainer's time and surfaces the agent's reasoning for correction.

## What breaks without it

Vague entries become load-bearing. Two sessions read the same sentence two ways and ship contradictory work, and the contradiction surfaces only at review, where it is expensive. Alternatively the agent blocks on a questionnaire the maintainer never fully answers. Field observation: both source repos independently converged on the same interview grammar (one question, recommendation first) after watching multi-question intakes stall.
