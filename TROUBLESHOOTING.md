# 🔍 Troubleshooting & Optimization

Vibe coding isn't magic. Sometimes the AI gets stuck, loops, or writes "creative" but broken code. Here is how to fix the vibe.

---

## 👻 1. AI Hallucination Recovery

### Detecting the "Hallucination"
-   AI suggests a library that doesn't exist.
-   AI uses a function from a different version of your stack.
-   AI keeps making the same mistake after you've corrected it.

### The Recovery Protocol
1.  **Stop the Loop:** If the AI fails twice, do not try a third time.
2.  **Clean the Context:** Type `/clear` or start a new session.
3.  **Feed the Source:** Go find the actual documentation or code snippet. Paste it and say: "This is the correct way to do it. Use this pattern."

---

## 🔧 2. Common Errors & Solutions

### "I don't have enough context"
-   **Cause:** You haven't opened the relevant files.
-   **Fix:** Specifically tell it: "Read `schema.ts` and `auth.ts` first."

### "This change might break existing code"
-   **Cause:** AI is being too conservative or sees a conflict.
-   **Fix:** Ask for a **Plan Mode** analysis first. "Analyze the impact of this change and list all affected files."

### Infinite Generation Loop
-   **Cause:** The task is too big or the logic is circular.
-   **Fix:** Break the prompt into 3 smaller tasks.

---

## ⚡️ 3. Token & Performance Optimization

AI performance drops as the chat history grows.

-   **Short Sessions:** One feature = One chat session.
-   **Atomic Prompts:** Instead of "Build the whole page," say "Build the Header component."
-   **Use @-Mentions:** Use `@filename` to give the AI only the specific files it needs.

---

## 🛑 4. When to Go Manual

Vibe coding is for **90% of the work**. The last 10% sometimes needs a human touch:

-   **Complex Math/Algorithms:** AI is bad at complex math logic.
-   **Novel Architectures:** If you're building something that has never been done before.
-   **Performance-Critical Code:** Tight loops or low-level memory management.

---

> **The Golden Rule:** If you spend more than 10 minutes trying to prompt a fix, **fix it manually**, show the AI the result, and move on. 🚀
