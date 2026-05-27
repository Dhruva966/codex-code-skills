# Claude to Codex Skill Migration Report

Date: 2026-05-26

## Bottom line

Yes, many Claude Code skills can come over to Codex.

The cleanly portable part is the `SKILL.md` workflow logic:

- checklists
- rubrics
- research discipline
- debugging process
- review criteria
- planning structure

The weakly portable part is Claude-specific runtime behavior:

- hooks
- slash commands
- `AskUserQuestion`
- plugin marketplace packaging
- `.claude` / `.gstack` state
- automatic subagent/session mechanics

The right strategy is:

1. port leaf workflows, not the gstack runtime
2. keep skills small and Codex-native
3. replace hooks with explicit preflight/postflight skills
4. use official or standard migration paths when possible

The repo now uses a two-layer structure:

1. `codex-skill-port/` for the flat install bundle that syncs into `~/.codex/skills`
2. `claude-families/` for a grouped close-port catalog that preserves a Claude-like family layout without creating duplicate installed skill names

## High-confidence ports

Already staged in `codex-skill-port/`:

- `api-design`
- `architecture-decision-records`
- `backend-patterns`
- `code-tour`
- `codebase-onboarding`
- `click-path-audit`
- `codex-superpowers`
- `database-migrations`
- `deep-research-report`
- `deployment-patterns`
- `docker-patterns`
- `documentation-lookup`
- `finishing-a-development-branch`
- `frontend-patterns`
- `git-workflow`
- `hookless-preflight-postflight`
- `systematic-debugging`
- `verification-before-completion`
- `search-first-research`
- `research-ops`
- `iterative-retrieval`
- `karpathy-guidelines`
- `karpathy-style-engineering`
- `surgical-change`
- `decision-council`
- `writing-plans`
- `executing-plans`
- `plan-eng-review`
- `python-testing`
- `review-rubric`
- `qa-orchestrator`
- `office-hours`
- `receiving-code-review`
- `rules-distill`
- `security-review`
- `session-handoff`
- `skill-stocktake`
- `parallel-agent-coordination`
- `using-git-worktrees`
- `workspace-surface-audit`

## Best local source families

Directly portable or portable with small edits:

- `verification-before-completion`
- `systematic-debugging`
- `search-first`
- `iterative-retrieval`
- `research-ops`
- `writing-plans`
- `executing-plans`
- `review`
- `qa`
- `office-hours`
- `council`
- `karpathy-guidelines`

Do not port whole-cloth:

- `gstack` runtime
- telemetry / upgrade / memory harness skills
- hook-driven guardrails
- `.claude` or `.gstack` persistence mechanics

## Feasibility map

Clean fit in Codex:

- verification
- debugging
- review rubrics
- planning
- research
- browser-driven QA
- codebase retrieval
- idea shaping
- session handoff

Needs adaptation:

- subagent orchestration
- parallel workstreams
- plan review suites
- deep-research variants tied to specific MCPs
- GitHub review workflows that assume `gh` auth and network

Not feasible 1:1:

- Claude-only hooks
- slash-command ergonomics
- `AskUserQuestion`-centric flows outside supported modes
- gstack telemetry/state machinery

## Online resources that genuinely help

Official / strongest:

- OpenAI `migrate-to-codex` skill
  - <https://github.com/openai/skills/blob/main/skills/.curated/migrate-to-codex/SKILL.md>
- OpenAI skills catalog
  - <https://github.com/openai/skills>
- Agent Skills open standard
  - <https://agentskills.io/specification>
- OpenAI help on skills portability
  - <https://help.openai.com/en/articles/20001066-skills-in-chatgpt>
- Claude Code skills docs
  - <https://code.claude.com/docs/en/skills>
- Claude Code hooks docs
  - <https://code.claude.com/docs/en/hooks>

Useful community bridges:

- `plugin-claude-2-codex`
  - <https://github.com/yibie/plugin-claude-2-codex>
- `npx skills`
  - <https://github.com/vercel-labs/skills>
- OpenPackage platform docs
  - <https://openpackage.dev/docs/platforms>
- OpenClaw migration docs
  - <https://docs.openclaw.ai/cli/migrate>
- Randroids dual-format skills repo
  - <https://github.com/randroids-dojo/skills>
- `troykelly/codex-skills`
  - <https://github.com/troykelly/codex-skills>

Discovery-only, lower signal:

- <https://www.awesomeskills.dev/en>
- <https://www.agentskills.to/>

## Construct translation

Typical mapping:

- `CLAUDE.md` -> `AGENTS.md`
- `.claude/skills/*/SKILL.md` -> Codex skill directories
- `.claude/commands/*.md` -> often best rewritten as Codex skills
- Claude subagents / `agents/*.md` -> Codex agents or delegated workflows
- `.mcp.json` -> sometimes portable, sometimes partial
- Claude hooks -> partial or manual replacement only
- plugins / marketplace wiring -> manual or tool-assisted migration

## Current state

The staged skills are in the workspace, published to the public repository, and synced into `~/.codex/skills`.

## Recommendation

Use the staged bundle as the manual baseline.

Then, if you want broader automated migration beyond this bundle, use:

1. OpenAI `migrate-to-codex` as the reference workflow
2. `plugin-claude-2-codex` for construct translation experiments
3. `npx skills` or OpenPackage if you want a shared cross-agent distribution story
