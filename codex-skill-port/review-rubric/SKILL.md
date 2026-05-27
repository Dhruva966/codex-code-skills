---
name: review-rubric
description: Use when asked to review code, diffs, plans, or implementations. Applies an explicit bug/risk-focused rubric: correctness, scope fidelity, regressions, missing tests, edge cases, and operational risk.
---

# Review Rubric

Review for truth, risk, and fit to the request.

## Default Stance

Focus on:

- correctness
- regressions
- scope drift
- missing verification
- edge cases
- operational or rollout risk

Style-only commentary is secondary unless it hides a bug or makes maintenance materially worse.

## Scope Check

Classify the change:

- Clean: built what was requested, nothing materially extra or missing
- Drift detected: added behavior or abstractions beyond the request
- Requirements missing: some requested behavior is absent
- Unverifiable: evidence is too thin to conclude safely

Be conservative with “done.”

## Review Questions

1. Does this solve the stated problem?
2. Is anything important missing?
3. Did the change alter adjacent behavior?
4. Are failure modes, permissions, data handling, and edge cases covered?
5. Is the verification proportional to the risk?
6. Did the author choose the smallest reasonable change?

## Output Shape

For code review findings:

- severity
- file and line or module
- why it matters
- what would make it safe

If there are no findings, say that clearly and mention residual risk or test gaps.
