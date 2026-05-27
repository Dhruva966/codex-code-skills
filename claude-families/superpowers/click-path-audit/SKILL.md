---
name: click-path-audit
description: Use when UI controls individually look wired but the final user-visible behavior is still wrong. Audits click paths, handler sequences, shared state side effects, and state-transition conflicts.
---

# Click Path Audit

Find bugs where the button works mechanically but the user journey still fails.

## Look For

- later calls undoing earlier state changes
- shared state side effects
- stale closures
- async race conditions
- effects that reset or override intended UI state
- handlers that never reach the promised final state

## Workflow

1. identify the touchpoint
2. trace handler calls in order
3. map what each call reads, writes, and resets
4. compare expected final state against actual final state
5. report the conflicting transition or missing transition

## Best Use

Run this after normal debugging when users still report “the button does nothing” or “the flow feels broken.”
