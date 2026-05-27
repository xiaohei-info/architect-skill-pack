---
name: technology-adoption-comparison
description: "Structured methodology for comparing technology options (frameworks, platforms, tools) and documenting adoption decisions with evidence-based reasoning."
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [architect, technology-evaluation, decision-records, comparison, adoption]
    related_skills: [arch-lifecycle-tech-overview-methodology, solution-survey-protocol]
---

# Technology Adoption Comparison

## Overview

A structured approach for evaluating competing technology options and documenting adoption decisions with evidence-based reasoning. This skill addresses the common architecture task: "Should we use X or Y?" with a reproducible methodology.

## When to Use

Use when:
- Choosing between competing frameworks/platforms (e.g., one agent runtime vs another, React vs Vue)
- Evaluating whether to build vs buy vs adopt open source
- Documenting technology decisions for architecture reviews
- Creating adoption justification with trade-off analysis

Do not use when:
- The decision is already made and you just need implementation help
- Comparing trivial or non-technical options
- The scope is purely preference-based without technical merit

## The Five-Source Evidence Model

A robust technology comparison requires evidence from multiple independent sources:

### 1. Official Documentation & Release Notes
**What to extract:**
- Core capabilities and feature set
- Architecture principles and design philosophy
- Recent release highlights and roadmap direction
- Breaking changes and migration paths

**Tools:**
- `skill_view` for official docs skills
- `search_files` for local release notes
- `web_extract` for official documentation URLs

### 2. Source Code & Implementation Evidence
**What to extract:**
- Actual implementation of key features (not just marketing claims)
- Code quality indicators (test coverage, documentation)
- Integration patterns and extension points

**Tools:**
- `search_files` for implementation details
- `read_file` for key source files

### 3. Third-Party Analysis & Comparisons
**What to extract:**
- Independent benchmark results
- Comparative analyses from trusted sources
- Community sentiment and adoption trends
- Security audit results or CVE history

**Tools:**
- `web_search` for comparison articles
- `web_extract` for detailed analysis
- Look for patterns across multiple sources

### 4. Migration & Adoption Evidence
**What to extract:**
- Migration tools and documentation quality
- Real-world adoption stories
- Community size and activity metrics
- Breaking changes history

**Tools:**
- Search for "migrate from X to Y" patterns
- Check GitHub stars, forks, issues
- Analyze release cadence and maintenance

### 5. Fit-to-Problem Assessment
**What to extract:**
- Alignment with project requirements
- Integration complexity with existing stack
- Team expertise and learning curve
- Long-term maintainability

**Tools:**
- Map features to requirements
- Identify gaps and workarounds needed

## Output Structure

### Adoption Decision Document

```markdown
## Technology Adoption Decision: [Option A] vs [Option B]

### Decision
**Selected:** [Option A]  
**Category:** [direct-adoption | selective-reuse | interface-adoption | build-custom]

### Evidence Summary

| Source Type | Key Finding | Confidence |
|-------------|-------------|------------|
| Official Docs | [Capability X confirmed] | High |
| Source Code | [Implementation detail] | High |
| Third-Party | [Benchmark/comparison result] | Medium |
| Migration | [Migration path exists] | High |
| Fit | [Requirement alignment] | High |

### Trade-off Analysis

| Criteria | Option A | Option B | Winner |
|----------|----------|----------|--------|
| Capability Match | Score | Score | A/B |
| Integration Cost | Score | Score | A/B |
| Maintenance Burden | Score | Score | A/B |
| Community/Support | Score | Score | A/B |
| Risk Profile | Score | Score | A/B |

### Risks & Mitigations

1. **[Risk]** → [Mitigation]
2. **[Risk]** → [Mitigation]

### Non-Goals (What We're NOT Doing)

- Not building custom alternative to [capability that exists]
- Not adopting [feature] in MVP phase
- Not maintaining [component] ourselves

### Verification Path

- [ ] Test [key capability] in isolated environment
- [ ] Validate [integration point] with existing stack
- [ ] Confirm [performance/security] requirements met
```

## Anti-Patterns to Avoid

1. **Single-source decisions** - Don't rely only on marketing materials
2. **Spec-sheet comparison** - Features matter less than fit-to-problem
3. **Ignoring migration cost** - Adoption includes transition, not just end state
4. **Over-engineering** - Don't compare at a level of detail irrelevant to your use case
5. **Permanent decisions** - Document what would change the decision

## References

- `references/hermes-vs-openclaw-example.md` - Example comparison artifact shape

## Related Skills

- `arch-lifecycle-tech-overview-methodology` - For subsequent architecture design
- `solution-survey-protocol` - For broader solution space exploration
