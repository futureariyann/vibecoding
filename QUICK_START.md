# 🚀 Quick Start: Your First Vibe Coding Project

Welcome to the future of development. This guide will help you set up your first **Vibe Coding** project in less than 30 minutes using **OpenCode**.

---

## 🛠️ Step 1: Install the Tools

To start vibe coding, you need a few basic tools:

1.  **Node.js**: The engine that runs your code. [Download here](https://nodejs.org).
2.  **Git**: To save your progress and share your code. [Download here](https://git-scm.com).
3.  **OpenCode**: Your AI Agent. 
    - Install it via terminal: `npm install -g opencode-ai`
    - Or download the desktop app from [opencode.ai](https://opencode.ai).

---

## 🏗️ Step 2: Create Your Project

Open your terminal and run these commands to start a modern web project:

```bash
# 1. Create a new Next.js project
npx create-next-app@latest my-vibe-app --typescript --tailwind --eslint

# 2. Go to the project folder
cd my-vibe-app

# 3. Initialize OpenCode
opencode /init
```

---

## 📄 Step 3: Setup Your AGENTS.md

OpenCode works best when it has clear instructions. Create a file named `AGENTS.md` in your project root and paste this:

```markdown
# AGENTS.md

## Project Goal
A simple Todo App built with Next.js and Tailwind CSS.

## Tech Stack
- Framework: Next.js 15 (App Router)
- Language: TypeScript
- Styling: Tailwind CSS
- UI: shadcn/ui

## Commands
- Install: `npm install`
- Dev: `npm run dev`
- Test: `npm run test`

## Rules
- Use functional components.
- No `any` types.
- Always use Tailwind for styling.
```

---

## ⚡️ Step 4: Your First Vibe Session

Now, let the AI build the app for you. Open your project in **OpenCode** and type:

> "Read AGENTS.md. Now, create a beautiful Todo App with a clean dark mode design. I want to be able to add, delete, and mark tasks as done."

### What happens next?
1.  OpenCode will read your rules.
2.  It will create the necessary files.
3.  It will show you the result.

---

## ✅ Step 5: The Vibe Check

Once the AI finishes, run the app:

```bash
npm run dev
```

Open `http://localhost:3000` in your browser. If it looks good, you just finished your first Vibe Coding session! 🚀

---

> **Next Step:** Read [PROMPT_ENGINEERING.md](./PROMPT_ENGINEERING.md) to learn how to talk to your AI like a pro.
