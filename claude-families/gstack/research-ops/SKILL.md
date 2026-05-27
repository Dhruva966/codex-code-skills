---
name: research-ops
description: Use when the user wants fresh facts, comparisons, enrichment, or recommendations built from current public evidence and any supplied local context. Separates sourced fact, user-provided context, inference, and recommendation.
---

# Research Ops

Evidence-first wrapper for current-state research.

## When To Use

- the answer depends on current information
- the user wants a comparison or recommendation
- the user already gave partial evidence that needs verification or synthesis
- the same lookup may become a recurring monitor later

## Guardrails

- do not answer current questions from memory when fresh search is cheap
- separate sourced fact, user-provided evidence, inference, and recommendation
- use the lightest research lane that answers the question well

## Workflow

1. Start from what the user already supplied.
   - Sort it into: supported, needs verification, open questions.

2. Classify the task.
   - quick factual answer
   - comparison or decision memo
   - enrichment on people or companies
   - recurring monitoring candidate

3. Gather evidence.
   - Start with targeted search.
   - Escalate to multi-source deep research when synthesis matters.
   - Prefer authoritative and recent sources.

4. Report with clean boundaries.
   - Sourced facts
   - User-provided context
   - Inference
   - Recommendation

5. Include dates when freshness matters.

6. Say when a recurring workflow would be better than repeating manual research.
