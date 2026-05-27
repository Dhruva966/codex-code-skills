---
name: docker-patterns
description: Use when designing Dockerfiles, Compose stacks, local containerized development, multi-service networking, or container security and image-size practices.
---

# Docker Patterns

Use containers to clarify environments, not to create mysterious ones.

## Focus Areas

- local development Compose layouts
- multi-stage Dockerfiles
- networking and service discovery
- volume strategy
- health checks and dependency readiness
- image size and container security

## Rules

- pin concrete base image versions
- prefer multi-stage builds
- run as non-root in production images
- keep dev and prod stages distinct
- use health checks for critical services
- expose only what must be exposed

## Review Questions

1. Does local development ergonomics match how the app is actually run?
2. Are build layers ordered for cache efficiency?
3. Are secrets excluded from images?
4. Are service dependencies explicit and healthy before startup?
5. Is the production image smaller and safer than the dev image?
