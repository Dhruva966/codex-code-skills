---
name: finishing-a-development-branch
description: Use when implementation is complete and verification is green, and you need to decide how to land, preserve, or discard the work. Guides final branch completion without unsafe git shortcuts.
---

# Finishing a Development Branch

Completion is not just “code is written.” It includes choosing the right landing path.

## Sequence

1. verify the relevant tests/checks pass
2. determine the intended base branch
3. choose the outcome:
   - merge locally
   - push and create PR
   - keep branch as-is
   - discard the work

## Rules

- do not proceed while verification is red
- do not delete work without explicit confirmation
- do not force-push casually
- if using a worktree, clean it up only when the chosen outcome makes that safe

## Output

- current verification state
- chosen landing path
- any cleanup still needed
