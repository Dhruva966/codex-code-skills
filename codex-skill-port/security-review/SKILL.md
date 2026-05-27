---
name: security-review
description: Use when handling auth, user input, secrets, uploads, API endpoints, payments, or sensitive data. Applies a practical security checklist covering validation, authorization, injection, secret handling, and data exposure.
---

# Security Review

Security review should happen while designing and coding, not only after.

## Check Areas

1. Secrets
   - no hardcoded credentials
   - env vars or secret manager only
   - no accidental exposure in logs, docs, or examples

2. Input validation
   - validate all user-controlled input
   - use allow-lists and schemas
   - constrain uploads by type, size, and extension

3. Injection resistance
   - parameterized queries only
   - avoid shell injection, path traversal, template injection, and unsafe eval

4. Auth and authorization
   - verify identity and permissions before sensitive actions
   - store session/token material safely
   - check row-level or object-level access where relevant

5. Data exposure
   - minimize returned fields
   - avoid leaking internal errors or sensitive metadata
   - audit logs and analytics for secrets

6. Browser/app surface
   - XSS, CSRF, open redirects, unsafe HTML, insecure cookies

## Output

- highest-risk findings
- concrete exploit or failure mode
- safest mitigation
- missing verification or test coverage

Be conservative. A “maybe exploitable” trust boundary issue deserves attention.
