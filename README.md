# agency-setup

AI coding agents lose the working rules of a repo between sessions and across repos; this library is a set of versioned rules and templates that an agent installs into a repo after interviewing you, so every repo starts with the same memory files, review rules and checks.

**To set up a new repo:** point that repo's agent at this library and say "set this repo up using agency-setup". The agent reads [SETUP.md](SETUP.md), interviews you (one question at a time, recommendation first), and installs the right components.

## What you get

A `full-dev` install (profile: a named preset of components) puts this into the target repo:

```
CLAUDE.md                         budgeted rules file: session start, repo map, invariants
REVIEW.md                         what every PR review is judged against
docs/
  STATE.md  journal.md  decisions.md  open-questions.md
  setup-manifest.md               interview answers, component versions installed
.claude/
  agents/   product-lead.md  builder.md  reviewer.md
  skills/   gateway/  coding-handoff/  parallel-lanes/  process-steward/   (each holds a SKILL.md)
.github/
  pull_request_template.md
  workflows/docs-lint.yml         word budget, stale-STATE and PR-title checks
```

Projects with a UI can add the `design-lane` component. Every installed file carries a stamp naming its component and version.

## How the install goes

```
Agent: What is this project? (recommend: a long-lived TypeScript service)
You:   A budgeting app, mostly code, I will work on it for months.
Agent: Which profile? I recommend full-dev, because you ship code over many sessions.
You:   Yes.
Agent: How should changes reach main? I recommend PR plus review against REVIEW.md.
You:   Yes.
Agent: Test and typecheck commands? (recommend: npm test, tsc --noEmit)
```

## In use

Installed into three repos so far; local adaptations flow back through the harvest procedure in [setup/harvest.md](setup/harvest.md).

## What lives where

| Path | What |
|---|---|
| [SETUP.md](SETUP.md) | The router: interview + install procedure a foreign agent follows |
| [doctrine/](doctrine/) | The why: ten process principles, amendment-only |
| [components/](components/) | The installables: versioned templates with manifests |
| [profiles/](profiles/) | Presets: full-dev, docs-research, eval-pipeline, minimal |
| [setup/harvest.md](setup/harvest.md) | The reverse flow: mining live repos for library improvements |
| [setup/sources.md](setup/sources.md) | The inbound flow: vetting external material (component libraries, fonts, icons) |
| [setup/proposals/](setup/proposals/) | Proposed library changes awaiting a ruling, e.g. installing into an existing repo |
| [docs/](docs/) | This repo's own memory core (it self-hosts its doctrine) |

## Terms

- **Maintainer:** the human who owns a repo and approves its rules and merges.
- **Gateway:** the one agent session the maintainer talks to; it interviews, records decisions, and hands work out.
- **Lane:** a subagent or parallel session that does one stream of work (building, design, review) and reports through files and PRs, not to the maintainer directly.
- **Ruling:** a numbered decision (D1, D2, ...) in `docs/decisions.md`; append-only, changed only by a later ruling.
- **Harvest:** reading live repos for fixes and improvements and proposing them back as versioned library changes.

`docs/` is this repo's own decision record and state, which the library asks every repo to keep; start with [docs/decisions.md](docs/decisions.md).

## License

MIT. See [LICENSE](LICENSE).
