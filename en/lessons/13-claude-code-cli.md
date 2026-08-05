# Lesson 13 — Claude Code CLI in the Terminal

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: Windows, an account or API key

[← Prev](12-vscode-setup.md) · [Course home](../README.md) · [Next: Mini project →](14-mini-project.md)

---

## 🧠 Theory (3 min)

**Claude Code** is Anthropic's AI coding assistant that runs in your **terminal**. Unlike a chat window, it can:

- **read your project files**,
- **write and edit code**,
- **run commands** (with your permission),
- work through multi-step tasks on its own.

Think of it as a junior developer sitting at your keyboard — you describe what you want in plain English, and it does the work, asking before anything risky.

It's installed via **npm**, the package manager that comes with **Node.js**. So we install Node.js first.

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

### Step 2 — Install Claude Code

```powershell
npm install -g @anthropic-ai/claude-code
```

The `-g` means "install globally" so you can run it from any folder. This takes a minute.

Verify:

```powershell
claude --version
```

### Step 3 — Start it in your project

```powershell
cd $HOME\learn-ai-claude
claude
```

The first time, it will guide you through **signing in** (your Claude account or API key). Follow the prompts.

### Step 4 — Give it a task

Once Claude Code is running, just type what you want. Try:

```text
Look at the files in this folder and tell me what each one does.
```

Then try something that changes files:

```text
Create a file called todo.py that lets me add tasks to a list and print them.
```

It will show you the file it wants to create and ask you to **approve**. Say yes, then run it:

```powershell
python todo.py
```

### Step 5 — Iterate

Ask for improvements in plain English:

```text
Add the ability to mark a task as done.
```

```text
Save the tasks to a file so they're remembered next time.
```

It edits the code for you. This is the core loop of AI-assisted coding: **describe → review → approve → run**.

---

## 🔑 Handy things to know

| Want to… | Do this |
|----------|---------|
| Start Claude Code | `claude` (inside your project folder) |
| Exit | Type `/exit` or press Ctrl+C twice |
| See commands | Type `/help` |
| Undo a change | Ask it: "undo your last change" |
| Stay safe | Always **read** what it proposes before approving |

> **Golden safety rule:** Claude Code asks before editing files or running commands. Read the preview. If you don't understand a step, ask it *"explain what this command does and whether it's safe."*

---

## ✅ Checkpoint

- [ ] `node --version` and `npm --version` work.
- [ ] `claude --version` works.
- [ ] Claude Code created a file you approved.
- [ ] You asked for an improvement and it edited the code.

---

## 🎯 Homework

Ask Claude Code: *"Add comments to todo.py explaining each part for a beginner, then give me a one-paragraph summary of how the program works."* Read the summary — that's a great way to learn to code.

---

## 💡 Key takeaways

- Claude Code = AI coding assistant in the terminal; installed via `npm install -g @anthropic-ai/claude-code`.
- It needs **Node.js** (install first with winget).
- Run `claude` inside a project folder, then describe tasks in plain English.
- It **asks before** editing files or running commands — always review.

[← Prev](12-vscode-setup.md) · [Course home](../README.md) · [Next: Mini project →](14-mini-project.md)
