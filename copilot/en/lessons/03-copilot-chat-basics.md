# Lesson 03 — Copilot Chat Basics

⏱️ **12 minutes** · Level: Beginner · Needs: VS Code + Copilot (Lesson 2)

🌐 [Polski](../../pl/lessons/03-podstawy-copilot-chat.md) · [← Prev](02-setup-vscode-and-copilot.md) · [Course home](../README.md) · [Next: Prompting Copilot well →](04-prompting-copilot-well.md)

---

## 🧠 Theory (3 min)

Completions finish your lines. **Copilot Chat** lets you *talk* to Copilot about your code — ask questions, request changes, generate tests, and understand errors. Two ways to use it:

- **Chat view** — a side panel for a back-and-forth conversation about your project.
- **Inline chat** (**Ctrl+I**) — a small box right in the file, perfect for "change this function."

Chat understands **your open files and project**, so answers are about *your* code — not generic. And it has handy **slash commands** like `/explain`, `/fix`, and `/tests` that package common requests.

---

## 🛠️ Practice (8 min)

### Step 1 — Open the Chat view

Click the **Copilot Chat** icon in the left/side bar (or **Ctrl+Alt+I**). A chat panel opens.

### Step 2 — Ask about your code

Open `demo.py` from Lesson 2, then in chat:

```text
Explain what fibonacci(n) does, step by step, for a beginner.
```

Notice the answer refers to *your actual function*.

### Step 3 — Use slash commands

In the chat box, type `/` to see commands. Try:

```text
/explain
```
```text
/tests
```

- **/explain** — explains the current selection/file.
- **/tests** — generates unit tests for it.
- **/fix** — proposes a fix for a problem.

### Step 4 — Inline chat for a quick edit

1. Select the `fibonacci` function.
2. Press **Ctrl+I** and type:

```text
Add input validation: raise a ValueError if n is negative.
```

3. Copilot shows a **diff**. Click **Accept** to apply, or **Discard**.

Inline chat is the fastest way to change the code right in front of you.

### Step 5 — Fix an error with Copilot

Break something on purpose (delete a colon), run the file, then:
1. Select the error in the terminal, or open the file.
2. Ask in chat: `/fix` or "Why does this error happen and how do I fix it?"

### Step 6 — Pick a model (optional)

Some setups let you choose the **model** from a dropdown in the chat box. A more capable model helps on hard problems; a faster one is fine for simple asks. Availability varies by plan.

---

## 🧩 Chat commands to know

| Command | Does |
|---------|------|
| `/explain` | Explains selected code or the file |
| `/fix` | Proposes a fix for an error/problem |
| `/tests` | Generates tests for the selection |
| `/doc` | Adds documentation/comments |
| Inline chat (**Ctrl+I**) | Edit the code in place, as a diff |

> Exact commands vary by version — type `/` in the chat to see what's available now.

---

## ✅ Checkpoint

- [ ] You opened the Chat view and asked about your own code.
- [ ] You ran `/explain` and `/tests`.
- [ ] You used inline chat (**Ctrl+I**) and accepted a diff.
- [ ] You fixed an error with `/fix` or a chat question.

---

## 🎯 Homework

Write a small buggy script (e.g. a loop with an off-by-one error). Use **/fix** to correct it, **/tests** to generate tests, and **/explain** to understand the fix. Keep the file — you'll reuse it.

---

## 💡 Key takeaways

- **Copilot Chat** talks about *your* code — via the **Chat view** and **inline chat (Ctrl+I)**.
- **Slash commands** (`/explain`, `/fix`, `/tests`, `/doc`) package common requests.
- Inline chat shows changes as a **diff** you accept or discard — you stay in control.

🌐 [Polski](../../pl/lessons/03-podstawy-copilot-chat.md) · [← Prev](02-setup-vscode-and-copilot.md) · [Course home](../README.md) · [Next: Prompting Copilot well →](04-prompting-copilot-well.md)
