# Workflow Rules

Decision tree only. Global invent / scope / verify / git / priority live in `AGENTS.md`.
These workflow rules may be overridden **only** with an explicit user statement (see `AGENTS.md`).

## Inspect when
- Before changing code not read in this session
- Before claiming how something works
- Before adding a dependency or new pattern
- When fixing a bug (trace the relevant flow first)
- Before asking the user about missing info (inspect first)

## Plan when
- Multi-file or cross-cutting change
- New feature with design choices
- Auth, payments, data model, migrations, public API changes
- Requirement is ambiguous and assumptions would change the design

How: `commands/plan.md`.
If a meaningful architectural decision exists: invoke `agents/architect.md` inside planning — it does not replace plan approval.

## Ask the user when
- After inspect, missing project context or info still materially affects the solution
- Touching auth / security / payments / prod data
- Adding a new dependency or service
- Large refactor, file deletion, or irreversible action
- Two valid approaches differ a lot in cost/risk

## Implement directly when
- Change is small, local, and low-risk
- Requirement is clear
- Existing pattern is obvious from nearby code
- No architecture or product decision is required
- Missing `[...]` fields in `project-context.md` do not materially affect this change

## Independent review when
Required for security-sensitive, auth, payments, migrations, public API, architectural changes, or when the user requests review.
Otherwise implementer self-check is enough (`AGENTS.md` section 7).
