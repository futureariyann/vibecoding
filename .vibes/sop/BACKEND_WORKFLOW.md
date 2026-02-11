# 🛠️ Backend Engineering Workflow

## ⚡️ 1. API Route Creation

**Standard:** Hono / Next.js Route Handlers

1.  **Validator:** Define Zod schema first.
2.  **Handler:** Implement logic.
3.  **Error Handling:** Use `try/catch` and return standard error response.

## 🗄️ 2. Database Changes

**Standard:** Drizzle ORM

1.  **Edit:** Modify `schema.ts`.
2.  **Generate:** `npm run db:generate`.
3.  **Verify:** Check SQL output.
4.  **Migrate:** `npm run db:migrate` (Dev only).

## 🛡️ 3. Security

-   **Auth:** Check `session` before any action.
-   **Sanitization:** Zod handles this automatically.
