# P02: One fact, one home

## Statement

Every category of fact has exactly one authoritative home (live status on the tracker, rulings in the decision log, requirements in the spec, orientation in STATE). Every other file points to the home; none copies from it.

## Rationale

Duplicated facts drift. Two copies of a status are correct only until the first update that touches one and misses the other, and after that a reader cannot tell which copy is live. Pointers cannot drift: the reader always lands on the current value. Choosing the home also settles write-contention up front, because there is exactly one place an update can go.

## What breaks without it

Status ledgers in docs go stale the day they are written, then get trusted anyway. Agents act on the stale copy, and reconciliation becomes a recurring chore that no one owns. Field observation: a repo that tracked work in both a document table and an issue board spent whole sessions reconciling the two before ruling that the board carries status and docs only point.
