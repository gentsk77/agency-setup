# agency-setup

A process library for agent-driven projects: the distilled working system from two field-tested repos (a full product-development repo and an evaluation-pipeline repo), packaged so any new repo can install exactly the slice it needs.

**To set up a new repo:** point that repo's agent at this library and say "set this repo up using agency-setup". The agent reads [SETUP.md](SETUP.md), interviews you (one question at a time, recommendation first), and installs the right components.

## What lives where

| Path | What |
|---|---|
| [SETUP.md](SETUP.md) | The router: interview + install procedure a foreign agent follows |
| [doctrine/](doctrine/) | The why: ten process principles, amendment-only |
| [components/](components/) | The installables: versioned templates with manifests |
| [profiles/](profiles/) | Presets: full-dev, docs-research, eval-pipeline, minimal |
| [setup/harvest.md](setup/harvest.md) | The reverse flow: mining live repos for library improvements |
| [docs/](docs/) | This repo's own memory core (it self-hosts its doctrine) |

## The model

- **Copy with provenance:** installs copy files and stamp them `component@version`; repos evolve independently.
- **Agents propose, the maintainer ratifies:** every doctrine change is a logged amendment; every component change bumps a version.
- **Person-agnostic:** the library carries process mechanics only; no product, domain, or personal content.
