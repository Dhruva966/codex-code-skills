---
name: api-design
description: Use when designing or reviewing HTTP APIs. Covers resource naming, method semantics, status codes, pagination, filtering, error envelopes, versioning, and compatibility-minded API contracts.
---

# API Design

Design APIs that are predictable, boring, and easy to integrate against.

## Core Rules

- resources are nouns, not verbs
- use plural resource names
- use HTTP semantics honestly
- make errors structured and actionable
- design for compatibility, not cleverness

## Review Checklist

1. Resource shape
   - Are URLs resource-oriented and consistent?
   - Are nested resources justified?

2. Method semantics
   - `GET` for read
   - `POST` for create or explicit actions
   - `PUT` for replacement
   - `PATCH` for partial update
   - `DELETE` for removal

3. Status codes
   - `200`, `201`, `204` for success
   - `400`, `401`, `403`, `404`, `409`, `422`, `429` for client problems
   - avoid `200`-with-error-body anti-patterns

4. Response format
   - consistent success shape
   - structured error shape with code and message
   - field-level details when validation fails

5. List endpoints
   - pagination strategy is explicit
   - filtering and sorting are predictable
   - defaults and limits are documented

6. Compatibility
   - additive changes preferred
   - versioning strategy is intentional
   - no breaking rename or shape drift without migration plan

## Good Outcome

An engineer should be able to infer how a new endpoint behaves from the patterns of the existing ones.
