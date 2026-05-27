# AGENTS.md

## Purpose

This repository is a library of reusable architect methods and `SKILL.md`-packaged assets that can be installed directly in Hermes or adapted into OpenCode, Codex, Claude Code, and similar agent runtimes.

Use it as:
- a source of installable `SKILL.md` packages
- a reference library for architecture workflow design
- a portability guide for adapting Hermes-style architecture methods to other runtimes

## Read order

When working in this repository:
1. `README.md` — human-facing overview
2. `docs/bundles.md` — what each bundle is for
3. `docs/runtime-adaptation.md` — how the same methods map into different agent runtimes
4. `docs/portability-notes.md` — what is host-native vs portable
5. target `skills/<bundle>/<skill-name>/SKILL.md`

## Editing rules

When modifying this repo:
- preserve each skill as a self-contained unit
- keep linked support files beside the skill
- do not hardcode private machine paths, usernames, or vault names
- keep descriptions optimized for discovery: *when to use the skill* matters more than internal narration
- prefer surgical edits over style churn
- keep architecture-stage boundaries explicit; do not merge business-solution, technical-overview, detailed-design, and deployment concerns into one generic skill unless that merge is intentional and justified

## Publishing rules

Before release:
- verify copied support files are present
- remove or generalize environment-specific assumptions
- ensure README and docs explain repo structure clearly
- do not claim a method is fully generic if it still depends on host-native primitives or one user's local topology

## Installation model

The packaging model is directory-based skill reuse:
- one skill = one folder
- `SKILL.md` is the entrypoint
- `references/`, `templates/`, `scripts/`, and `assets/` stay beside the skill when present

## Scope boundary

This repo is for:
- skill files
- methodology docs
- reusable support references/templates/scripts

This repo is not for:
- private chat logs
- transient task state
- machine-specific deployment secrets
- user-specific vault paths or host-specific wrappers unless they are intentionally labeled as examples
