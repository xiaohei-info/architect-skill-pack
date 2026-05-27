# architect-skill-pack

Languages: [English](README.md) | [简体中文](README.zh-CN.md)

[![Release](https://img.shields.io/github/v/release/xiaohei-info/architect-skill-pack?display_name=tag)](https://github.com/xiaohei-info/architect-skill-pack/releases)
[![License](https://img.shields.io/github/license/xiaohei-info/architect-skill-pack)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/xiaohei-info/architect-skill-pack)](https://github.com/xiaohei-info/architect-skill-pack/commits/main)

**A reusable open-source skill pack for architecture work: survey, solution design, technical overview, detailed design, deployment handoff, and architecture-grade diagrams.**

This pack is **not Hermes-only**. It is packaged in `SKILL.md` form for easy Hermes installation, but the methods are also intended for **OpenCode, Codex, Claude Code, and other general-purpose agent runtimes**.

Use this repository when your architect agent or architecture workflow has one of these failure modes:
- it jumps from vague demand straight into implementation
- architecture docs mix business framing, technical design, and deployment details into one blurry artifact
- diagrams exist, but each one answers the wrong question
- solution survey is shallow, so teams rebuild what mature systems already solved
- detailed design is incomplete, so implementation starts without clear flows, contracts, or verification paths

You can adopt **one skill**, **one bundle**, or the **full pack** depending on what your team is missing.

## What you get

If you adopt this pack well, you should get:
- clearer stage selection before architecture work starts
- better separation between business-solution, system, technical, and deployment artifacts
- diagrams that answer distinct questions instead of repeating each other
- more implementation-ready detailed design outputs
- more explicit trade-offs, reuse decisions, and verification paths in architecture work

![architect-skill-pack social preview](assets/social-preview.svg)

## Runtime compatibility

You can use this repository in at least two ways:

- **Direct install path** — Hermes users can install the skill folders directly.
- **Method library path** — OpenCode, Codex, Claude Code, and similar agents can treat each skill as a reusable architecture playbook, then map the steps into their own prompt, command, planner, or subagent workflow model.

See [`docs/runtime-adaptation.md`](docs/runtime-adaptation.md) for concrete mapping guidance.

## What this pack contains

This repository packages 17 architect-role skills into three public bundles:

- **lifecycle-methodology** — stage routing and end-to-end architecture delivery discipline
- **diagramming** — business architecture, business flow, system architecture, technical architecture, and core-flow diagramming methods
- **architecture-supplements** — DDD boundary modeling, design-pattern/refactoring guidance, and technology adoption comparison

## Start small: one skill, one bundle, or the full pack

You do **not** need to install everything.

- **One skill** — fix one sharp architecture failure
  - Example: `lifecycle-methodology/arch-lifecycle-delivery`
- **One bundle** — improve one class of architecture work
  - Example: `diagramming/`
- **Full pack** — install the whole architecture workflow kit

## Good first picks by need

### If architecture work starts too early or in the wrong stage
Start with:
- `lifecycle-methodology/arch-lifecycle-delivery`
- `lifecycle-methodology/arch-lifecycle-demand-survey-methodology`

### If solution design is fuzzy
Start with:
- `lifecycle-methodology/arch-lifecycle-solution-design-methodology`
- `diagramming/arch-lifecycle-solution-design-biz-flow-diagramming`
- `diagramming/arch-lifecycle-solution-design-biz-arch-diagramming`

### If technical design is missing structure
Start with:
- `lifecycle-methodology/arch-lifecycle-tech-overview-methodology`
- `lifecycle-methodology/arch-lifecycle-tech-detailed-methodology`
- `diagramming/arch-lifecycle-tech-detailed-core-flow-diagramming`
- `diagramming/arch-lifecycle-tech-detailed-technical-arch-diagramming`

### If technology choices keep turning into opinion fights
Start with:
- `architecture-supplements/technology-adoption-comparison`
- `architecture-supplements/ddd-domain-modeling-for-architecture`
- `architecture-supplements/design-patterns-and-refactoring`

## Installation paths

### Path A: direct install into Hermes

### Prerequisites

Before installing into Hermes, make sure:
- you already have a working Hermes installation
- your skill library path exists or can be created under `~/.hermes/skills/`
- you will copy the **whole skill directory**, not only `SKILL.md`

### 1. Clone the repo

```bash
git clone https://github.com/xiaohei-info/architect-skill-pack.git
cd architect-skill-pack
```

### 2. Copy one skill into your Hermes skill library

Example: install `arch-lifecycle-delivery` only.

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery   ~/.hermes/skills/software-development/
```

### 3. Or copy one full bundle

Example: install the full lifecycle bundle.

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/* ~/.hermes/skills/software-development/
```

### 4. Path B: use as a method library in OpenCode, Codex, Claude Code, or similar agents

If your host does not support Hermes-style skill installation, keep the repository as a workspace-side method library and do this instead:

1. pick the target skill folder
2. read its `SKILL.md` plus any `references/` or `templates/`
3. map the workflow into your host's equivalent of:
   - reusable prompt or playbook
   - custom command
   - planner checklist
   - subagent/delegation pattern
4. keep the host-specific wiring outside the public skill when possible

See [`docs/runtime-adaptation.md`](docs/runtime-adaptation.md) for a runtime-by-runtime mapping guide.

### 5. Preserve support files

Always copy the whole skill directory, not only `SKILL.md`.

That means preserving any bundled:
- `references/`
- `templates/`
- `scripts/`
- `assets/`

## Use it outside Hermes too

Hermes is the easiest direct-install path because the repository already uses `SKILL.md` packaging, but the methods are meant to travel.

Practical host examples:
- **OpenCode** — load a chosen skill as a workspace playbook or task-specific guidance file, then map its process into your agent, planner, and worker flow
- **Codex** — use the skill as a reusable architecture procedure in repo docs, custom command wrappers, or issue/plan templates
- **Claude Code** — use the skill as a repo-side method doc, command recipe, or architecture review checklist
- **Other agent runtimes** — translate the trigger, steps, verification pattern, and output contract into your host's equivalent abstractions

See [`docs/runtime-adaptation.md`](docs/runtime-adaptation.md) and [`docs/portability-notes.md`](docs/portability-notes.md).

## Repository layout

```text
skills/
  lifecycle-methodology/
  diagramming/
  architecture-supplements/

docs/
  adoption-guide.md
  bundles.md
  portability-notes.md
  runtime-adaptation.md
  social-preview.md
  source-map.md

assets/
  social-preview.svg
```

## Why this pack is different

The strongest ideas in this repo are:
- **survey before architecture** instead of jumping straight to custom design
- **stage-specific delivery** instead of one giant design blob
- **diagram responsibility discipline** instead of mixing every concern into one picture
- **implementation-ready detailed design** instead of elegant but unusable architecture prose
- **explicit trade-offs and verification** instead of architecture-by-confidence

## Recommended reading path

1. Pick the failure mode you want to fix.
2. Install one skill or one bundle.
3. Read [`docs/adoption-guide.md`](docs/adoption-guide.md) for rollout guidance.
4. Read [`docs/portability-notes.md`](docs/portability-notes.md) if you are adapting outside Hermes.
5. Read the chosen skill's `SKILL.md` and support files before relying on it in production.

## Related docs

- [`AGENTS.md`](AGENTS.md) — repository working rules for agent collaborators
- [`docs/adoption-guide.md`](docs/adoption-guide.md) — modular adoption paths and install guidance
- [`docs/runtime-adaptation.md`](docs/runtime-adaptation.md) — how to apply the pack in Hermes, OpenCode, Codex, Claude Code, and similar hosts
- [`docs/bundles.md`](docs/bundles.md) — bundle-by-bundle overview
- [`docs/portability-notes.md`](docs/portability-notes.md) — what is host-native vs portable
- [`docs/source-map.md`](docs/source-map.md) — public bundle to original source mapping
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — contribution guidance
- [`SECURITY.md`](SECURITY.md) — responsible disclosure path
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) — participation expectations

## License

MIT
