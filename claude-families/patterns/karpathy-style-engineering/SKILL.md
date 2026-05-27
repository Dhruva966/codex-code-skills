---
name: karpathy-style-engineering
description: Use for ML, AI, evals, data/model behavior, prompt or agent iteration, and prototype-to-production work where the best path is a simple baseline, tight feedback loop, instrumentation, and empirical debugging.
---

# Karpathy-Style Engineering

Build understanding by making the system observable and simple before making it clever.

## Loop

1. Start with the smallest complete thing.
   - A tiny dataset, a minimal prompt, a baseline model, a single golden path, or a simple script.
   - Make it run end to end before optimizing.

2. Inspect the data.
   - Print examples.
   - Check shapes, distributions, labels, nulls, token lengths, and edge cases.
   - Look at failures manually before inventing metrics.

3. Establish a baseline.
   - Record current behavior and a dumb/simple comparator.
   - Use evals, tests, or snapshots that can catch regressions.

4. Change one thing.
   - Keep experiments small.
   - Name the hypothesis.
   - Log the result.

5. Debug empirically.
   - Prefer concrete traces, examples, loss curves, confusion matrices, and failure cases.
   - When behavior is surprising, inspect actual inputs and outputs.

6. Scale only after the small loop works.
   - Add complexity when the baseline exposes the need.
   - Keep interfaces typed, deterministic, and easy for agents to reason about.

## For LLM/Agent Work

- Create representative eval cases before large prompt rewrites.
- Keep prompts short enough to inspect.
- Separate retrieval, reasoning, tool use, and formatting failures.
- Preserve failing examples as regression tests.
- Track cost, latency, and quality together.

## Output Standard

When reporting results, include:

- baseline
- experiment/change
- evidence
- remaining failure modes
- next smallest useful experiment
