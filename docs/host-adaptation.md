# Host Adaptation Guide

## Goal

This pack is packaged in `SKILL.md` form, but its core value is **method**, not one specific host.

Use this guide when the user asks:
- can this pack work outside my current host?
- how should I adapt it to my own system?
- what is the equivalent of a skill in my workflow model?

## Two adoption modes

### 1. Direct-install mode

Best fit:
- any host that supports folder-based skill loading with `SKILL.md` as entrypoint

Pattern:
- copy the skill directory into the host skill library
- keep `references/`, `templates/`, `scripts/`, and `assets/` beside the entry file
- load the skill natively in the host runtime

### 2. Method-library mode

Best fit:
- hosts without native `SKILL.md` support
- teams using the methods as playbooks, checklists, or design guides
- any workflow where you want architecture discipline without native skill primitives

Pattern:
- keep this repository in the workspace or team knowledge base
- choose one target skill
- read `SKILL.md` plus support files
- map the method into your own abstractions

## Host mapping principles

When adapting to any host, map these four things:

1. **Trigger condition** → how does your system know when to use this method?
2. **Boundary** → when should it *not* be used?
3. **Execution workflow** → how does your system follow the ordered process?
4. **Verification / output contract** → what proves the method was applied well?

If you keep only the overview paragraph, you did not really port the skill.

## Typical mapping patterns

| Skill concept | Typical host equivalent |
|---------------|------------------------|
| skill folder | method module / playbook / procedure file |
| skill loading | prompt module loading / custom command / task routing |
| delegated worker | child process / subagent / specialist subprocess |
| file/tool references | your codebase tooling or knowledge retrieval layer |
| checklist / verification | closeout gate / review rubric / acceptance criteria |

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
- good: `docs/host-adaptation.md` explains general adaptation patterns
- bad: rewriting a public lifecycle skill so it only makes sense if the reader has one tool's exact command system

## Recommended adoption order

If you are not on a host with native `SKILL.md` support, start in this order:

1. `arch-lifecycle-delivery`
2. `arch-lifecycle-solution-design-methodology` or `arch-lifecycle-tech-overview-methodology`
3. one diagramming skill that matches your most common artifact gap
4. `technology-adoption-comparison`

This gives you routing, stage discipline, one strong artifact method, and one strong decision method before expanding further.

## Verification

Before claiming an adaptation is complete, check:
- the host can actually find and use the chosen method
- support files stayed attached to the method
- the trigger condition is still visible after adaptation
- the verification checklist still exists in some form
- the host-specific glue did not silently change the method boundary