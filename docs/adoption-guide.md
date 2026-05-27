# Adoption Guide

## Goal

Adopt this repository as a **modular architecture skill pack**, not as an all-or-nothing overwrite.

This guide intentionally separates:
- **direct installation** into hosts that support folder-based skill loading
- **method adaptation** for general-purpose agents such as OpenCode, Codex, and Claude Code

## Smallest useful adoption profiles

### 1. Minimum

Use when you want one architectural behavior fix quickly.

Adopt one or two skills such as:
- `arch-lifecycle-delivery`
- `technology-adoption-comparison`
- `arch-lifecycle-tech-detailed-core-flow-diagramming`

### 2. Standard

Use when you want a stable architecture workflow.

Adopt:
- all of `lifecycle-methodology/`
- selected skills from `diagramming/`
- one or more supplements from `architecture-supplements/`

### 3. Full

Use when you want the whole architecture-delivery chain available.

Adopt:
- all three bundles

## Path A — direct install into Hermes

The public bundle structure is optimized for browsing. Hermes install paths still follow the original skill category.

For this repository, every skill belongs under:

```bash
~/.hermes/skills/software-development/
```

### Example installs

#### Install one skill

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery \
  ~/.hermes/skills/software-development/
```

#### Install one whole bundle

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/* ~/.hermes/skills/software-development/
```

#### Install the whole pack

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/* ~/.hermes/skills/software-development/
cp -R skills/diagramming/* ~/.hermes/skills/software-development/
cp -R skills/architecture-supplements/* ~/.hermes/skills/software-development/
```

## Path B — method adaptation for OpenCode, Codex, Claude Code, and similar agents

If the host does not support Hermes-style skill installation, use the repository as a method library.

### Recommended adaptation workflow

1. pick the target skill folder
2. read `SKILL.md` plus any `references/` and `templates/`
3. extract four things into your host:
   - trigger condition
   - boundary of use
   - ordered process
   - verification / output contract
4. store the adapted method in the host's natural place, such as:
   - workspace docs
   - reusable prompt modules
   - custom commands
   - planner checklists
   - review rubrics
5. keep host-specific glue outside the public method core when possible

### Good examples by host

- **OpenCode** — convert the chosen skill into a workspace playbook plus a task-routing convention
- **Codex** — convert the chosen skill into a repo-side procedure, issue/plan companion, or reusable architecture checklist
- **Claude Code** — convert the chosen skill into a repo-local method doc, command recipe, or architecture review rubric

See [`docs/runtime-adaptation.md`](runtime-adaptation.md) for a more explicit mapping guide.

## After adoption

Use the skills deliberately in prompts, commands, or planning flows.

Examples:
- “Use `arch-lifecycle-delivery` to decide the correct architecture stage before proposing a design.”
- “Use `technology-adoption-comparison` to compare these stack options.”
- “Use `arch-lifecycle-tech-detailed-methodology` and `arch-lifecycle-tech-detailed-core-flow-diagramming` to turn this overview into implementation-ready detailed design.”

## Verification

After adoption, verify that:
- the chosen method is actually reachable in the host
- support files stayed attached beside the method
- the trigger condition is still visible after adaptation
- the verification checklist still exists in some form
- the chosen bundle matches the actual problem you want to fix
