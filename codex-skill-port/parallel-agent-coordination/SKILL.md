---
name: parallel-agent-coordination
description: Use when the user explicitly asks for subagents, parallel agents, independent reviewers, multiple perspectives, or delegated workstreams. Coordinates Codex subagents only for independent, well-scoped tasks with clear outputs and non-overlapping write scopes.
---

# Parallel Agent Coordination

Use Codex subagents when the user explicitly asks for delegation, subagents, or parallel agent work. Do not spawn agents merely because a task is large or interesting.

## When To Use

Good fits:

- independent codebase questions that can be answered in parallel
- separate failing test files with different likely root causes
- implementation slices with disjoint file ownership
- independent review passes, such as spec compliance and quality review
- ambiguous decisions where a skeptic or critic can reduce anchoring

Poor fits:

- one tightly coupled bug
- immediate blocking work on the critical path
- tasks likely to edit the same files
- vague "go explore everything" requests

## Coordination Steps

1. Make a local plan first.
   - Identify the immediate task you should do locally.
   - Identify sidecar tasks that can run independently.

2. Write sharp prompts.
   - One task per agent.
   - Include scope, files or modules, constraints, expected output, and what not to touch.
   - For code edits, assign disjoint ownership and tell workers not to revert others' edits.

3. Run in parallel only when independence is real.
   - Explorers answer specific questions.
   - Workers make bounded changes in owned files.
   - Reviewers use the original spec and output, not each other's reviews.

4. Keep moving locally.
   - Do non-overlapping work while agents run.
   - Wait only when the next step truly needs their result.

5. Integrate deliberately.
   - Read each result.
   - Inspect diffs for worker edits.
   - Resolve conflicts.
   - Verify the integrated result with normal tests/checks.

## Review Patterns

For high-risk output, use two independent reviewers with the same rubric. Both must pass for a confident ship signal. If either fails, fix the concrete issue and re-review.

For ambiguous decisions, use three lenses:

- Skeptic: challenge assumptions and propose the simplest credible alternative.
- Pragmatist: optimize for speed, user impact, and operational reality.
- Critic: surface edge cases, downside risk, and failure modes.

Show the strongest dissent in the final synthesis.
