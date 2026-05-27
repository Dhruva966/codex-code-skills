---
name: workspace-surface-audit
description: Use when the user wants to know what the current workspace, tools, plugins, env surface, and integrations can actually do right now. Produces a capability audit and recommends the highest-value next workflow additions.
---

# Workspace Surface Audit

Answer the practical question: what can this workspace actually do, and what is missing?

## Audit Targets

- repo surface
- installed skills
- available tools and plugins
- configured connectors or app integrations
- environment-backed capabilities, without revealing secret values

## Output Sections

1. current surface
2. parity with desired workflows
3. primitive-only gaps
4. missing integrations
5. top next moves

## Rules

- never print secret values
- separate “available now” from “available but not wrapped well” from “missing”
- recommend the right shape for the gap: skill, hookless workflow, tool bridge, or connector
