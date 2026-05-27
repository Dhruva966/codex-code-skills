---
name: frontend-patterns
description: Use when building or reviewing React and modern frontend code. Covers composition, custom hooks, async data patterns, state management, forms, rendering, and performance heuristics.
---

# Frontend Patterns

Prefer components that are easy to reason about, test, and change.

## Core Patterns

- composition over monolithic components
- custom hooks for reusable stateful behavior
- clear async loading, success, and error states
- state close to where it is used unless there is a real sharing need
- forms with explicit validation and user feedback

## Performance Heuristics

- avoid premature memoization
- split large components when behavior and rendering concerns are mixed
- watch list rendering and unnecessary refetching
- make state transitions and data ownership obvious

## Review Questions

1. Is the component boundary clean?
2. Are loading/error/empty states handled?
3. Is state local, lifted, or shared for a real reason?
4. Is the code readable without tracing five indirections?
5. Are performance choices evidence-based rather than ritual?
