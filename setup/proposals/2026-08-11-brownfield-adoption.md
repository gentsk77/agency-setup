---
what:   a harvest change set proposing adoption mode (a third install path for targets that already run a process), centered on a full procedure for merging into an incumbent instruction file
why:    SETUP.md recognizes only fresh-install and upgrade; a target with a working process gets treated as greenfield, and its instruction file (the highest-value real estate in any repo) gets overwritten or diluted
status: proposed, unratified; generalized 2026-08-11 after a second field event, awaiting maintainer review
date:   2026-08-11
---

# Harvest proposal: adoption mode, and how to merge into an incumbent CLAUDE.md

## Before you read

- **Background**: this library installs by copying versioned component files into a target repo and stamping each with `component@version` (D1, copy with provenance). `SETUP.md` is the procedure a foreign agent follows. `setup/harvest.md` is the reverse flow: mine a live install for improvements and propose them back. This file is one such change set.
- **Prerequisites**: [SETUP.md](../../SETUP.md) Steps 0 to 3 and Upgrade mode; [doctrine/P02-one-fact-one-home.md](../../doctrine/P02-one-fact-one-home.md); [doctrine/P03-budgeted-constitution.md](../../doctrine/P03-budgeted-constitution.md); [setup/harvest.md](../harvest.md) step 5, which fixes this file's output shape.
- **Terms**: *target* = the repo being set up. *Brownfield target* = a target that already carries a working process the library did not install. *Incumbent* = a file or rule that already exists in the target and is load-bearing. *Home* = the single authoritative location for one category of fact (P02). *Graft* = an insertion into an incumbent file, fenced by paired provenance comments. *Slot* = one of the seven functional jobs an instruction file does (Candidate 5 defines them).
- **Status**: **proposed, unratified.** Nothing here is applied. Per P06 the maintainer ratifies each item; per D7 the changes land through a PR.

## TL;DR

`SETUP.md` branches two ways at Step 0, and a real third state has no procedure: a target with no manifest but a live process of its own. Field-run against one such target, the resolved component set produced seven collisions, and only one was a path collision the current procedure could see. The centerpiece of this proposal is **Candidate 5: a format-independent procedure for merging library components into an incumbent instruction file** (CLAUDE.md or equivalent). It reads the incumbent as seven functional slots rather than as a format, grafts pointers instead of law, mimics the incumbent's style, fences everything it can and registers what it cannot, and never resolves a contradiction in the library's favor. The remaining candidates supply the frame: an adoption doctrine article, a collision survey, four install modes, a manifest schema that records the boundary, and a steward that audits it.

## The gap

`SETUP.md` Step 0 recognizes two states: a manifest exists (upgrade) or it does not (fresh install). A third state occurs in the field and has no procedure: **the target has never met the library, but already runs a process that works and is load-bearing.**

The default path for that state is fresh install, which points the installer at a target whose instruction file is already law, whose journal role is already filled, and whose intake skill already has a posture. Some of that gets quietly overwritten; the rest gets quietly duplicated.

## Field evidence

### First event: the install

One live target: a knowledge-base repo, roughly one week of process history, a hand-written constitution carrying nine artifact rules and four document rules, an explicit thesis that the commit log is the project timeline, and a capture-first intake skill whose stated posture is "do not interrogate, do not interrupt".

Resolving the `docs-research` profile against it surfaced **seven collisions. Exactly one of them was a path collision** (the constitution). The other six were invisible to a path check:

| Collision | Class | Why a path check misses it |
|---|---|---|
| `docs/journal.md` vs the target's commit-log-is-the-timeline thesis | home | new path, but a second home for the same category of fact |
| the skeleton word budget vs a constitution whose every line passes the deletion test | law | the budget is prose inside a file, not a file |
| `gateway` (grill before file) vs a capture-first intake skill | law | zero path overlap; the two postures sit on the same seam |
| `steward` output location vs the target's existing dated-audit directory | home | the template names a location the target already has an answer for |
| `steward` prose checks vs the target's machine-checked invariants command | home | the duplicate is a check, not a file |
| `decisions.md` rejected-alternatives format vs a doc rule banning rejected alternatives | law | the contradiction is between two documents' contents |

