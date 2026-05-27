# Portability Notes

## What is Hermes-native

This repository uses Hermes-compatible skill packaging:
- `SKILL.md` as the skill entrypoint
- optional `references/`, `templates/`, `scripts/`, and `assets/` beside the skill
- some instructions refer to Hermes tools such as `delegate_task`, `read_file`, `search_files`, `patch`, `write_file`, or `todo`

## What is portable

Most of the core methods are not Hermes-specific:
- survey before solution freeze
- lifecycle-stage routing
- architecture artifact separation
- explicit trade-offs and verification
- DDD boundary thinking
- diagram responsibility discipline

## How to adapt outside Hermes

Translate Hermes-native concepts into the nearest equivalent in your host:

- `skill` -> prompt module / reusable playbook / procedure file
- `delegate_task` -> child-agent / worker / specialist subprocess abstraction
- `read_file/search_files/patch/write_file` -> your file and codebase tooling
- `todo` -> your planner or task-state system

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
