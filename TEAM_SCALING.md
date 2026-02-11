# 👥 Vibe Coding for Teams

Scaling vibe coding to a team requires more than just sharing a repo. It requires a **Control Plane** — a corporate-like structure where everyone (humans and AI) knows their role.

---

## 🏢 1. The Corporate Hierarchy

For large-scale projects, we structure our context files like a company:

-   **CEO (`AGENT.md`)**: The main "Router". It sets the mission and directs the AI to specific SOPs.
-   **Managers (`.vibes/control/`)**: Specialized rules for Security, UI, and Backend.
-   **Workers (`.vibes/sop/`)**: Step-by-step Standard Operating Procedures for specific tasks.
-   **Archive (`.vibes/memory/`)**: Immutable facts, tech stack decisions, and past lessons.

---

## 🌿 2. Git Workflow with AI

AI can be messy with commits. Follow this protocol to keep your history clean:

1.  **Isolated Branches:** One feature = one branch. Never let the AI build two things at once in the same branch.
2.  **Conventional Commits:** Enforce the use of `feat:`, `fix:`, and `refactor:`.
3.  **The "Check then Commit" Rule:** Never let the AI auto-commit without your approval. Always run a `git diff` first.

---

## 🤝 3. Collaboration Patterns

### Shared vs. Personal Rules
-   **`AGENT.md`**: Should be committed to Git. This contains the "Team Rules".
-   **`.vibes/local.md`**: (Optional) Put your personal shortcuts here and add it to `.gitignore`.

### Code Review Checklist for AI Code
When reviewing an AI-generated PR, look for:
-   **Ghost Dependencies:** Did the AI add a library without updating `package.json`?
-   **Zombie Code:** Are there unused functions left behind after a refactor?
-   **Context Leak:** Did the AI accidentally include local paths or secrets?

---

## 📈 4. Scaling Architecture

Loosely coupled systems work best with AI.
-   **Small Files:** Aim for <200 lines. AI gets confused by giant files.
-   **Strict Interfaces:** Use TypeScript `interface` for every component. This gives the AI a "contract" to follow.
-   **Feature Folders:** Keep logic, types, and components for one feature in a single folder.

---

> **Key Takeaway:** In a team, you are no longer just a coder. You are an **Engineer Manager** for your AI agents. 🚀
