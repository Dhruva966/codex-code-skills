---
name: surgical-change
description: Use when the user asks for minimal, simple, safe, scoped, or surgical changes; when editing risky code; or when scope creep and speculative refactors would increase risk. Emphasizes smallest effective diff, assumptions check, and targeted verification.
---

# Surgical Change

Make the smallest change that solves the real problem.

## Scope Discipline

Before editing:

- Restate the requested behavior in one sentence.
- Identify the exact files and boundaries likely involved.
- List assumptions that could make the change wrong.
- Check nearby patterns before inventing a new one.

During editing:

- Prefer local fixes over broad abstractions.
- Do not bundle unrelated cleanup.
- Preserve public contracts unless the request requires changing them.
- Avoid "while here" refactors.
- Add an abstraction only when it removes real duplication or clarifies a shared invariant.

After editing:

- Review the diff for accidental churn.
- Verify the narrow behavior first.
- Broaden tests only to the affected surface.
- Tell the user what was intentionally left alone if that matters.

## Assumption Check

Ask or investigate when:

- the request can be interpreted in multiple incompatible ways
- data loss, billing, auth, permissions, migrations, or production behavior are involved
- the codebase has an existing pattern that conflicts with the obvious fix
- the smallest change would create a hidden long-term invariant

Otherwise, make a reasonable assumption and keep moving.

## Simplicity Test

A good surgical change is:

- easy to review
- easy to revert
- covered by a focused check
- consistent with the surrounding code
- no broader than the user's actual goal
