# ⚡️ Tech Stack & Skills (v2.0 Maximized)

## 📦 Core Stack (2026 Standard)

-   **Runtime:** Node.js (LTS) via **npm**
-   **Framework:** Next.js 16 (App Router, Server Actions)
-   **Language:** TypeScript 5.x (Strict Mode)
-   **Database:** PostgreSQL 17 (Neon/Supabase)
-   **ORM:** Drizzle ORM (Schema-First)
-   **Auth:** Better Auth v2

## 🎨 Frontend Mastery

-   **Styling:** Tailwind CSS v4 (Use `@theme` variables, no `tailwind.config.js`)
-   **Components:** shadcn/ui (Radix Primitives)
-   **Icons:** `lucide-react`
-   **State:**
    1.  **URL State:** `nuqs` (Preferred for search/filters)
    2.  **Server State:** `TanStack Query` (For async data)
    3.  **Global Client:** `zustand` (Only if absolutely necessary)
-   **Forms:** `react-hook-form` + `zod` resolver

## 🧪 Testing & Quality

-   **Unit:** `vitest` (Co-located with files: `utils/math.ts` -> `utils/math.test.ts`)
-   **E2E:** `playwright` (In `/e2e` directory)
-   **Linting:** `eslint` + `prettier` (Run on save)

## 📂 Directory Structure Enforcement

Enforce this structure to prevent "spaghetti code":

```typescript
/src
  /app              # Next.js App Router (Pages & Layouts ONLY)
    /(auth)         # Route Groups (Login, Register)
    /dashboard      # Protected Routes
  /components
    /ui             # shadcn/ui primitives (Button, Input)
    /features       # Domain-specific components (AuthForm, UserCard)
    /layout         # Sidebar, Navbar, Footer
  /lib
    db.ts           # Drizzle Client
    utils.ts        # cn() helper
  /server
    /actions        # Server Actions (use 'use server')
    /db             # Database Schema & Migrations
  /hooks            # Custom React Hooks
  /types            # Global TypeScript Definitions
```

## 🚫 Banned Patterns (Anti-Vibes)

1.  **No `useEffect` for Data Fetching:** Use Server Components or TanStack Query.
2.  **No Default Exports:** Use named exports (`export const Button = ...`) for better refactoring.
3.  **No Inline Styles:** Use Tailwind classes.
4.  **No Relative Imports:** Use aliases (`@/components/ui/button`).
5.  **No `console.log` in Production:** Use a proper logger or `console.error` for caught exceptions.

## 📝 Code Snippet Standards

### API Route (Hono/Next.js)

```typescript
import { z } from "zod";
import { db } from "@/lib/db";

const schema = z.object({ id: z.string() });

export async function POST(req: Request) {
  const body = await req.json();
  const parsed = schema.safeParse(body);
  
  if (!parsed.success) {
    return Response.json({ error: "Invalid input" }, { status: 400 });
  }

  // ... implementation
}
```

### Server Action

```typescript
"use server";

import { revalidatePath } from "next/cache";
import { db } from "@/lib/db";

export async function createItem(formData: FormData) {
  // Validate
  // Mutate
  // Revalidate
}
```
