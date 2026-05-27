---
name: decision-council
description: Use when a decision has multiple credible paths and the user wants second opinions, tradeoff surfacing, or explicit challenge before choosing. Uses structured disagreement and keeps the strongest dissent visible.
---

# Decision Council

Use structured disagreement for ambiguous decisions, not for straightforward execution.

## Best Fit

- multiple plausible implementation or product paths
- go / no-go calls
- scope cuts versus polish
- architecture choices with non-obvious tradeoffs
- moments where anchoring on the first idea is risky

## Roles

- Architect: correctness, maintainability, long-term effects
- Skeptic: challenge framing and assumptions, propose a simpler credible alternative
- Pragmatist: optimize for speed, user impact, and operational reality
- Critic: surface edge cases, downside risk, and failure modes

## Workflow

1. Extract the decision.
   - What exactly are we choosing?
   - What constraints matter?
   - What counts as success?

2. Form your initial Architect position first.
   - State your current recommendation.
   - State the biggest risk in your recommendation.

3. Gather only the needed context.
   - Relevant files, metrics, specs, or constraints.
   - Keep it compact.

4. Get independent voices.
   - If subagents are explicitly requested and available, use fresh agents with compact context.
   - Otherwise, simulate the roles sequentially without letting one collapse into the others.

5. Synthesize.
   - Show consensus.
   - Show strongest dissent.
   - Say whether outside challenge changed your mind.
   - End with a recommendation, not a false sense of unanimity.

## Output Shape

- Architect
- Skeptic
- Pragmatist
- Critic
- Consensus
- Strongest dissent
- Recommendation
