# Claude-style Families

This directory is the **grouped close-port catalog**.

It is organized to feel more like the original Claude Code skill world:

- [`superpowers/`](./superpowers) - execution discipline, debugging, planning, review reception, and completion workflows
- [`gstack/`](./gstack) - audit, QA, review, research, and meta-maintenance workflows
- [`patterns/`](./patterns) - reusable engineering and architecture patterns

## Important

This is a **catalog layer**, not the primary install layer.

The stable Codex install bundle lives in [`../codex-skill-port/`](../codex-skill-port). That flat layout avoids duplicate skill-name collisions in `~/.codex/skills` while still preserving a Claude-like grouped view in the repo.
