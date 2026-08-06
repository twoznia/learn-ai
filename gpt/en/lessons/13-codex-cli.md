# Lesson 13 — Codex CLI in the Terminal

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: Windows, a ChatGPT account or API key

🌐 [Polski](../../pl/lessons/13-codex-cli.md) · [← Prev](12-vscode-ai.md) · [Course home](../README.md) · [Next: Mini project →](14-mini-project.md)

---

## 🧠 Theory (3 min)

**Codex CLI** is OpenAI's open-source AI coding assistant that runs in your **terminal**. Unlike a chat window, it can:

- **read your project files**,
- **write and edit code**,
- **run commands** (with your permission),
- work through multi-step tasks on its own.

Think of it as a junior developer at your keyboard — you describe what you want in plain English, and it does the work, asking before anything risky.

It's installed via **npm**, which comes with **Node.js**. So we install Node.js first.

---

## 🛠️ Practice (7 min)

### Step 1 — Install Node.js

In **PowerShell**:

```powershell
winget install --id OpenJS.NodeJS.LTS -e
```

**Close and reopen PowerShell**, then verify:

```powershell
node --version
npm --version
```

Both should print version numbers (e.g. `v22.x` and `10.x`). ✅

### Step 2 — Install Codex CLI

```powershell
npm install -g @openai/codex
```

The `-g` means "install globally" so you can run it from any folder.

Verify:

```powershell
codex --version
```

### Step 3 — Start it in your project

```powershell
cd $HOME\learn-ai-gpt
codex
```

The first time, it will guide you through **signing in** — you can sign in with your **ChatGPT account** or use your `OPENAI_API_KEY`. Follow the prompts.

### Step 4 — Give it a task

Once Codex is running, just type what you want:

```text
Look at the files in this folder and tell me what each one does.
```

Then something that changes files:

```text
Create a file called todo.py that lets me add tasks to a list and print them.
```

It will show you the file it wants to create and ask you to **approve**. Say yes, then run it:

```powershell
python todo.py
```

### Step 5 — Iterate

```text
Add the ability to mark a task as done.
```
```text
Save the tasks to a file so they're remembered next time.
```

It edits the code for you. The core loop of AI-assisted coding: **describe → review → approve → run**.

---

## 🔑 Handy things to know

| Want to… | Do this |
|----------|---------|
| Start Codex | `codex` (inside your project folder) |
| Exit | Press Ctrl+C twice (or type the quit command shown) |
| See help | Type `/help` |
| Undo a change | Ask it: "undo your last change" |
| Stay safe | Always **read** what it proposes before approving |

> **Golden safety rule:** Codex asks before editing files or running commands. Read the preview. If unsure, ask it *"explain what this command does and whether it's safe."*

---

## ✅ Checkpoint

- [ ] `node --version` and `npm --version` work.
- [ ] `codex --version` works.
- [ ] Codex created a file you approved.
- [ ] You asked for an improvement and it edited the code.

---

## 🎯 Homework

Ask Codex: *"Add comments to todo.py explaining each part for a beginner, then give me a one-paragraph summary of how the program works."* Read the summary — a great way to learn to code.

---

## 💡 Key takeaways

- Codex CLI = OpenAI's AI coding assistant in the terminal; install via `npm install -g @openai/codex`.
- It needs **Node.js** (install first with winget).
- Run `codex` inside a project folder; sign in with ChatGPT or an API key.
- It **asks before** editing files or running commands — always review.

🌐 [Polski](../../pl/lessons/13-codex-cli.md) · [← Prev](12-vscode-ai.md) · [Course home](../README.md) · [Next: Mini project →](14-mini-project.md)
