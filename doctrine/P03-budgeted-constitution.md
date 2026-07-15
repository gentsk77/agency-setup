# P03: The instruction layer is a budgeted constitution

## Statement

The repo's agent-facing instruction file (CLAUDE.md or equivalent) carries a hard word budget, enforced mechanically. A rule earns entry only after the same mistake happens twice; it is stated once, with procedure delegated to skills and rationale delegated to the decision log. Prune by the deletion test: would removing this line cause mistakes?

## Rationale

Instruction files grow monotonically unless something pushes back, and every marginal line dilutes attention on the lines that matter. Agents (and humans) weight a 300-word constitution; they skim a 3000-word one. The budget converts "should we add this" from a taste argument into an economic one: adding a line means finding words to cut, so only rules that pay rent survive. The two-mistakes bar keeps speculative rules out; the deletion test evicts rules whose risk has passed.

## What breaks without it

Instruction files become append-only landfills where critical invariants sit next to stale one-off notes at equal visual weight. Agents miss the load-bearing rule because it is buried, and maintainers stop reading their own law. Field observation: budget enforcement plus the deletion test kept a heavily-iterated repo's constitution under one screen through sixty-plus recorded rulings.
