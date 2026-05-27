# architect-skill-pack

Languages: [English](README.md) | [简体中文](README.zh-CN.md)

[![Release](https://img.shields.io/github/v/release/xiaohei-info/architect-skill-pack?display_name=tag)](https://github.com/xiaohei-info/architect-skill-pack/releases)
[![License](https://img.shields.io/github/license/xiaohei-info/architect-skill-pack)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/xiaohei-info/architect-skill-pack)](https://github.com/xiaohei-info/architect-skill-pack/commits/main)

**A reusable open-source skill pack for architecture work: survey, solution design, technical overview, detailed design, deployment handoff, and architecture-grade diagrams.**

This is a **universal architecture method pack**. Any agent runtime, host system, or architecture team can use it.

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

Any agent runtime, host system, or architecture team can use this pack.

Two common usage modes:
- **Direct install** — hosts that support `SKILL.md` folder-based loading can install directly
- **Method library** — treat each skill as a reusable architecture playbook and map it into your own prompt, command, planner, or workflow model

See [`docs/host-adaptation.md`](docs/host-adaptation.md) for adaptation guidance.

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

### Path A: direct install (hosts with `SKILL.md` support)

If your host supports folder-based skill loading with `SKILL.md` as the entrypoint, install directly.

### Prerequisites

Before installing, make sure:
- the host skill library path exists or can be created
### 3. Install chosen skills

Install into your host's skill library path.

Example for one skill:

```bash
mkdir -p <your-skill-library-path>
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery <your-skill-library-path>/
```

Example for one bundle:

```bash
mkdir -p <your-skill-library-path>
cp -R skills/lifecycle-methodology/* <your-skill-library-path>/
```

Full pack:

```bash
mkdir -p <your-skill-library-path>
cp -R skills/lifecycle-methodology/* <your-skill-library-path>/
cp -R skills/diagramming/* <your-skill-library-path>/
cp -R skills/architecture-supplements/* <your-skill-library-path>/
```

### 4. Path B: use as a method library

If your host does not support `SKILL.md` folder-based loading, use the repository as a method library:

1. pick the target skill folder
2. read `SKILL.md` plus any `references/` or `templates/`
3. map the workflow into your host's equivalent:
   - reusable prompt or playbook
   - custom command
   - planner checklist
   - workflow or delegation pattern
4. keep host-specific wiring outside the public skill when possible

See [`docs/host-adaptation.md`](docs/host-adaptation.md) for adaptation guidance.

### 5. Preserve support files

Always copy the whole skill directory, not only `SKILL.md`.

That means preserving any bundled:
- `references/`
- `templates/`
- `scripts/`
- `assets/`

## Use it in any host

This pack is packaged in `SKILL.md` form, but the methods are universal.

Typical usage patterns:
- hosts with `SKILL.md` support: direct install
- other hosts: method library, playbook, checklist, or workflow reference
- teams without an agent: use as architecture review rubric or design process guide

See [`docs/host-adaptation.md`](docs/host-adaptation.md) and [`docs/portability-notes.md`](docs/portability-notes.md).

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
4. Read [`docs/portability-notes.md`](docs/portability-notes.md) if you are adapting to a different host.
5. Read the chosen skill's `SKILL.md` and support files before relying on it in production.

## Related docs

- [`AGENTS.md`](AGENTS.md) — repository working rules for agent collaborators
- [`docs/adoption-guide.md`](docs/adoption-guide.md) — modular adoption paths
- [`docs/host-adaptation.md`](docs/host-adaptation.md) — how to adapt to your host or workflow
- [`docs/bundles.md`](docs/bundles.md) — bundle-by-bundle overview
- [`docs/portability-notes.md`](docs/portability-notes.md) — what is host-native vs portable
- [`docs/source-map.md`](docs/source-map.md) — public bundle to original source mapping
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — contribution guidance
- [`SECURITY.md`](SECURITY.md) — responsible disclosure path
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) — participation expectations

## License

MIT
