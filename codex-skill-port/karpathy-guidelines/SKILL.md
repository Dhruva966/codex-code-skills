---
name: karpathy-guidelines
description: Use when writing, reviewing, or refactoring code to reduce common LLM coding mistakes. Emphasizes explicit assumptions, simplicity, surgical changes, and verifiable success criteria.
---

# Karpathy Guidelines

Behavioral guardrails for code generation and refactoring.

## 1. Think Before Coding

Do not assume. Do not hide confusion. Surface tradeoffs.

Before implementing:

- state assumptions explicitly
- if multiple interpretations exist, present them instead of choosing silently
- if a simpler approach exists, say so
- if something is unclear and risky, stop and ask

## 2. Simplicity First

Write the minimum code that solves the problem.

- no features beyond the request
- no abstractions for one-off code
- no speculative configurability
- no defensive handling for impossible scenarios unless the codebase already expects it

If you wrote 200 lines and the same job takes 50, simplify it.

## 3. Surgical Changes

Touch only what you must.

- do not refactor unrelated code
- do not "improve" adjacent style or formatting unless your change requires it
- match local patterns even if you would design it differently from scratch
- remove only the unused code created by your own change

Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

Turn vague tasks into verifiable goals.

Examples:

- "fix the bug" -> reproduce it, add a regression check, make it pass
- "add validation" -> define invalid inputs, test them, implement the smallest fix
- "refactor X" -> preserve behavior and verify before and after

For multi-step work, define each step with its proving check.
