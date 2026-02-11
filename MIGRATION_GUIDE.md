# 🏗️ Migrating to Vibe Coding

Moving an existing project to a vibe coding workflow doesn't happen overnight. It's a journey from **Manual Implementation** to **Intent Management**.

---

## 🔍 1. The Assessment

Before you start, ask these questions about your codebase:
-   **Is it typed?** If you use JavaScript, migrate to TypeScript first. AI needs types to understand "shapes."
-   **Is it modular?** If you have 2000-line files, the AI will hallucinate.
-   **Are there tests?** You need a safety net to know if the AI broke something.

---

## 🪜 2. The Gradual Migration Strategy

### Step 1: Document the Vibe
Create your `AGENT.md` and `SKILL.md` based on your **current** stack. Don't try to change the stack yet.

### Step 2: Documentation First
Ask the AI to read your core files and generate READMEs or JSDoc comments. This "trains" the AI on your specific patterns.

### Step 3: Start with New Features
Build all *new* features using the Vibe Coding loop. Leave the old code alone for now.

### Step 4: The "Bite-Sized" Refactor
Pick one messy component. Ask the AI: "Read this component and suggest a plan to split it into three smaller files. Do not change the logic yet."

---

## 🛠️ 3. Refactoring Patterns

| Pattern | Goal | AI Prompt Example |
| :--- | :--- | :--- |
| **Logic Extraction** | Move business logic out of UI files. | "Move the form validation logic from `Signup.tsx` into a new `useSignup.ts` hook." |
| **Type Hardening** | Replace `any` with strict types. | "Read `api.ts`. Replace all `any` types with interfaces based on the actual data returned." |
| **Boilerplate Kill** | Move repetitive code to helpers. | "I see the same error handling in 5 files. Create a shared `errorHandler` utility and update the files." |

---

## 📖 4. Case Study: Legacy React to Modern Next.js

**Old State:** React Class Components, Redux, Inline CSS.
**Goal:** Next.js Server Components, Tailwind, URL state.

**The Workflow:**
1.  **Read Class:** Agent reads `UserList.class.js`.
2.  **Define Interface:** Agent creates `UserList.types.ts`.
3.  **Build Functional:** Agent writes `UserList.tsx` using Tailwind.
4.  **Verify:** Run them side-by-side to ensure UI parity.

---

> **Pro Tip:** Don't migrate everything at once. **Migrate the intent, then the syntax.** 🚀
