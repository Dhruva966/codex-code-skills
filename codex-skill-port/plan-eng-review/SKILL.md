---
name: plan-eng-review
description: Use when reviewing an implementation plan, design doc, or architecture before coding. Focuses on execution readiness, data flow, boundaries, edge cases, testing, performance, and hidden assumptions.
---

# Plan Eng Review

Review the plan before the code locks in the mistakes.

## What To Check

- architecture and boundaries
- data flow and state transitions
- interfaces and contracts
- error paths and edge cases
- test strategy and proving checks
- performance or scaling assumptions
- rollout and migration risk

## Review Questions

1. Is the architecture coherent and appropriately simple?
2. Are file/module boundaries clear?
3. Where can hidden coupling or state leaks appear?
4. Which edge cases are unaccounted for?
5. Does the test plan prove the risky parts, not just the happy path?
6. Are there performance, concurrency, or migration concerns?
7. Is anything being deferred that will be much more expensive later?

## Output Shape

- readiness verdict
- strongest concerns
- missing tests or checks
- assumptions to validate first
- recommended plan changes

Be opinionated. Better to catch plan flaws now than after implementation begins.
