# codex-code-skills

Codex-native ports of high-value Claude Code workflows.

This repo does **not** try to reproduce Claude-specific runtime behavior like hooks, slash commands, `.claude` state, or gstack telemetry. It ports the parts that actually travel well:

- debugging workflows
- verification gates
- research discipline
- planning and execution structure
- review rubrics
- QA orchestration
- idea shaping
- session handoff

## What's here

- [`codex-skill-port/`](./codex-skill-port) - the staged skill bundle
- [`claude-to-codex-skill-migration-report.md`](./claude-to-codex-skill-migration-report.md) - research, feasibility notes, and migration guidance

## Included skills

- `codex-superpowers`
- `decision-council`
- `executing-plans`
- `iterative-retrieval`
- `karpathy-guidelines`
- `karpathy-style-engineering`
- `office-hours`
- `parallel-agent-coordination`
- `qa-orchestrator`
- `research-ops`
- `review-rubric`
- `search-first-research`
- `session-handoff`
- `surgical-change`
- `systematic-debugging`
- `verification-before-completion`
- `writing-plans`

## Install

Copy the skill directories into your Codex skills folder:

```bash
mkdir -p ~/.codex/skills
cp -R codex-skill-port/* ~/.codex/skills/
```

## Design principles

- Port leaf workflows, not the full gstack runtime
- Prefer explicit skills over automatic hooks
- Keep skills small and Codex-native
- Treat subagent-heavy Claude patterns as optional adaptations, not assumptions
- Do not force 1:1 parity where Codex has a different or better default

## Non-goals

This repo intentionally does not try to port:

- Claude-only hook behavior
- slash-command ergonomics
- `.claude` or `.gstack` persistence layers
- telemetry, upgrade flows, or local harness state
- plugin marketplace wiring

## Source model

These skills were derived from a broader Claude Code skill collection, then filtered through:

- actual Codex tool availability
- the Agent Skills open standard
- official OpenAI migration guidance
- runtime feasibility in a real Codex environment