**Read the ratio, not the count.** A path-collision check catches one collision in seven on a brownfield target.

### Second event: the target rewrote its constitution, and the graft survived

Two days after install, the same target repartitioned itself: it moved all artifact law out of its instruction file into a spec directory and rewrote the instruction file as a pure router. Three observations matter to this proposal:

1. **The graft survived a wholesale rewrite.** The fenced section was transplanted verbatim into the new file because the fences made it identifiable as library-owned. Grafts must therefore be located by stamp search, never by position or surrounding text.
2. **The unfenceable edits needed their register.** Rows the install had added to a native table could not carry fences; because the manifest registered them, the rewrite re-registered them under the new structure instead of losing them.
3. **A declined component was correctly reversed.** `ci-gates` had been declined with the reason "no remote", which only ever evaluated its CI flavor. A later session installed its local pre-commit flavor as a hard gate. The reversal was legitimate, but only because the decline reason happened to name its premise. Decline records must state the premise they evaluated, so a reversal can test whether the premise still holds.

---

## Candidate 1: adopt doctrine article P11

Evidence: the seven collisions above, six of which resolve in the target's favor on the merits, not as a courtesy.

Proposed new file `doctrine/P11-install-into-gaps.md`:

> # P11: Install into gaps, not over law
>
> ## Statement
>
> When a target already carries a load-bearing process of its own, the library installs into gaps only. Where an installable contradicts a standing rule of the target, or would become a second home for a category of fact the target already houses, **the target's version wins by default.** The divergence is recorded in the manifest, not resolved in the library's favor.
>
> ## Rationale
>
> The library holds no evidence about the target that the target does not already hold. A rule standing in a live repo was paid for in mistakes made there; the library's corresponding rule was paid for somewhere else. Installing over it swaps observed cost for imported cost, which is a strictly worse trade at equal confidence.
>
> The second half is P02 refusing to stop at the library boundary. One fact, one home is a property of the target's fact space, not of the install's file list. A template whose path is free can still open a second home for a category the target already houses, and no path check can see that. The check has to run on categories of fact, not on filenames.
>
> ## What breaks without it
>
> Two failure modes, both terminal for the install. Either the constitution gets overwritten, the maintainer reverts the whole change set, and the components that would have helped are lost with the ones that would not; or the duplicating files land quietly, and months later two homes disagree with no way to tell which is live, which is exactly the drift P02 exists to prevent, reintroduced by the mechanism meant to enforce it.
>
> Field observation: on the first target with a pre-existing process, seven collisions surfaced and a path check would have caught one.

Bump: `doctrine/amendments.md` gets `| A2 | 2026-08-11 | Adopt P11 (install into gaps), from the first brownfield target. |`

## Candidate 2: SETUP.md Step 0 gets a third branch

Proposed replacement for Step 0:

