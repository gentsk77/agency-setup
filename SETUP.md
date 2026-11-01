# SETUP: the router

You are an agent in some other repo (the **target**), pointed at this library to set up the target's working process. This file is your complete procedure. Read it fully before acting; you cannot invoke this repo's skills from your session, so this document is deliberately self-contained.

The library's principles live in `doctrine/` (read `doctrine/README.md` plus any article you are about to install machinery for); the installables live in `components/` (registry: `components/README.md`); the presets live in `profiles/`; vetted external material (component libraries, fonts, icon sets) is registered in `setup/sources.md`.

## Step 0: fresh install or upgrade?

If the target already contains `docs/setup-manifest.md`, this is an **upgrade**: skip to "Upgrade mode" at the bottom. Otherwise continue.

## Step 1: the interview

Dogfood P04: ask **one question at a time**, each led by your recommendation so the maintainer can accept or veto cheaply. Do not batch the questions. Record every answer; they populate the manifest and the placeholders.

**Q1. What is this project?** Free-form. Listen for: purpose, primary artifact type (code / prose / evaluation / mixed), horizon (throwaway experiment vs long-lived).

**Q2. Fidelity.** Recommend a profile from Q1 and say why:
- ships code seriously → `full-dev`
- writing, research, thinking → `docs-research`
- screens candidates against criteria → `eval-pipeline`
- throwaway or tiny → `minimal`
The maintainer can override or mix ("docs-research plus steward"). Profiles are presets, not contracts; read the chosen profile file in `profiles/` for its follow-up questions and ask those too.

**Q3. Review posture.** Options: (a) PR + review law (every trunk change via PR, reviewed against REVIEW.md before the maintainer looks), (b) commit-needs-approval (agent prepares, maintainer says "commit it"), (c) free-commit on branches, gates at merge. Recommend (a) for full-dev with a remote, (b) otherwise. This answer sets `{{GIT_POSTURE}}` and whether review-law installs.

**Q4. Git posture.** GitHub remote with CI, or local-only? Picks the ci-gates flavor (workflow vs pre-commit hook) and how dev-lanes degrades (see its COMPONENT.md).

**Q5. Multi-agent now or later?** Skip this question for the `minimal` profile: it installs no gateway (see `profiles/minimal.md`), and the gateway is the first component to add if the repo outgrows it. For every other profile the gateway installs either way (the intake discipline is the durable part). If "later", note in the manifest that dev-lanes/design-lane charters are dormant until first dispatch.

**Carry the source defaults.** If design-lane installs, always record the vetted sources matching the target's stack (from `setup/sources.md`: the component library base, motion layer, font catalog, icon set) in the setup manifest as the project's **default component stack**. This is a reference, not an install, and not a question: components-by-default is the standing posture (a designer does not ask whether to use the company's system). The establishment interview in the `design-proposals` skill is where the maintainer confirms **which** library (default = the recorded one) and where anything actually gets adopted; the design system's own law governs how it all looks and when it animates.

## Step 2: resolve the component set

Start from the profile's list (each file in `profiles/` names its set), apply the interview adjustments, then order by the `Requires` column in `components/README.md` (dependencies first). Confirm the final set with the maintainer in one line before installing.

## Step 3: install

For each component, in dependency order:

1. Read its `COMPONENT.md` fully; it carries per-component install notes that override anything generic here.
2. Copy each file under `templates/` to its target path (create directories as needed).
3. Fill every `{{PLACEHOLDER}}` from interview answers; the component's COMPONENT.md documents each one. No placeholder may survive installation.
4. Execute any `<!-- installer: ... -->` comments in the template (conditional sections, rows to add), then delete those comments.
5. Prepend the provenance stamp as the file's first line (after frontmatter, if the file has frontmatter):
   `<!-- agency-setup: <component>@<version>, installed <YYYY-MM-DD> -->`
   For non-markdown files use the file's native comment syntax.

Then:

6. **Write the manifest** at `docs/setup-manifest.md` in the target:

```markdown
# Setup manifest

- source: agency-setup
- installed: <YYYY-MM-DD>
- profile: <name, plus adjustments>

## Interview record

- project: <one line from Q1>
- fidelity: <Q2 answer>
- review posture: <Q3 answer>
- git posture: <Q4 answer>
- multi-agent: <Q5 answer>

## Installed components

| component | version | files |
|---|---|---|
| memory-core | 1.0.0 | docs/STATE.md, docs/journal.md, docs/decisions.md, docs/open-questions.md |
```

7. **Generate the initial `docs/STATE.md` content** from Q1 (real orientation, not template boilerplate) and finish the target's `CLAUDE.md` (fill the repo-map rows for everything you just installed).
8. Do not commit anything yourself unless the target's git posture allows it; otherwise present the change set and suggested commit message and wait.

## Step 4: hand off

Tell the maintainer: setup is complete. If the gateway was installed, the first real braindump should go through it (`.claude/agents/product-lead.md`), which will grill it into the memory core. For the `minimal` profile there is no gateway: tell the maintainer to just work, and that re-running this file to add the gateway is the upgrade path once requirements start arriving as braindumps. If a component was installed dormant, say which and what wakes it.

## Upgrade mode

1. Read the target's `docs/setup-manifest.md` and compare each installed version against `components/README.md`.
2. For each outdated component, read its COMPONENT.md changelog, then **diff the library template against the target's file**. Local edits are legitimate divergence (that is the copy-with-provenance model): never overwrite them blindly. Propose per file: take the update, keep the local version, or merge.
3. Update manifest versions for whatever was taken. Same commit discipline as Step 3.8.
4. If the target's local edits look like an improvement to the library itself, tell the maintainer to consider a harvest pass (`setup/harvest.md`) in the reverse direction.
