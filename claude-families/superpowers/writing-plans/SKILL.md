---
name: writing-plans
description: Use when you have specs or requirements for a multi-step implementation and should create an execution plan before touching code. Produces concrete, verifiable, bite-sized steps with exact files and checks.
---

# Writing Plans

Write plans for an engineer who knows the craft but not this codebase.

## Plan Standard

Every plan should make execution obvious:

- exact files to create or modify
- clear task boundaries
- concrete verification commands or checks
- no placeholders like "handle edge cases" or "write tests"
- no speculative architecture

## Workflow

1. Restate the goal.
   - One sentence for what gets built or changed.

2. Map the structure first.
   - Which files are involved?
   - What responsibility does each file hold?
   - Where do tests belong?

3. Break work into bite-sized tasks.
   - Each task should have one dominant purpose and one proving check.
   - Prefer steps that are independently reviewable.

4. Define verification for each task.
   - test command
   - build/lint/typecheck command
   - browser or manual check
   - diff or requirements checklist

5. Self-review the plan.
   - Coverage: every requirement mapped to a task
   - Consistency: names, types, and paths line up
   - Placeholder scan: remove vague instructions

## Good Plan Shape

- Goal
- Architecture
- Tech constraints
- Task 1 ... verify with ...
- Task 2 ... verify with ...
- Risks / open assumptions

If the task is small enough to execute safely without a plan, skip this skill and do the work.