> ## Step 0: which mode?
>
> - Target contains `docs/setup-manifest.md`: **upgrade**, skip to "Upgrade mode".
> - Target has no manifest and no process of its own: **fresh install**, continue to Step 1.
> - Target has no manifest but **already carries a process**: **adoption**. Continue to Step 1; Step 2 becomes mandatory rather than a formality, and instruction-layer components install through the merge procedure (see `claude-md-skeleton`'s COMPONENT.md).
>
> Adoption triggers on any of: an agent instruction file (`CLAUDE.md`, `AGENTS.md`, or equivalent) written by hand rather than generated; a populated `docs/` with its own stated conventions; existing `.claude/skills/` or `.claude/agents/`; a stated convention about what the commit log or an external tracker is for.
>
> In adoption mode the interview keeps every question but changes one default: the maintainer is not choosing a process from scratch, they are choosing which gaps to fill. Ask what is already working before asking what to install.

## Candidate 3: SETUP.md Step 2 becomes the collision survey

Proposed replacement for the current Step 2, which today only orders components by dependency:

> ## Step 2: resolve the set, and in adoption mode survey it
>
> Start from the profile's list, apply the interview adjustments, order by the `Requires` column.
>
> In adoption mode, before installing anything, classify **every template file in the resolved set** against the target. Three classes, each with its own test:
>
> | Class | Test | Default resolution |
> |---|---|---|
> | **Path** | the template's target path already holds a file | never overwrite: merge (instruction files), adapt, or decline |
> | **Home** | the category of fact the template carries already has an authoritative home in the target, at any path or outside the file tree (the commit log, an issue board, an existing command) | defer: do not install, record the incumbent home |
> | **Law** | the template's own content states a rule that contradicts a standing rule of the target | the target's rule wins (P11); decline the contradicting part, or escalate |
>
> Run the home test by asking, for each template, *what question does this file answer*, then asking the target where that question is answered today. Never run it by comparing filenames.
>
> A law collision the maintainer wants resolved the other way (the target's rule changes) is a ruling, not an install step: it goes to the target's decision log with its rejected alternatives, and it needs explicit sign-off before the dependent files land.
>
> Confirm the surveyed set with the maintainer in one line before installing: what installs, what merges, what defers, what declines.

## Candidate 4: four install modes

Every file in the resolved set installs in exactly one of four modes, recorded in the manifest:

- **copied**: the whole template, provenance stamp as the first line. The only mode a fresh install uses.
- **merged**: the component's demands grafted into a file the target already owns, per the Candidate 5 procedure. Applies to instruction files and any other incumbent the maintainer wants extended rather than replaced.
- **deferred**: not installed; the manifest records which existing path, command, or mechanism serves that role.
- **declined**: not installed; the manifest records the ruling, its reason, **and the premise the reason evaluated** (see the ci-gates reversal in the field evidence: a decline whose premise is recorded can be safely re-litigated when the premise falls; one whose premise is implicit cannot).

## Candidate 5: merging into an incumbent instruction file

This is the centerpiece. Targets arrive with instruction files in every shape: monolithic law books, thin pointers, bilingual files, files with no headings at all. The merge procedure must not depend on any particular shape. Proposed home: a new **"Merge mode"** section in `components/claude-md-skeleton/COMPONENT.md` (bumping it to 1.1.0), with SETUP.md Step 3 pointing at it. Full proposed text:

> ## Merge mode: installing into an incumbent instruction file
>
> Used in adoption mode whenever the target already has an agent instruction file. The skeleton template is **not copied**. The incumbent stays the one instruction file; the library enters it as a guest.
>
> ### M1. Inventory the incumbent by slot, not by format
>
> Read the whole file. Map each block (heading, paragraph, table, list) to the functional slot it serves:
>
> | # | Slot | The job it does |
> |---|---|---|
> | 1 | identity | what this repo is, in a line |
> | 2 | session start | what to run or read before working |
> | 3 | session end | what to update before stopping |
> | 4 | conduct law | git posture, permissions, what is forbidden |
> | 5 | artifact law | rules about the repo's actual product |
> | 6 | navigation | where things live; what to read for which task |
> | 7 | self-maintenance | how this file itself changes |
>
> A block that maps to no slot is left untouched. **The inventory is a reading, never a refactor: the incumbent file is not reorganized, renamed, or reordered during install.** Reorganizing is the maintainer's move, on the maintainer's clock.
>
> ### M2. Read the component's slot demands
>
> Each component's COMPONENT.md declares which slots it needs presence in and the minimal graft per slot (for example, memory-core: session start, one pointer to the state file; session end, one line on routing durables; navigation, one row per memory file). A component with no declared demands installs no graft.
>
> ### M3. Resolve each demanded slot
>
> - **Slot empty**: graft a fenced block where the incumbent's own structure suggests it belongs (session-start content near whatever runs first, navigation rows near the existing map). No structure to suggest placement: append at the end, fenced.
> - **Slot occupied, compatible**: graft the minimal delta only. If the incumbent already does the job (it already says "read the state file first"), graft **nothing** and record "satisfied by incumbent" in the manifest. Never restate what the slot already says (P02).
> - **Slot occupied, contradictory**: law collision. The incumbent wins by default (P11). Escalation options for the maintainer, cheapest first: drop the component's demand; scope-limit using the incumbent's own override idiom if it has one (a file that already says "this rule overrides the workspace default" has a native pattern for scoped exceptions; reuse it rather than inventing phrasing); amend the incumbent, which is a ruling in the target's decision log plus sign-off, never an install-time edit.
>
> ### M4. Graft rules
>
> 1. **Pointers, not law.** A graft inserts pointers to installed files plus at most one rule of behavior per component. If a component needs more standing text than that, the text belongs in a file of its own, pointed at. The incumbent file's attention budget is the scarcest resource in the repo, and the library is a guest in it.
> 2. **Style mimicry is mandatory.** Write the graft in the incumbent's natural language (a Chinese file gets a Chinese graft), heading level, list style, and emphasis idiom. Acceptance test: a reader who does not know the library cannot tell grafted lines from native ones except by the fence comments.
> 3. **Fence everything fenceable.** Paired provenance comments in the file's native comment syntax around every inserted region:
>    `<!-- agency-setup: <component>@<version> graft, installed <YYYY-MM-DD> -->` ... `<!-- /agency-setup -->`
> 4. **Register everything unfenceable.** Edits that cannot be fenced without breaking rendering (a row added to a native table, an item added to a native list, a word changed inline) are enumerated in the manifest's graft register: file, a **content anchor** (the row's first cell, the item's opening words; never a line number), the inserted content, component@version. Line numbers rot; content anchors survive rewrites.
> 5. **Never impose the budget.** The skeleton's word budget is offered once in the interview and dropped if the incumbent's every line pays rent. A brownfield constitution that passes the deletion test is not over budget, whatever its word count.
>
> ### M5. Edge cases
>
> - **No instruction file, but conventions live elsewhere** (README, CONTRIBUTING): this is fresh install for the skeleton, but its law lines defer to the existing conventions by pointer instead of restating them.
> - **Multiple instruction files** (an AGENTS.md symlink, nested per-directory files in a monorepo): graft into the file agents actually load for the scope being installed. One fact, one graft; never the same content into two files. A symlink pair counts as one file.
> - **The incumbent is already a router** (thin file pointing at law elsewhere): the graft shrinks to routing-table entries; the component's pointers join the router in its own format.
>
> ### M6. Upgrade contract for grafts
>
> - Locate grafts by **stamp search over the whole file**, never by remembered position. Field observation: a target rewrote its instruction file wholesale two days after install; the fenced graft survived verbatim because the rewrite transplanted it by stamp.
> - A missing fence at upgrade time is a target-authored deletion, which is a ruling: record it, do not re-graft without asking.
> - Registered unfenced edits are verified by content anchor. Anchor gone (the hosting table was deleted): the entry is stale; flag it, never recreate the hosting structure to re-house it.
> - Content changes inside a fence are either a harvest candidate or an accident; the steward surfaces which (Candidate 7).

Bump: `claude-md-skeleton` 1.0.0 to 1.1.0, changelog entry "Merge mode for incumbent instruction files"; the slot-demand declaration convention added to `components/README.md` conventions.

## Candidate 6: manifest schema v2

Evidence: the current schema records what was installed and nothing else, so an upgrade agent cannot distinguish "missing because new" from "ruled out on the merits", and cannot find grafts at all.

Proposed: the manifest template grows three sections, and Upgrade mode grows a reading order.

> ## Installed components
>
> | component | version | mode | files |
>
> ## Graft register
>
> | file | content anchor | inserted content | component@version |
>
> ## Boundary and rulings
>
> | component / file | collision class | resolution | incumbent home / reason and evaluated premise |
>
> Upgrade mode reads the boundary table **before** the installed table: the installed table says what is here, the boundary table says why the rest is not, and the latter is what an upgrade agent is about to get wrong.
>
> New Upgrade-mode rule: **a deferred or declined entry is never installed by a version bump.** Reversing one requires showing its recorded premise no longer holds, plus maintainer sign-off.

## Candidate 7: steward 1.1.0

Evidence: two of the seven collisions were inside this one component, and the second field event added a graft-integrity failure mode.

Proposed changes to the steward skill template:

1. **Output goes to the target's existing home for dated findings** when one exists (resolved during the survey); the template's own branch naming is the fallback.
2. **Never restate in prose a check the target already mechanizes.** If the target has a lint, doctor, or validate command, the skill calls it and reads its output (P02 applied to criteria, P07 applied to enforcement).
3. **New check, status truth:** for every doc carrying a status field, compare it against what later work actually did. Observed failure: an audit still read "proposal awaits ruling" after a later planning document recorded the same proposal as settled.
4. **New check, graft integrity:** fences paired, contents unedited, register anchors still resolving. Unstamped edits inside a fence are a harvest candidate or an accident; surface which.
5. **New check, home overlap:** enumerate the target's fact homes and flag any new file that moved into an occupied one. This is the recurring check P11 needs to keep holding after install day.

Bump `steward` to 1.1.0; update `components/README.md`.

## Candidate 8: profiles are presets, said louder

Evidence: `gateway` sits in the `docs-research` profile and was wholly wrong for the first brownfield target, on the merits.

Proposed one-line addition to `profiles/README.md`:

> In adoption mode, expect to decline profile defaults. A profile encodes what a greenfield repo of that shape needs; a target that already solved one of those needs its own way does not need it twice. Declining a default is the survey working, not the survey failing.

## Candidate 9: log the ruling

Proposed `docs/decisions.md` entry:

> ## D9: Adoption is a third install mode; the incumbent process wins; instruction files are merged, never replaced
>
> A target that carries its own load-bearing process is neither a fresh install nor an upgrade. `SETUP.md` gains adoption mode: a mandatory collision survey over three classes (path, home, law), four install modes (copied, merged, deferred, declined), and a manifest that records the boundary and the graft register as first-class content, read before the installed list on every upgrade. Instruction files are never replaced: the merge procedure (claude-md-skeleton 1.1.0) reads the incumbent as functional slots, grafts pointers in the incumbent's own style, fences what it can, registers what it cannot, and lets the incumbent win every contradiction by default (P11); reversing that is a ruling in the target's decision log with sign-off.
>
> Rejected: treating brownfield as fresh install with manual care (the failure is structural, not carelessness: six of seven observed collisions are invisible to the path check the procedure performs); a force flag that overwrites and lets the maintainer revert (revert is all-or-nothing, so it discards the correct components with the wrong ones); asking the maintainer per file without the taxonomy (the same question asked seven times with no shared vocabulary produces seven inconsistent answers and no record of why); normalizing incumbent instruction files to a library format before merging (the format is the maintainer's, and a normalize step is an overwrite wearing a different name).

## Version bump summary

| Item | Change |
|---|---|
| `doctrine/P11-install-into-gaps.md` | new article |
| `doctrine/amendments.md` | + A2 |
| `SETUP.md` | Step 0 third branch, Step 2 survey, Step 3 four modes + pointer to merge mode, Upgrade mode reading order and no-auto-install rule |
| manifest template inside `SETUP.md` | schema v2: mode column, graft register, boundary table with evaluated premise |
| `components/claude-md-skeleton` | 1.0.0 to 1.1.0: Merge mode section; slot-demand declarations |
| `components/README.md` | conventions: slot-demand declaration; version rows for both bumps |
| `components/steward` | 1.0.0 to 1.1.0: five changes |
| `profiles/README.md` | one line on declining defaults |
| `docs/decisions.md` | + D9 |

`SETUP.md` and the manifest schema are not versioned components; D9 is their record.

## Lineage

- 2026-08-11: first draft, from the install field event (seven collisions, one visible to a path check).
- 2026-08-11 (later): generalized after the second field event (the target rewrote its instruction file into a router and the graft survived by stamp; one decline was legitimately reversed because its premise happened to be recorded). Centerpiece rewritten as the format-independent merge procedure in Candidate 5.
