---
name: hookless-preflight-postflight
description: Use as an explicit replacement for Claude-style automatic hooks. Runs pre-edit checks, approval-sensitive command checks, and post-edit verification intentionally rather than via hidden automation.
---

# Hookless Preflight Postflight

Codex does not need fake Claude hooks. Do the useful parts explicitly.

## Preflight

Before editing or running risky commands:

- restate the requested change
- identify the files or surfaces likely involved
- note assumptions or ambiguity
- check for destructive or approval-sensitive actions
- decide the proving check before changing code

## During Work

- keep the diff scoped
- avoid unrelated cleanup
- do not run destructive commands without explicit approval
- if the task is current/freshness-sensitive, do the lookup before acting

## Postflight

After editing:

- run the smallest relevant verification first
- broaden verification if the blast radius is larger
- inspect the diff for accidental churn
- confirm whether the original request is fully met, partially met, or blocked

## Use With

- `verification-before-completion` for claiming success
- `systematic-debugging` for failures
- `surgical-change` for scope control
- `qa-orchestrator` for user-facing flows
