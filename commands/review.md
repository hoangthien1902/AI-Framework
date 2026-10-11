# Review

Follow `AGENTS.md` for global rules. This is an **independent** review pass — not the implementer self-check.

## When required

Per `AGENTS.md` / `rules/workflow.md`:
- Security-sensitive changes
- Auth, payments, data migrations
- Public API changes
- Architectural changes
- User explicitly requests review

Otherwise do not run this command by default.

## Purpose

Review an implementation before treating a sensitive/high-impact task as complete.

## Workflow

1. Read `project-context.md` and the original requirement.
2. Inspect the changed files.
3. Compare with the approved plan (if any).
4. Check tests, edge cases, and security.
5. Report findings.

## Output

- Issues
- Severity
- Suggested fixes
- Approval status

## Rules

- Focus on meaningful issues.
- Do not modify code during review.
- Reviewer perspective and heuristics: `AGENTS.md` section 8.4.
