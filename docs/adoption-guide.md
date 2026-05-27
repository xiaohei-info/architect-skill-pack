# Adoption Guide

## Goal

Adopt this repository as a **modular architecture skill pack**, not as an all-or-nothing overwrite.

## Smallest useful adoption profiles

### 1. Minimum

Use when you want one architectural behavior fix quickly.

Install one or two skills such as:
- `arch-lifecycle-delivery`
- `technology-adoption-comparison`
- `arch-lifecycle-tech-detailed-core-flow-diagramming`

### 2. Standard

Use when you want a stable architecture workflow.

Install:
- all of `lifecycle-methodology/`
- selected skills from `diagramming/`
- one or more supplements from `architecture-supplements/`

### 3. Full

Use when you want the whole architecture-delivery chain available.

Install:
- all three bundles

## Hermes install path

The public bundle structure is optimized for browsing. Hermes install paths still follow the original skill category.

For this repository, every skill belongs under:

```bash
~/.hermes/skills/software-development/
```

## Example installs

### Install one skill

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery   ~/.hermes/skills/software-development/
```

### Install one whole bundle

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/* ~/.hermes/skills/software-development/
```

### Install the whole pack

```bash
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/* ~/.hermes/skills/software-development/
cp -R skills/diagramming/* ~/.hermes/skills/software-development/
cp -R skills/architecture-supplements/* ~/.hermes/skills/software-development/
```

## After install

Use the skills deliberately in prompts.

Examples:
- “Use `arch-lifecycle-delivery` to decide the correct architecture stage before proposing a design.”
- “Use `technology-adoption-comparison` to compare these stack options.”
- “Use `arch-lifecycle-tech-detailed-methodology` and `arch-lifecycle-tech-detailed-core-flow-diagramming` to turn this overview into implementation-ready detailed design.”

## Verification

After installation, verify that:
- the copied directories exist under `~/.hermes/skills/software-development/`
- support files were preserved beside `SKILL.md`
- the host runtime can discover and load the installed skills
- the chosen bundle matches the actual problem you want to fix
