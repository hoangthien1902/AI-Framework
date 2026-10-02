# Project Context


## 1. Project

**Name:** [Project name]

**Purpose:** [What problem does this project solve?]

**Users:** [Who uses it? end-user / admin / internal...]

**Main Goal (current):** [Current priority — 1–3 sentences]

**Status:** [active / mvp / maintenance / experiment]

---

## 2. Tech Stack

**Language(s):** [e.g. TypeScript, Python]

**Frontend:** [e.g. Next.js 15 / React / none]

**Backend:** [e.g. FastAPI / NestJS / none]

**Database:** [PostgreSQL / MongoDB / SQLite / none]

**Auth:** [e.g. NextAuth / JWT / Clerk / not yet]

**Infrastructure:** [Docker / Vercel / AWS / local only]

**Testing:** [Vitest / Jest / Pytest / Playwright / not yet]

**Package Manager:** [pnpm / npm / yarn / uv / poetry]

**Other key libs:** [list 3–10 important libraries]

---

## 3. Architecture

**Overview:** [1–3 sentences describing the architecture]

**Main components:**
- `[path]` — [responsibility]
- `[path]` — [responsibility]
- `[path]` — [responsibility]

**Data flow:** [how requests/events move through the system]

**Important integrations:** [payment / email / AI provider / none]

---

## 4. Entry Points

**App start:** `[file/command that starts the app]`

**API entry:** `[e.g. src/app/api, main.py]`

**UI entry:** `[e.g. src/app/page.tsx / none]`

**Config / env:** `[e.g. .env.example, config/]`

**Key domains/modules:**
- `[path]` — [domain]
- `[path]` — [domain]

---

## 5. Commands

**Install:** `[pnpm install / uv sync / ...]`

**Dev:** `[pnpm dev / make run / ...]`

**Build:** `[pnpm build / ...]`

**Test:** `[pnpm test / pytest / ...]`

**Lint/typecheck:** `[pnpm lint / tsc --noEmit / ...]`

**Other:** `[migrate / seed / storybook / ...]`

---

## 6. Conventions

**Folder structure:** [short description or link to docs]

**Naming:** [files, components, API routes, DB tables...]

**Error handling:** [pattern used in this project]

**API style:** [REST / tRPC / GraphQL — response shape?]

**State management (UI):** [server components / zustand / redux / none]

**PR / commit style for this project:** [e.g. Conventional Commits / short, focus on why]

---

## 7. Constraints

**Hard constraints:** [performance, compliance, offline, model API budget...]

**Compatibility:** [browsers/OS/versions that must be kept]

**Performance budgets:** [if any]

**Dependencies policy:** [can/cannot add libraries freely?]

---

## 8. Do / Don't

**Do:**
- [preferred pattern in this project]
- [preferred pattern]

**Don't:**
- [project anti-pattern]
- [things that must never be touched / done]

---

## 9. Out of Scope (default)

Unless the user explicitly asks, do not:
- [e.g. rewrite auth]
- [e.g. migrate the database]
- [e.g. redesign the entire UI]
- [e.g. change infra/provider]

---

## 10. Notes

[Anything the AI must know before working — secrets policy, staging quirks, known bugs...]
