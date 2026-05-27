# Portability Notes

## Core positioning

This repository is **agent-portable architecture method packaging**.

It happens to be easiest to install in Hermes because the folders already follow `SKILL.md` conventions, but the repository is not conceptually limited to Hermes. The methods are meant to be reusable in Hermes, OpenCode, Codex, Claude Code, and similar agent runtimes.

## What is host-native in this repository

Some packaging details are host-native rather than universal:
- `SKILL.md` as the skill entrypoint
- optional `references/`, `templates/`, `scripts/`, and `assets/` beside the skill
- some instructions refer to host abstractions that may need translation, such as skill loading, delegated workers, file-reading tools, or task-state helpers

## What is portable

Most of the core methods are not tied to one host:
- survey before solution freeze
- lifecycle-stage routing
- architecture artifact separation
- explicit trade-offs and verification
- DDD boundary thinking
- diagram responsibility discipline

## Cross-host translation pattern

Translate host-native concepts into the nearest equivalent in your runtime:

- `skill` -> prompt module / reusable playbook / procedure file
- delegated worker concept -> child-agent / subagent / specialist subprocess abstraction
- file/tool references -> your codebase tooling or knowledge retrieval layer
- checklist / verification section -> your closeout gate or review rubric

## Named runtime examples

### Hermes
- strongest direct-install path
- use the skill folders as-is

### OpenCode
- treat the chosen skill as a workspace playbook or reusable architecture method doc
- map the process into your planner and worker flow

### Codex
- treat the chosen skill as a repo-side procedure, issue template companion, or architecture checklist
- keep the verification section intact

### Claude Code
- treat the chosen skill as a stable repo-side operating procedure or review rubric
- keep support references beside the method instead of flattening them away

See [`docs/runtime-adaptation.md`](runtime-adaptation.md) for a more explicit runtime-by-runtime guide.

## Deliberate generalization applied in this public pack

This public copy removes or normalizes:
- machine-specific paths
- user-specific vault names
- role/profile-local packaging language where a generic architect-role phrasing is enough
- local source-map details that only matter in one private workspace

## What still needs host judgment

Do not assume every host should load all skills at once.
Choose the smallest useful subset based on:
- whether the host needs lifecycle routing
- whether the host can benefit from architecture-specific diagrams
- whether the host supports multi-step artifact production and review
- whether the host has a natural place for support references and templates
