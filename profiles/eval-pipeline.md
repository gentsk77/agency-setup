# Profile: eval-pipeline

For repos that screen candidates against explicit criteria: ideas, vendors, papers, designs, hires. The rulebook is the product; the pipeline keeps judgment honest.

## Component set

memory-core, claude-md-skeleton, gateway, gradable-rules. Add ci-gates if the repo has a remote (it gains the `validate_rules.py` check).

## Follow-up questions

1. **What is the subject?** One noun phrase (fills `{{SUBJECT}}` across the eval skills).
2. **Where do the first rules come from?** If the maintainer has raw criteria (a doc, a list in their head), the first working session is a grilling pass that turns each criterion into a gradable article: Statement, PASS/FAIL/UNCLEAR, Evidence required. Do not import criteria verbatim; ungradable rules fail validation by design.
3. **Human-reserved rules.** Which judgments must never be delegated to an agent judge (taste, gut reaction, personal commitment)? Mark those articles as human-graded in their Grading section.

## First session after install

Write the first rules through the gateway (grill each criterion until it grades), run `python scripts/validate_rules.py` until it exits 0, then run the first candidate through `eval-run` end to end as a shakedown.
