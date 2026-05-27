---
name: using-git-worktrees
description: Use when starting isolated feature work, parallel experiments, or risky implementation from a clean branch. Creates and verifies git worktrees with attention to ignore rules, setup, and clean baselines.
---

# Using Git Worktrees

Worktrees are for isolation without repo duplication.

## When To Use

- risky or large feature work
- parallel experiments
- keeping current workspace stable
- separating review/fix work from new development

## Workflow

1. Choose a location consistently.
   - prefer an existing worktree directory convention if the repo has one

2. Verify project-local worktree dirs are ignored.
   - avoid polluting git status with worktree contents

3. Create the worktree from the right base branch.

4. Run project setup.
   - install deps only if needed
   - confirm the workspace starts from a clean baseline

5. Verify baseline before real work.
   - run the smallest meaningful test/build check

## Rules

- do not start major work in a dirty ambiguous workspace when isolation would help
- do not skip ignore verification for project-local worktree directories
- do not ignore failing baseline checks
