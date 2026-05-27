---
name: search-first-research
description: Use before building common functionality, adding dependencies, choosing libraries, evaluating tools, or answering research-heavy/current questions. Searches existing repo patterns and authoritative external sources before custom implementation.
---

# Search-First Research

Prefer existing proven solutions over custom code when the problem is common. Prefer current authoritative sources over memory when facts, APIs, libraries, laws, prices, or recommendations may have changed.

## Workflow

1. Define the need.
   - What capability is required?
   - What language, framework, license, deployment, or security constraints matter?

2. Search locally first.
   - Use `rg` and `rg --files`.
   - Look for helpers, tests, prior integrations, config, and established project patterns.

3. Search external sources when useful or required.
   - For technical implementation, prefer primary sources: official docs, package docs, source repos, RFCs, standards, papers.
   - For current facts or high-stakes domains, browse and cite sources.
   - For package choices, compare maintenance, docs, license, dependency weight, and fit.

4. Decide.
   - Adopt: exact fit, maintained, acceptable license.
   - Extend: good foundation with a thin local wrapper.
   - Compose: a few small tools solve the problem cleanly.
   - Build: no suitable option, or custom code is simpler and lower risk.

5. Implement conservatively.
   - Follow repo patterns.
   - Avoid introducing a dependency for a tiny one-off unless it reduces real risk.
   - Cite sources in the final answer when external research informed the decision.

## Research Report Shape

For broad research, return:

- answer or recommendation
- key evidence
- tradeoffs and uncertainties
- sources
- date-sensitive caveats

Separate facts from inference.
