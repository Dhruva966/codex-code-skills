---
name: deployment-patterns
description: Use when planning production releases, CI/CD, Dockerized deploys, health checks, rollout strategy, rollback handling, or production-readiness gates.
---

# Deployment Patterns

Deployment design is about safe change under real traffic.

## Choose a Rollout Strategy

- rolling for standard compatible deploys
- blue-green when instant cutover and rollback matter
- canary when you need real-traffic validation before full rollout

## Readiness Checklist

- health/readiness checks exist
- startup and shutdown behavior are understood
- old and new versions can coexist if the rollout requires it
- rollback path is real, not aspirational
- environment-specific config is explicit
- CI verifies build, lint, tests, and deploy artifacts

## Review Questions

1. What happens if only half the instances update?
2. What metrics indicate a bad rollout quickly?
3. What is the fastest safe rollback?
4. Are schema/API changes backward compatible during rollout?
5. Is the deployment pipeline proving the right things before release?
