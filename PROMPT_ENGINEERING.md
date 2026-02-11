# 🧠 Prompt Engineering for Vibe Coders

Talking to an AI agent like **OpenCode** is different from using a chat bot. You are the **Conductor**, and the AI is your **Orchestra**.

---

## 🌟 The Golden Rules of Prompting

### 1. Context is King
Never say "Fix the bug." 
Say: "The button in `@src/components/Button.tsx` is not changing color on hover. Check the Tailwind classes."

### 2. Behavior over Implementation
Don't tell the AI *how* to code. Tell it *what* the user should see.
- **Bad:** "Use a div with flex and justify-center."
- **Good:** "Make the login form appear centered on the screen with a modern look."

### 3. Step-by-Step (The Plan)
For big tasks, always ask for a plan first.
- **Prompt:** "I want to add user authentication. Don't code yet. Give me a step-by-step plan in `plan.md` first."

---

## 📝 Prompt Templates

### Template 1: New Feature
```markdown
I want to add [FEATURE NAME].

1. Read [RELEVANT FILES] to understand our patterns.
2. Create a plan for the implementation.
3. Once I approve, build the feature.
4. Use [SPECIFIC LIBRARY] for this task.
```

### Template 2: Bug Fix
```markdown
Fix the bug where [ISSUE DESCRIPTION].

Steps to see the bug:
1. Click [X]
2. Observe [Y]

Please find the root cause, write a test to prove it, and fix it.
```

### Template 3: Refactoring
```markdown
Refactor [FILE/COMPONENT] to make it more readable.

Requirements:
- Do not change how it works.
- Split large functions into smaller ones.
- All existing tests must pass.
```

---

## 🛡️ The "Vibe Check" Workflow

After the AI writes code, always follow this loop:

1.  **Read:** Look at the code changes. Does it look right?
2.  **Verify:** Run `npm run dev` or `npm test`.
3.  **Refine:** If something is off, don't fix it yourself. Tell the AI: "The design is too crowded. Add more padding between items."

---

> **Tip:** Keep your prompts short and specific. One feature per prompt is the best way to avoid mistakes. 🚀
