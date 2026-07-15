# agency-setup design (approved 2026-07-14)

## What this repo is

A centralized, person-agnostic process library distilled from two field-tested repos: a full e2e product-development repo (the "how": gateway, lanes, review law, handoffs) and an evaluation-pipeline repo (the "why": gradable rules, amendment discipline, bounded loops, judge isolation). New repos point an agent at this repo; a setup flow interviews the maintainer and installs just the right components.

## Decisions taken at design time

1. **Copy with provenance.** The setup flow copies component files into the target repo and stamps each with `component@version` and install date. Repos evolve independently; improvements flow back via an explicit harvest pass.
2. **Template repo plus entry doc.** The router is `SETUP.md`, a plain document the foreign agent reads and follows. Mechanical reason: a foreign repo's session cannot invoke this repo's skills (skills only load from the session's own `.claude/`), so the router must be a document, not a skill.
3. **Harvest skill.** The repo carries a harvest procedure: point it at a live repo, it diffs installed components against actual practice and proposes amendments to the library. Maintainer ratifies.
4. **Four profiles day one:** full-dev, docs-research, eval-pipeline, minimal. Profiles are presets over components; the interview adjusts the set.

## Structure

```
agency-setup/
├── CLAUDE.md            own constitution (self-hosting: follows its own doctrine)
├── README.md            for humans
├── SETUP.md             THE ROUTER: entry point foreign agents read
├── doctrine/            the why: ~10 process principles as amendment-only articles
├── components/          modular installables, versioned, with COMPONENT.md manifests
├── profiles/            presets: named component sets + profile-specific follow-ups
├── setup/harvest.md     harvest procedure
└── docs/                own memory core (STATE, journal, decisions, open-questions)
```

## Layer 1: doctrine/

Ten articles, each: Statement / Rationale / What breaks without it. Amendment-only (add or supersede, logged in `doctrine/amendments.md`, never edit an adopted body). Person-agnostic; provenance stated generically ("field-tested in a product repo"), never by name.

P01 repo-is-memory · P02 one-fact-one-home · P03 budgeted-constitution · P04 grill-before-file · P05 gateway-pattern · P06 maintainer-gates · P07 mechanize-over-prose · P08 append-only-law · P09 evidence-or-no-verdict · P10 fresh-context-isolation

## Layer 2: components/

Each component: `COMPONENT.md` (version, what it installs, placeholders, dependencies, install notes) plus `templates/` holding the exact files to copy. Placeholders use `{{NAME}}` syntax, documented per component.

| Component | Distilled from | Installs |
|---|---|---|
| memory-core | both source repos | STATE/journal/decisions/open-questions templates + mutation rules |
| claude-md-skeleton | both | budgeted CLAUDE.md template: session start/end, repo map, invariants |
| gateway | pm-gateway pattern | product-lead agent charter + gateway skill (intake, routing, dispatch) |
| dev-lanes | coding-handoff + parallel-lanes | builder charter, handoff format, per-commit gates, draft-PR registry, region ownership |
| review-law | review constitution pattern | REVIEW.md template, reviewer charter, PR template, review flow |
| steward | process-steward | recurring audit skill, generalized checks |
| gradable-rules | evaluation pipeline | article format, amendment log, validate script, eval-intake/research/grade/run skills with isolation + bounded loop |
| design-lane | design-lead pattern | design-system-as-law + proposal lifecycle, mechanics only |
| ci-gates | docs-lint CI | GitHub Actions word-budget/phrasing/PR-grammar lint + local pre-commit equivalent |

## Layer 3: SETUP.md (the router)

Foreign agent procedure, dogfooding P04 (one question at a time, recommendation first):

1. What is the project (purpose, artifact type: code / prose / evaluation / mixed)
2. Fidelity (recommend a profile from answer 1; maintainer vetoes)
3. Review posture (PR + review law / commit-needs-approval / free-commit)
4. Git posture (GitHub with CI vs local-only; picks ci-gates flavor)
5. Multi-agent now or later (gateway + lanes vs solo session with upgrade path)

Then: resolve profile to component set, copy files, fill placeholders, stamp provenance headers, write install manifest (`docs/setup-manifest.md` in the target), generate initial CLAUDE.md and STATE.md from answers, hand off ("first braindump goes through your new gateway"). Re-running SETUP.md on an already-installed repo enters upgrade mode: diff manifest versions against the library.

## Harvest loop

`setup/harvest.md`: given a live repo path, read its manifest, diff installed components against actual practice (edits to installed files, process rulings in its decisions/journal), propose amendments to library components with version bumps. Maintainer ratifies every amendment (P06).

## Constraints

- No em dashes anywhere (workspace rule).
- Person-agnostic: roles only; no product names, no maintainer specifics, no domain content from source repos (e.g. rubric CONTENT stays out; rubric FORMAT comes in).
- Workspace git floor applies to this repo: no commit or push without in-the-moment approval.
