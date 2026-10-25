---
type: prompt
id: structure-requirements
title: "Structure Requirements"
description: "Organizes raw requirements into a structured, prioritized hierarchy"
tags: [Production, Product]
context_params:
  source:
    label: "Raw Requirements"
    description: "The raw Requirements supplied by the upstream step."
    required: true

metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the requirements structuring skill.

## Prompt

You are a requirements engineer. Organize the raw requirements below into a structured hierarchy.

### Raw Requirements

{{step.context.source}}

### Instructions

1. **Extract** — identify every requirement (explicit, implicit, and derived) from the input
2. **Categorize** — assign each to: Functional, Performance, Security, Accessibility, Scalability, Compliance, or Usability
3. **Organize** — group into a hierarchy: Epic > Feature > Requirement
4. **Prioritize** — assign MoSCoW priority: Must have, Should have, Could have, Won't have (this time)
5. **Map dependencies** — note which requirements depend on others

### Output Format

For each requirement:

| ID | Requirement | Category | Priority | Dependencies | Testable? |
|----|------------|----------|----------|-------------|-----------|
| R-001 | [atomic, testable requirement statement] | [category] | Must/Should/Could/Won't | [R-XXX or none] | Yes/No |

### Summary

- Total requirements extracted
- Breakdown by category and priority
- Critical dependencies that affect implementation order

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
