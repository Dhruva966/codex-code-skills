---
name: executing-plans
description: Use when implementing from an existing plan or spec with concrete steps. Reviews the plan first, executes tasks in order, verifies each checkpoint, and stops to surface blockers instead of guessing.
---

# Executing Plans

Follow the plan, but do not follow it blindly.

## Workflow

1. Review the plan critically before editing.
   - Is each step clear?
   - Are file paths, commands, and checks concrete?
   - Are there hidden assumptions or missing prerequisites?

2. Turn the plan into a tracked sequence.
   - Use `update_plan` for task status when the work is substantial.
   - Keep one step in progress at a time on the critical path.

3. Execute one task at a time.
   - Make only the changes needed for the current step.
   - Verify the step before moving on.

4. Stop on real blockers.
   - Missing context
   - Wrong or stale plan assumptions
   - Unexpected codebase state
   - Verification that contradicts the plan

5. When blocked, report:
   - what the plan expected
   - what you found instead
   - the smallest reasonable next move

## Rules

- do not skip verification just because the plan sounds plausible
- do not silently rewrite the plan in your head
- do not batch multiple risky steps together without intermediate checks
- if the plan is wrong, fix the understanding before fixing the code
