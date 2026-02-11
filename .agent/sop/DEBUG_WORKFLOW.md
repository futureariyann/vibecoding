# 🛡️ Debugging & Incident Response

## 🔬 1. Reproduction Protocol

**Goal:** Prove the bug exists before fixing it.

1.  **Test Case:** Write a failing test in `tests/repro.test.ts`.
2.  **Verify:** Run the test to confirm failure.

## 🕵️ 2. Root Cause Analysis

1.  **Logs:** Read server logs.
2.  **Trace:** Follow the data flow.
3.  **Hypothesis:** "The issue is caused by X because Y."

## 🔨 3. The Fix

1.  **Implement:** Fix the code.
2.  **Verify:** Run the repro test (it should pass now).
3.  **Cleanup:** Remove the repro test or promote it to the regression suite.
