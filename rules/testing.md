# Testing Rules

Domain-specific testing guidance. Global verify / “do not invent test results” live in `AGENTS.md`.

## When tests are needed
- New user-facing behavior
- Bug fixes (prefer a regression test when practical)
- Changes to auth, payments, data integrity, or core business rules
- Public API contract changes

## When tests may be skipped (state explicitly)
- Pure typo/copy with no behavior change
- No test harness yet and adding one is out of scope
- User explicitly asks not to add tests

Even when tests are skipped, perform other relevant verification and state what was not tested.
Skipping tests ≠ skipping verification.

## What to test
- Observable behavior, not implementation details
- Happy path + important edge cases + failure cases
- Boundaries: invalid input, empty states, auth denial, timeouts when relevant

## Levels (keep basic)
- Unit: pure logic and isolated functions
- Integration: module boundaries, DB/API wiring when touched
- E2E: critical flows only unless the project already relies on them

## Discipline
- Prefer meaningful tests over coverage theater
- Do not weaken assertions just to make CI green
- Run the most relevant tests after changes
