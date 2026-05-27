# Portability Notes

## Core positioning

This repository is **universal architecture method packaging**.

It is packaged in `SKILL.md` form for easy installation on hosts that support folder-based skill loading, but the repository is **not limited to one host**. The methods are meant to be reusable in any agent runtime, host system, or architecture team.

## What is host-native in this repository

Some packaging details are host-native rather than universal:
- `SKILL.md` as the skill entrypoint
- optional `references/`, `templates/`, `scripts/`, and `assets/` beside the skill
- some instructions refer to abstractions that may need translation, such as skill loading, delegated workers, file-reading tools, or task-state helpers

## What is portable

Most of the core methods are not tied to one host:
- survey before solution freeze
- lifecycle-stage routing
- architecture artifact separation
- explicit trade-offs and verification
- DDD boundary thinking
- diagram responsibility discipline

## Cross-host translation pattern

Translate host-native concepts into the nearest equivalent in your runtime or workflow:

- `skill` → prompt module / reusable playbook / procedure file
- delegated worker concept → child-agent / subprocess / specialist abstraction
- file/tool references → your codebase tooling or knowledge retrieval layer
- checklist / verification section → your closeout gate or review rubric

## What still needs host judgment

Do not assume every host should load all skills at once.
Choose the smallest useful subset based on:
- whether the host needs lifecycle routing
- whether the host can benefit from architecture-specific diagrams
- whether the host supports multi-step artifact production and review
- whether the host has a natural place for support references and templates

See [`docs/host-adaptation.md`](host-adaptation.md) for more guidance.