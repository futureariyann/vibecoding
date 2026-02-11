# 🛡️ Security & Safety Guide

Vibe coding is fast, but you must stay safe. AI can sometimes suggest insecure code or accidentally share your secrets.

---

## 🔑 1. Protect Your Secrets

**Never** let the AI see your API keys, passwords, or database URLs.

-   **Rule:** Always use a `.env` file.
-   **Rule:** Add `.env` to your `.gitignore`.
-   **OpenCode Tip:** If you see the AI writing a password in a file, stop it immediately and ask it to use an environment variable.

---

## 🛡️ 2. Sanitize Inputs

AI might forget to check user input. This can lead to attacks like **SQL Injection**.

-   **Solution:** Use validation libraries like **Zod**.
-   **Example:**
    ```typescript
    // Ask the AI to always use this pattern:
    const schema = z.object({
      email: z.string().email(),
    });
    ```

---

## 📦 3. Check Dependencies

AI might "hallucinate" a library that doesn't exist or recommend an old, insecure one.

-   **Step:** Before installing a new package, check its popularity on [npm](https://www.npmjs.com).
-   **Rule:** Only use well-known libraries like `axios`, `zod`, or `lucide-react`.

---

## 🧪 4. The Verification Rule

**Trust but verify.**

1.  **Linting:** Run `npm run lint` to find obvious mistakes.
2.  **Testing:** Ask the AI to write tests for its code.
3.  **Human Review:** Always read the code before you deploy it to production.

---

## 🚫 The "Never Do" List

-   **NEVER** give the AI access to your production database credentials.
-   **NEVER** run a command the AI suggests if you don't understand what it does (e.g., `rm -rf /`).
-   **NEVER** skip code reviews for security-sensitive areas (like Auth or Payments).

---

> **Stay Safe:** Speed is good, but security is better. Always follow the **Vibe Safety Protocol**. 🛡️
