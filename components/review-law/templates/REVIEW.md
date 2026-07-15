# Review instructions

Review constitution for {{PROJECT_NAME}}. Every PR review reads this file first; amend it via PR like any law.

## What Important means here

Reserve Important for findings that would break behavior or violate standing law:

- Correctness bugs, data-loss risk, broken edge cases.
- Violations of standing decisions (list the repo's own rulings here as they accumulate; cite D-numbers).
- Claims a merge would falsify (e.g. STATE.md saying "awaiting merge").

Style, naming, phrasing, and refactoring suggestions are Nit at most.

## Always check

- Tracker discipline: PRs reference the items they ship.
- Decision-log discipline: superseded entries carry their status stamp; placeholder numbers do not survive a merge.
- Code that makes a CLAUDE.md or skill statement stale flags the doc for update too.

## Do not report

- Anything CI already enforces.
- Formatting preferences with no behavior or law consequence.
- Content of archived or snapshot directories.

## Volume and convergence

- Report at most 5 Nits per review; say "plus N similar items" for the rest.
- After the first review round on a PR, post Important findings only.
- Behavior claims need a `file:line` citation, not an inference from naming.

## Summary shape

Open the review with a one-line tally, e.g. `1 important, 3 nits`, or lead with "No blocking issues."
