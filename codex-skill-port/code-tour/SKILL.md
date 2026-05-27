---
name: code-tour
description: Use when the user wants a guided walkthrough of how a feature, subsystem, bug path, PR, or architecture slice works. Creates a step-by-step narrative anchored to real files and precise code locations.
---

# Code Tour

Tell a path through the code, not a flat inventory.

## Best Uses

- onboarding tours
- architecture walkthroughs
- bug or RCA walkthroughs
- PR explanation tours
- “explain how this feature works” requests

## Workflow

1. Identify the reader.
   - new engineer, reviewer, debugger, architect, or feature owner

2. Discover the real path.
   - entry point
   - core execution path
   - important boundary or gotcha
   - next place to look

3. Verify anchors.
   - file exists
   - line/block is real
   - references are precise enough to follow

4. Present the tour as a short sequence.
   - what this file/block is
   - why it matters
   - what it connects to next

## Rule

Every step should help the reader move through the system with less confusion than before.
