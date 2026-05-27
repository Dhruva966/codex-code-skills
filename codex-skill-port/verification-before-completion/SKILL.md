---
name: verification-before-completion
description: Use before claiming work is complete, fixed, passing, ready, merged, or PR-ready. Requires fresh verification evidence from commands, browser checks, screenshots, or source inspection before success claims.
---

# Verification Before Completion

Core rule: evidence before claims.

Do not say work is done, fixed, passing, or ready unless you have fresh evidence from this turn.

## Gate

Before making a completion claim:

1. Identify the claim.
   - "Tests pass"
   - "Build succeeds"
   - "Bug is fixed"
   - "UI renders correctly"
   - "Requirements are met"

2. Identify the proof.
   - tests, build, lint, typecheck, browser interaction, screenshot, diff review, or checklist

3. Run or inspect the proof freshly.
   - Read the output.
   - Check the exit code.
   - Count failures, skipped checks, and partial runs.

4. Report precisely.
   - If proof passed, name the command or check.
   - If proof failed or could not run, say so directly and include the blocker.
   - Do not turn partial verification into full confidence.

## Claim Mapping

- Tests pass: requires the relevant test command output.
- Build succeeds: requires build command exit 0.
- Lint/typecheck clean: requires the actual linter/typechecker output.
- Bug fixed: requires reproducing the original symptom and seeing it resolved.
- UI works: requires browser or visual verification when a browser is available.
- Requirements met: requires checking each requested requirement, not just tests.

## Red Flags

Stop before saying:

- should work
- seems fixed
- probably passing
- looks good without running it
- done except for verification

Say the actual status instead.
