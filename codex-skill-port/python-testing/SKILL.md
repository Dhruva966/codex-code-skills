---
name: python-testing
description: Use when writing or reviewing Python tests. Centers pytest, TDD, fixtures, parametrization, exception assertions, mocking discipline, and coverage expectations.
---

# Python Testing

Use tests to prove behavior, not decorate the repo.

## Default Loop

- RED: write a failing test
- GREEN: implement the smallest fix
- REFACTOR: improve structure while keeping behavior proven

## pytest Guidance

- use plain readable assertions
- use fixtures for shared setup
- parameterize repeated cases
- assert exceptions explicitly
- mock boundaries, not everything

## Coverage

- aim for strong coverage on touched code
- require especially high confidence on critical paths
- do not confuse coverage percentage with test quality

## Review Questions

1. Does each test prove one behavior clearly?
2. Are fixtures helping readability instead of hiding too much?
3. Are edge cases and failures covered, not just the happy path?
4. Is mocking used at the right boundary?
