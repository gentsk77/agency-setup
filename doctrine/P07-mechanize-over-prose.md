# P07: Prefer a mechanized gate over new prose

## Statement

When a mistake recurs, reach first for a mechanical enforcement (CI check, lint, validation script, PR template checkbox, hook) and only second for a new written rule. A rule that can be checked by a script should be.

## Rationale

Prose rules depend on being read, remembered, and honored at the exact moment of temptation; scripts do not. Every mechanized rule is one the instruction budget (P03) never pays for again, and one that binds agents and humans identically without either having to recall it. Mechanization also forces precision: a rule too vague to check mechanically is usually too vague to follow consistently, and the attempt to script it exposes that.

## What breaks without it

The instruction file swells with rules that are each violated occasionally, and enforcement becomes a review-time argument instead of a red X. Agents in fresh contexts repeat exactly the mistakes the prose warned about, because warnings do not execute. Field observation: word budgets, title grammar, and stale-phrasing checks stopped recurring as review comments only after they became CI jobs.
