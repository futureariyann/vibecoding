# 🧠 Project Status & Memory

> **Note to Agent:** Read this file at the start of every session. Update it before you stop.

## 📍 Current Context

-   **Last Action:** [Date/Time] Refactored the `AuthButton` component to use the new `useSession` hook.
-   **Current Focus:** Implementing the "Dark Mode" toggle across the dashboard.
-   **Active Branch:** `feature/dark-mode-v2`

## 🚧 Known Issues (The "Fix Later" Pile)

-   [ ] The `UserAvatar` component flickers on initial load (hydration mismatch).
-   [ ] Database migration `0014_add_teams` failed on staging (needs manual rollback).

## 📋 Next Steps (The Plan)

1.  [x] Install `next-themes`.
2.  [ ] Create `ThemeToggle.tsx` in `@/components/layout`.
3.  [ ] Add `suppressHydrationWarning` to `layout.tsx`.
4.  [ ] Test toggle state persistence in local storage.

## 🧠 Architecture Decisions (Why We Did This)

-   **Why `next-themes`?** Native support for Tailwind v4 `dark:` variant without FOUC.
-   **Why Hono?** Shared types between FE and BE prevent 40% of runtime errors.
