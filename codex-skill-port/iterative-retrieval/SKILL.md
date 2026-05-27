---
name: iterative-retrieval
description: Use when exploring an unfamiliar codebase, preparing context for subagents, or solving tasks where you do not yet know which files matter. Progressively retrieves, scores, and refines context in up to three cycles.
---

# Iterative Retrieval

Use a progressive search loop when the right context is not obvious up front.

## When To Use

- unfamiliar repository or subsystem
- broad feature request with unclear ownership
- bug hunt where the failure point is known but the source is not
- preparing compact context for a subagent or review pass

## Loop

Run at most three cycles:

1. Dispatch.
   - Start with broad but relevant search terms.
   - Use `rg`, filename patterns, nearby tests, configs, and entry points.

2. Evaluate.
   - Score each result mentally: direct, related, weak, irrelevant.
   - Note missing context: types, callers, config, tests, terminology.

3. Refine.
   - Add project-specific terms discovered in the first pass.
   - Exclude clearly irrelevant files.
   - Narrow toward the highest-signal modules and tests.

Stop early once you have enough context to act. "Good enough and specific" beats "everything."

## Practical Rules

- Prefer 3 strong files over 20 mediocre ones.
- Learn the codebase's own vocabulary before broadening the search.
- Read tests and call sites, not just implementations.
- Preserve a short list of relevant files and why they matter.
- If context is still missing after three cycles, say what gap remains instead of pretending certainty.
