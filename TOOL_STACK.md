# 🛠️ The 2026 AI Tool Stack

In 2026, the choice of tool determines your velocity. Here is a comparison of the top AI coding tools and how to set them up.

---

## 📊 Comparison Matrix

| Tool | Best For | Interface | Core Strength |
| :--- | :--- | :--- | :--- |
| **OpenCode** | Open Source / Flexibilty | TUI / App / IDE | Multi-agent teams & MCP support. |
| **Cursor** | High-Velocity Prototyping | Integrated IDE | The "Composer" mode is best-in-class for UI. |
| **Claude Code** | Terminal Power Users | CLI | Extremely low hallucination rate. |
| **GitHub Copilot** | Enterprise / Stable | IDE Extension | Deep integration with GitHub Actions & PRs. |

---

## ⚙️ 1. OpenCode Setup (Recommended)

OpenCode is the most flexible tool for **Vibe Coding**.

1.  **Install:** `npm install -g opencode-ai`
2.  **Config:** Open `opencode.json` in your project root.
3.  **Load AGENTS.md:** Add `"instructions": ["AGENTS.md"]` to the config.
4.  **MCPs:** Add your database or search MCPs to give the AI real-world access.

---

## ⚙️ 2. Cursor Setup

Cursor is an AI-native fork of VS Code.

1.  **Download:** [cursor.sh](https://cursor.com).
2.  **Rules:** Create a `.cursorrules` file (or use `AGENTS.md`).
3.  **Indexing:** Ensure your project is fully indexed (Settings > Features > Indexing).
4.  **Composer:** Press `Cmd+I` to start a multi-file vibe session.

---

## ⚙️ 3. Claude Code Setup

The new terminal agent from Anthropic.

1.  **Install:** `npm install -g @anthropic-ai/claude-code`
2.  **Auth:** `claude auth`
3.  **Run:** Type `claude` in your project folder.
4.  **SOPs:** Tell it to "Always read `CLAUDE.md`" (our equivalent to `AGENT.md`).

---

## 🧠 Which one should you choose?

-   **Solo Dev / UI Focus:** Use **Cursor**.
-   **Backend / Team Focus:** Use **OpenCode**.
-   **Scripting / Terminal:** Use **Claude Code**.
-   **Corporate Security:** Use **GitHub Copilot**.

---

> **Vibe Tip:** All these tools support the **AGENTS.md** standard. Write your rules once, use them everywhere. 🚀
