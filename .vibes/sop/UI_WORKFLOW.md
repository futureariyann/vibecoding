# 🎨 UI Engineering Workflow

## 🛠️ 1. Component Creation

**Standard:** shadcn/ui + Tailwind v4

1.  **Check:** Does the component exist in `src/components/ui`?
2.  **Scaffold:** Create `src/components/features/[feature]/[name].tsx`.
3.  **Props:** Define strict interface (No `any`).
4.  **Story:** Create `[name].stories.tsx`.

## 🎨 2. Styling Rules

-   Use `flex` and `grid` for layout.
-   Use `gap-x` and `p-x` tokens.
-   **Forbidden:** `w-[123px]` (Arbitrary values).

## ⚡️ 3. State Management

-   Use `nuqs` for URL state (search params).
-   Use `useState` for local interaction.
-   **Forbidden:** `useEffect` for data fetching.
