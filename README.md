TOÀN BỘ AI-FRAMEWORK FLOW — UC: LOGIN
"User yêu cầu Agent code chức năng Login"

┌─────────────────────────────────────────────────────────────┐
│                         USER                                │
│                                                             │
│              "Code chức năng login"                         │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                       AGENTS.md                             │
│                                                             │
│  GLOBAL CONTRACT                                            │
│  - Priority / Framework invariants                          │
│  - Do not invent                                            │
│  - Inspect first                                            │
│  - Scope                                                    │
│  - Verification                                             │
│  - Khi nào cần plan                                         │
│  - Khi nào cần review                                       │
│                                                             │
│  → Đây là "luật chung" cho mọi task                         │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │    CLASSIFY TASK     │
                 │                      │
                 │ Login = non-trivial  │
                 │ Login = auth/security│
                 │ Login = FE + BE      │
                 └──────────┬───────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                  project-context.md                         │
│                                                             │
│  PROJECT FACTS                                              │
│  - FE dùng gì?                                              │
│  - BE dùng gì?                                              │
│  - DB gì?                                                   │
│  - Auth hiện tại thế nào?                                   │
│  - Convention / architecture hiện tại                       │
│                                                             │
│  → Cho Agent biết "project này đang tồn tại như thế nào"    │
│  → Blank = UNKNOWN, không được tự bịa                       │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    rules/workflow.md                        │
│                                                             │
│  WORKFLOW RULES                                             │
│  - Task này thuộc workflow nào?                             │
│  - Có cần plan không?                                       │
│  - Có approval gate không?                                  │
│  - Khi nào được bypass?                                     │
│  - Khi nào cần review?                                      │
│                                                             │
│  Login → non-trivial                                        │
│        → auth/security                                      │
│        → PLAN REQUIRED                                      │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                     commands/plan.md                        │
│                                                             │
│  PLAN WORKFLOW                                              │
│  - Inspect requirement                                      │
│  - Xác định các phần cần thay đổi                           │
│  - Xác định implementation steps                            │
│  - Testing plan                                             │
│  - Risks                                                    │
│  - Request user approval                                    │
│                                                             │
│  → Chưa code                                                │
│  → Chỉ tạo implementation plan                              │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                    ┌───────────────────┐
                    │ Có thông tin      │
                    │ chưa rõ / unknown?│
                    └─────────┬─────────┘
                              │
                       ┌──────┴──────┐
                       │             │
                      YES            NO
                       │             │
                       ▼             │
┌────────────────────────────────┐   │
│       commands/research.md     │   │
│                                │   │
│  RESEARCH / INSPECT            │   │
│  - Tìm hiểu unknowns           │   │
│  - Inspect code/docs           │   │
│  - Xác minh assumption         │   │
│                                │   │
│  → Chỉ dùng khi cần            │   │
└───────────────┬────────────────┘   │
                │                    │
                └─────────┬──────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                     RULES ĐANG ÁP DỤNG                      │
│                                                             │
│  rules/ai.md                                                │
│  └─ AI behavior                                             │
│     - Do not invent                                         │
│     - Inspect first                                         │
│     - State assumptions                                     │
│                                                             │
│  rules/security.md                                          │
│  └─ Authentication / security                               │
│     - Credential handling                                   │
│     - Password / token safety                               │
│     - Sensitive data                                        │
│                                                             │
│  rules/quality.md                                           │
│  └─ Code quality                                            │
│     - Maintainability                                       │
│     - Project conventions                                   │
│     - Avoid unnecessary complexity                          │
│                                                             │
│  rules/ui.md                                                │
│  └─ FE / UI rules                                           │
│     - Login UI                                              │
│     - UI conventions                                        │
│                                                             │
│  rules/testing.md                                           │
│  └─ Verification / testing                                  │
│     - What must be tested                                   │
│     - How to verify                                         │
│                                                             │
│  → Đây không phải "workflow"                                │
│  → Đây là các CONSTRAINT khi làm việc                       │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                    ┌───────────────────┐
                    │ Có architectural  │
                    │ decision đáng kể? │
                    └─────────┬─────────┘
                              │
                       ┌──────┴──────┐
                       │             │
                      YES            NO
                       │             │
                       ▼             │
┌────────────────────────────────┐   │
│      agents/architect.md       │   │
│                                │   │
│  ARCHITECT                     │   │
│  - Phân tích architecture      │   │
│  - Component boundaries        │   │
│  - Data / control flow         │   │
│  - Trade-offs                  │   │
│  - Architectural risks         │   │
│                                │   │
│  → OPTIONAL                    │   │
│  → Không phải approval gate    │   │
└───────────────┬────────────────┘   │
                │                    │
                └─────────┬──────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                         PLAN                                │
