# Harvest: feeding field learnings back into the library

The reverse flow of SETUP.md. Live repos evolve their installed process (that is the point of copy-with-provenance); this procedure mines that evolution and turns it into library amendments. Run it from a session that can read both this library and the live repo. Person-agnostic rule applies with force here: what crosses back into the library is the **mechanic**, stripped of the repo's domain, product, and people.

## Procedure

1. **Read the live repo's `docs/setup-manifest.md`.** No manifest means the repo predates the library or was set up by hand; you can still harvest (steps 3 to 4), but skip the drift diff.
2. **Drift diff.** For each manifest component, diff the installed files (find them by their provenance stamps) against the library's current templates at the manifest's version. Classify each divergence:
   - **Fix** (the live repo corrected something broken): candidate amendment.
   - **Improvement** (the live repo found a better mechanic): candidate amendment.
   - **Localization** (domain-specific adaptation): leave it; note the pattern only if a third repo localizes the same spot the same way, which means the template has a gap.
3. **Mine the decision log and journal.** Read the live repo's `docs/decisions.md` and recent journal entries for process rulings (rulings about how work happens, not what got built). Each is a candidate: a new doctrine article, an edit to a component template, or a new component.
4. **Strip and generalize.** Rewrite each candidate in role-and-mechanic language: no product names, no maintainer specifics, no domain content. If a candidate cannot survive the stripping (the lesson only makes sense in its domain), it does not belong in the library.
5. **Propose, never apply.** Output one change set: per candidate, the evidence (file, decision number, or diff hunk in the live repo), the proposed library change, and the version bumps (component changelog entries; doctrine changes go through `doctrine/amendments.md`). The maintainer ratifies each item (P06).
6. On ratification: apply the changes, bump versions, log amendments. Installed repos pick the changes up at their next SETUP.md upgrade pass; nothing is pushed to them.

## Cadence

On demand, after a live repo goes through visible process churn (a burst of process decisions, a steward pass that amended skills). A quarterly sweep across all installed repos is a reasonable ceiling; harvesting every session is noise.
