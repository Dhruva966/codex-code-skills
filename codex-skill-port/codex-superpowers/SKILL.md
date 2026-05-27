---
name: codex-superpowers
description: Use when the user asks to bring Claude/Superpowers/gstack workflows into Codex, asks which skills apply, or wants Claude-style skill routing adapted to Codex without Claude-specific hooks or slash-command mechanics.
---

# Codex Superpowers

Adapt portable Claude/Superpowers/gstack workflows into Codex skills and working habits. Do not import Claude-only mechanisms such as `Skill` tool calls, slash command syntax, `allowed-tools`, `hooks`, `AskUserQuestion`, `TodoWrite`, `ExitPlanMode`, telemetry, or `~/.claude`/`~/.gstack` state.

## Routing

Before acting, check whether a requested or clearly relevant skill exists in the current Codex skill list.

Use skills when they materially change the work:

- bugs, failures, unexpected behavior: `systematic-debugging`
- claims of completion, fixes, passing tests, PR readiness: `verification-before-completion`
- broad research or technology choice: `search-first-research`
- context gathering for codebase exploration or subagent prep: `iterative-retrieval`
- current-state evidence gathering and comparisons: `research-ops`
- current library/framework/API answers from primary docs: `documentation-lookup`
- broad cited diligence or landscape synthesis: `deep-research-report`
- independent workstreams, reviewers, or dissenting perspectives: `parallel-agent-coordination`
- risky edits, scope creep, or "keep it simple": `surgical-change`
- writing, reviewing, or refactoring code with simplicity and minimal-diff discipline: `karpathy-guidelines`
- ML, evals, data/model behavior, or learning-by-building loops: `karpathy-style-engineering`
- ambiguous choices with real tradeoffs: `decision-council`
- multi-step implementation planning before touching code: `writing-plans`
- plan-following execution with explicit checks: `executing-plans`
- architecture or implementation-plan readiness review: `plan-eng-review`
- explicit bug/risk-focused review: `review-rubric`
- security-sensitive feature review: `security-review`
- browser-and-behavior shipping checks: `qa-orchestrator`
- early-stage idea shaping and scope pressure-testing: `office-hours`
- API contract or endpoint design: `api-design`
- schema change and rollout safety: `database-migrations`
- repo orientation and architecture mapping: `codebase-onboarding`
- guided walkthroughs of real code paths: `code-tour`
- git branching, commits, rebases, and collaboration hygiene: `git-workflow`
- isolated branch work in separate workspaces: `using-git-worktrees`
- wrapping a session with durable state and open questions: `session-handoff`

If the source Claude skill is tool-specific, keep the underlying workflow and rewrite the mechanics for Codex.

## Portability Test

Port a skill only when:

- it is a durable workflow, checklist, rubric, or domain pattern
- it can be expressed without relying on Claude Code hooks or slash commands
- Codex has equivalent tools, or the skill can describe a manual fallback
- its trigger is narrow enough to avoid noisy activation

Skip or rewrite:

- global "always invoke this before every response" rules
- destructive command hooks that duplicate Codex approval policy
- skills that depend on unavailable MCPs, agents, or local binaries unless guarded by fallback steps
- telemetry, analytics, or personal-state scripts

## Working Rule

Use the smallest useful skill set. A skill should sharpen execution, not become ceremony.
