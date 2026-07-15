# Decision record: agency-setup

Rulings, D-numbered, append-only. A ruling changes only through a new numbered decision that supersedes or amends it; the same change stamps the old entry and updates its index row. An agent that finds reality contradicting a standing decision flags it in `open-questions.md` with a recommendation; only the maintainer retires a decision.

## Index

| # | Ruling |
|---|---|
| D1 | Consumption model: copy with provenance, not live reference |
| D2 | Delivery: template repo with SETUP.md entry doc; the router is a document, not a skill |
| D3 | Feedback loop: harvest procedure, propose-only |
| D4 | Day-one profiles: full-dev, docs-research, eval-pipeline, minimal |

## Entries

## D1: Consumption model: copy with provenance, not live reference

Installs copy component files into the target and stamp each with `component@version` plus install date. Targets evolve independently; improvements return via harvest. Rejected: live references (library edits would silently change every repo's process; targets could not diverge legitimately).

## D2: Delivery: template repo with SETUP.md entry doc

The router is a plain document a foreign agent reads, not a skill. Mechanical ground: a foreign repo's session cannot invoke this library's skills (skills load only from the session's own `.claude/`). Plugin packaging deferred, see open questions.

## D3: Feedback loop: harvest procedure, propose-only

The library carries `setup/harvest.md`: diff installed components against live practice, mine process rulings, propose amendments. Maintainer ratifies every item; harvest never applies unratified changes.

## D4: Day-one profiles: full-dev, docs-research, eval-pipeline, minimal

Four presets over the component registry. Profiles are starting points the interview adjusts, never contracts.
