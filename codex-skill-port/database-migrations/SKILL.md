---
name: database-migrations
description: Use when planning or reviewing schema changes, backfills, data migrations, rollouts, and rollback strategy. Emphasizes production safety, reversibility, and zero-downtime patterns.
---

# Database Migrations

Treat migration safety as product reliability work, not plumbing.

## Core Principles

- every production schema change is a migration
- prefer forward fixes over rollback fantasy
- separate schema changes from large data backfills
- test on realistic data volume when risk is non-trivial
- never edit an already-deployed migration

## Safety Checklist

Before approving or writing a migration:

- can it lock a large table?
- does it require a rewrite?
- is the new column nullable or safely defaulted?
- is index creation concurrent when needed?
- is backfill separated from DDL?
- is there a rollout and cleanup sequence?

## Preferred Patterns

- expand and contract for renames or removals
- add nullable column, backfill, dual-read/write, then enforce
- separate schema migration from data migration
- batch large updates instead of one giant transaction

## Review Questions

1. What is the production blast radius?
2. What happens on production-sized data?
3. Can old and new app versions coexist during rollout?
4. Is the failure mode recoverable with a forward migration?
5. Has the team separated correctness from convenience?

## Red Flags

- adding `NOT NULL` columns unsafely
- inline backfills on huge tables
- direct renames in live systems
- mixing schema and data changes casually
- no rollout or cleanup plan
