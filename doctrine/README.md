# Doctrine

The "why" layer: the process principles every component mechanizes. Components tell an agent what to do; doctrine records why the rule exists, so a future maintainer can tell when a rule stopped earning its keep.

## Article format

One principle per file, numbered `P01`, `P02`, and so on. Each article carries exactly three sections:

- **Statement.** The rule, in one or two sentences, stated so a reader could apply it without the rest of the file.
- **Rationale.** Why the rule exists, argued from mechanics (what force it counteracts), not from authority.
- **What breaks without it.** The concrete failure mode observed or predicted when the rule is absent. If nothing would break, the article fails the deletion test and should not be adopted.

Provenance is stated generically ("field-tested in a product-development repo"), never by repo, product, or person name. This library is person-agnostic by construction.

## Mutation rule

Amendment only. An adopted article body is never edited or deleted. To change a principle: add a new article (or a new version of one) and record the change in `amendments.md`; the superseded article gets a one-line status stamp under its heading pointing at its successor. This is P08 applied to the doctrine itself.
