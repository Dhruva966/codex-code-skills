---
name: systematic-debugging
description: Use when encountering bugs, failing tests, build errors, regressions, crashes, performance issues, or unexpected behavior before proposing fixes. Requires root-cause investigation, evidence gathering, minimal hypotheses, and verification.
---

# Systematic Debugging

Core rule: do not patch symptoms before finding the root cause.

## Process

1. Reproduce the issue.
   - Run the failing command or action yourself.
   - Read the full error, stack trace, exit code, and relevant logs.
   - If reproduction is intermittent, gather more evidence before changing code.

2. Locate the change or boundary.
   - Inspect recent diffs and affected files.
   - Trace bad values backward from the failure point to their source.
   - In multi-component systems, add or read diagnostics at each boundary: input, output, config, environment, and state.

3. Compare against working examples.
   - Search the codebase for similar working patterns.
   - Read the nearest tests and implementation, not just names.
   - List concrete differences between working and broken paths.

4. State one hypothesis.
   - Write "I think X is the root cause because Y."
   - Test one variable at a time.
   - If the hypothesis fails, replace it instead of stacking guesses.

5. Fix the source.
   - Prefer a failing regression test or minimal repro before the fix.
   - Make one focused change.
   - Avoid opportunistic refactors while debugging.

6. Verify.
   - Re-run the original failing command.
   - Run the smallest relevant regression suite.
   - Broaden verification only after the focused check passes.

## Stop Signals

Pause and re-investigate when:

- you are about to say "probably", "should fix", or "quick fix"
- you have tried two fixes without explaining why they failed
- each fix reveals a new failure in another part of the system
- the fix requires broad refactoring to explain a narrow symptom

After three failed fix attempts, question the architecture or assumptions before continuing.
