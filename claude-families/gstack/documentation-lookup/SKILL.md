---
name: documentation-lookup
description: Use when answering library, framework, SDK, or API questions that depend on current behavior. Prefer live official documentation and primary sources over memory, especially for setup, configuration, reference, and examples.
---

# Documentation Lookup

Use current docs instead of stale memory when the answer depends on a library or API.

## When To Use

- setup or configuration questions
- API reference questions
- code examples using a named framework or library
- version-sensitive behavior
- any case where a docs lookup is cheaper than being wrong

## Workflow

1. Identify the concrete library or product.
   - Use the exact user wording when possible.
   - Respect explicit versions.

2. Prefer official or primary documentation.
   - official docs
   - primary SDK docs
   - official source repo docs
   - standards or RFCs when relevant

3. Answer from the docs, not from recollection.
   - include the minimal current example
   - call out version-specific behavior when it matters
   - label uncertainty if docs are unclear

4. Keep the lookup bounded.
   - do not over-research simple API questions
   - do not invent details that the docs did not show

## Rules

- never guess when a current docs lookup is available
- prefer primary sources over blog posts
- if the user’s snippet may contain secrets, do not echo or forward them unnecessarily
- when the docs and your prior memory disagree, trust the docs
