# Runtime Adaptation Guide

## Goal

This repository is packaged in `SKILL.md` form, but its core value is **method**, not one specific host runtime.

Use this guide when the user asks:
- can this pack work outside Hermes?
- how should I use it in OpenCode / Codex / Claude Code?
- what is the equivalent of a skill in another agent system?

## Two adoption modes

### 1. Direct-install mode

Best fit:
- Hermes
- any host that already supports folder-based skill loading with `SKILL.md`

Pattern:
- copy the skill directory into the host skill library
- keep `references/`, `templates/`, `scripts/`, and `assets/` beside the entry file
- load the skill natively in the host runtime

### 2. Method-library mode

Best fit:
- OpenCode
- Codex
- Claude Code
- other general-purpose agents without Hermes-style skill loading

Pattern:
- keep this repository in the workspace or team knowledge base
- choose one target skill
- read `SKILL.md` plus support files
- map the method into the host's own abstractions

## Host mapping table

### Hermes

Use when:
- you want the easiest install path
- the host already supports `SKILL.md`

Typical mapping:
- skill folder -> installed Hermes skill
- `references/` / `templates/` -> copied beside the skill
- runtime load -> native skill loading

### OpenCode

Use when:
- you want the method inside an agent workflow, but not necessarily as a native skill primitive

Typical mapping:
- skill -> workspace playbook or repo-side method document
- trigger condition -> task-routing rule or manual operator choice
- numbered steps -> execution checklist
- verification checklist -> closeout gate
- related skills -> neighboring playbooks or linked docs

Good pattern:
- keep one folder or docs page per method
- call the method deliberately when starting a design, review, or comparison task
- preserve support references instead of collapsing everything into one prompt

### Codex

Typical mapping:
- skill -> repository guidance doc, reusable procedure, or issue/plan template
- process section -> repeatable implementation or design checklist
- output contract -> required final response structure
- verification checklist -> pre-closeout review step

Good pattern:
- keep the skill as repo-side documentation
- quote the method in task prompts when needed
- use the same checklist across issues/PRs instead of rewriting it from scratch

### Claude Code

Typical mapping:
- skill -> repo-side method document, command recipe, or review rubric
- trigger condition -> explicit instruction in the prompt or project guidance
- steps -> execution workflow in the current task
- references/templates -> linked supporting docs kept beside the method

Good pattern:
- treat the skill as a stable operating procedure
- keep host-specific command glue outside the public skill when possible
- preserve the verification and boundary sections instead of only copying the overview

## What to preserve when adapting

Even if the host does not support native skill loading, preserve these four things:

1. **Trigger condition**
   - when should this method be used?
2. **Boundary**
   - when should it *not* be used?
3. **Execution workflow**
   - the ordered process, not only the summary
4. **Verification / output contract**
   - what proves the method was applied well?

If you keep only the overview paragraph, you did not really port the skill.

## What not to overfit

Do not rewrite the public skill pack around one host's private quirks unless the repository explicitly adds a separate host-specific integration note.

Prefer:
- public method core
- host-specific wrapper outside the core

Examples:
- good: `docs/runtime-adaptation.md` explains how Hermes / OpenCode / Codex / Claude Code can each consume the same method
- bad: rewriting a public lifecycle skill so it only makes sense if the reader has one tool's exact command system

## Recommended adoption order for non-Hermes hosts

If you are not on Hermes, start in this order:

1. `arch-lifecycle-delivery`
2. `arch-lifecycle-solution-design-methodology` or `arch-lifecycle-tech-overview-methodology`
3. one diagramming skill that matches your most common artifact gap
4. `technology-adoption-comparison`

This gives you routing, stage discipline, one strong artifact method, and one strong decision method before expanding further.

## Verification

Before claiming a non-Hermes adoption is complete, check:
- the host can actually find and use the chosen method
- support files stayed attached to the method
- the trigger condition is still visible after adaptation
- the verification checklist still exists in some form
- the host-specific glue did not silently change the method boundary
