---
name: backend-patterns
description: Use when structuring backend code, service boundaries, repositories, middleware, transactions, caching, query efficiency, or request validation for server-side systems.
---

# Backend Patterns

Keep business logic explicit and separate from transport and persistence details.

## Preferred Structure

- controllers or handlers for transport concerns
- services for business logic
- repositories or query layers for persistence
- middleware for cross-cutting request concerns

## What To Watch

- N+1 query patterns
- oversized handlers with business logic mixed in
- transactions with unclear boundaries
- caching without invalidation thinking
- validation too late in the request path

## Review Questions

1. Is business logic separated from HTTP or framework glue?
2. Are database calls efficient and intentional?
3. Are transaction boundaries correct?
4. Are validation and errors structured consistently?
5. Would this be easy to test without the whole app running?
