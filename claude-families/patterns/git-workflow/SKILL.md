---
name: git-workflow
description: Use when deciding branching strategy, commit hygiene, merge vs rebase, conflict handling, release flow, or collaborative Git conventions. Emphasizes safe, understandable history.
---

# Git Workflow

Use Git in a way that helps the team reason about change.

## Core Guidance

- keep `main` or trunk deployable
- prefer short-lived branches
- write clear commit messages
- preserve shared history safely
- use `--force-with-lease`, never casual force-push

## Decision Points

1. Branching
   - GitHub flow for most teams
   - trunk-based for high-velocity teams with strong CI and flags
   - release branching only when the release model truly needs it

2. Commits
   - small, reviewable, intentional
   - subject explains what changed
   - body explains why when it matters

3. Merge vs rebase
   - rebase local or single-author branches for cleanliness
   - avoid rewriting shared branch history casually
   - merge when preserving branch history matters

4. Conflicts
   - resolve with understanding, not file-level guesswork
   - re-run tests after conflict resolution

## Red Flags

- vague “WIP” commits in shared history
- force-push to shared or protected branches
- long-lived branches drifting from `main`
- conflict resolution without verification