│                                                             │
│  Ví dụ:                                                     │
│  1. Reuse existing AuthService                              │
│  2. Implement / complete BE login endpoint                  │
│  3. Connect FE login form                                   │
│  4. Handle auth state                                       │
│  5. Handle validation / errors                              │
│  6. Add tests                                               │
│  7. Security verification                                   │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │    USER APPROVAL     │
                 │                      │
                 │ "OK, làm đi"         │
                 └──────────┬───────────┘
                            │
                            ▼
═══════════════════════════════════════════════════════════════
                         IMPLEMENT
═══════════════════════════════════════════════════════════════

             ┌─────────────────────────────────┐
             │             FE + BE             │
             │                                 │
             │       Agent bắt đầu code        │
             └────────────────┬────────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │ RULES vẫn được áp dụng   │
                │                          │
                │ ai.md                    │
                │ security.md              │
                │ quality.md               │
                │ ui.md                    │
                └─────────────┬────────────┘
                              │
                              ▼
                    ┌───────────────────┐
                    │ Có bug / unknown  │
                    │ trong lúc làm?    │
                    └─────────┬─────────┘
                              │
                         ┌────┴────┐
                         │         │
                        YES        NO
                         │         │
                         ▼         │
              ┌──────────────────┐ │
              │ agents/debugger  │ │
              │      .md         │ │
              │                  │ │
              │ DEBUGGER         │ │
              │ - Investigate    │ │
              │ - Find root cause│ │
              │ - Fix issue      │ │
              │                  │ │
              │ → Chỉ dùng khi   │ │
              │   cần debug      │ │
              └────────┬─────────┘ │
                       │           │
                       └─────┬─────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                    rules/testing.md                         │
│                                                             │
│  TEST / VERIFY                                              │
│                                                             │
│  FE:                                                        │
│  - Login form                                               │
│  - Validation                                               │
│  - Loading / error                                          │
│  - Successful login                                         │
│                                                             │
│  BE:                                                        │
│  - Valid credentials                                        │
│  - Invalid credentials                                      │
│  - Invalid payload                                          │
│  - Auth behavior                                            │
│                                                             │
│  → rules/testing.md nói "phải verify như thế nào"           │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                     ┌──────────────┐
                     │  SELF-CHECK  │
                     │              │
                     │ Implementer  │
                     │ tự kiểm tra  │
                     └──────┬───────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ Login = auth/security│
                 │        ↓             │
                 │ Review REQUIRED      │
                 └──────────┬───────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                   commands/review.md                        │
│                                                             │
│  REVIEW WORKFLOW                                            │
│  - Xác định review scope                                    │
│  - Independent review                                       │
│  - Review findings                                          │
│                                                             │
│  → File này nói "review được thực hiện theo quy trình nào"  │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                   agents/reviewer.md                        │
│                                                             │
│  REVIEWER                                                   │
│  - Inspect implementation                                   │
│  - Check correctness                                        │
│  - Check security                                           │
│  - Check regression                                         │
│  - Check requirements                                       │
│                                                             │
│  → Reviewer KHÔNG tự code                                   │
└───────────────────────────┬─────────────────────────────────┘
                            │
                            ▼
                    ┌──────────────────┐
                    │   Issues found?  │
                    └────────┬─────────┘
                             │
                      ┌──────┴──────┐
                      │             │
                     YES            NO
                      │             │
                      ▼             ▼
          ┌──────────────────┐   ┌─────────────────┐
          │ Return to        │   │ FINAL VERIFY    │
          │ implementation   │   │                 │
          │ / debugger       │   │ Tests passed    │
          └────────┬─────────┘   │ Requirements OK │
                   │             │ Review passed   │
                   │             └────────┬────────┘
                   │                      │
                   └──────────────────────┘
                                          │
                                          ▼
                              ┌─────────────────────┐
                              │        DONE         │
                              │                     │
                              │ Login implemented   │
                              │ + verified          │
                              │ + reviewed          │
                              └─────────────────────┘



USER
 ↓
AGENTS.md
 ↓
project-context.md
 ↓
rules/workflow.md
 ↓
commands/plan.md
 ↓
research.md (nếu cần)
 ↓
security.md + ai.md + quality.md + ui.md
 ↓
architect.md (nếu cần)
 ↓
APPROVAL
 ↓
FE + BE IMPLEMENT
 ↓
debugger.md (nếu cần)
 ↓
testing.md
 ↓
SELF-CHECK
 ↓
commands/review.md
 ↓
reviewer.md
 ↓
FIX / REVIEW LOOP
 ↓
DONE