> ✅ KEEP: Shared framework — do not change when switching projects.

# Security Rules

Domain-specific security only. Global invent / scope / git / secrets-in-commits live in `AGENTS.md`.

## Secrets
- Never hardcode secrets, API keys, tokens, or credentials
- Never commit `.env` or credential files
- Do not print secrets in logs, errors, or chat output

## Input & auth
- Validate and sanitize external input at trust boundaries
- Enforce authentication and authorization where the feature requires it
- Do not bypass auth checks to “make it work”

## Injections
- Use parameterized queries / ORM-safe APIs — no string-built SQL with untrusted input
- Do not pass unsanitized input into shell/commands
- Be careful with HTML/markdown rendering and XSS on UI surfaces

## Data & logging
- Do not log passwords, tokens, PII, or full sensitive payloads
- Return safe errors to clients; keep detailed errors server-side
- Check security impact before adding external dependencies

## Default stance
If unsure whether something is sensitive, treat it as sensitive and ask.
