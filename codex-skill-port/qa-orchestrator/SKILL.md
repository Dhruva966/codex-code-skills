---
name: qa-orchestrator
description: Use when the user wants QA, pre-ship checking, browser verification, or “does this actually work?” Runs a repeatable QA pass using browser checks, focused shell verification, issue capture, and ship-readiness reporting.
---

# QA Orchestrator

Test the product as a user, not just as a developer.

## When To Use

- “QA this”
- “does this work?”
- before shipping a UI or user-facing workflow
- after a risky feature or bug fix

## Pass Structure

1. Identify the surface area.
   - changed routes, flows, components, commands, or APIs

2. Verify the obvious path.
   - app loads
   - key action works
   - expected success state appears

3. Verify adjacent states.
   - empty
   - loading
   - error
   - retry / refresh
   - auth / permission differences when relevant

4. Use the right tool mix.
   - Browser for live interaction and screenshots
   - shell commands for tests, logs, build, and targeted checks
   - `verification-before-completion` for any shipping claim

5. Document issues immediately.
   - exact repro steps
   - observed result
   - expected result
   - severity

## Output

- health summary
- issues found
- what was verified successfully
- ship-readiness verdict
- what still needs manual confirmation, if anything
