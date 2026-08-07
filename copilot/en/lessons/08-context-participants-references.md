# Lesson 08 — Giving Copilot the Right Context

⏱️ **11 minutes** · Level: Intermediate · Needs: VS Code + Copilot, a multi-file project

🌐 [Polski](../../pl/lessons/08-kontekst-uczestnicy-referencje.md) · [← Prev](07-custom-instructions.md) · [Course home](../README.md) · [Next: Git & GitHub fundamentals →](09-git-and-github-fundamentals.md)

---

## 🧠 Theory (4 min)

Copilot answers best when it's looking at the **right context**. VS Code gives you precise ways to point at it:

- **@ participants** — specialists you address, like **@workspace** (your whole project), **@vscode** (the editor itself), **@terminal** (shell/commands). They pull in relevant context.
- **# references** — attach a specific **#file**, selection, symbol, or other resource so Copilot uses exactly that.
- **The working set** — in Edit/Agent mode, the files you've added.

Instead of hoping Copilot guesses, you **tell it where to look**. That's the difference between a generic answer and one grounded in your codebase.

> Participant and reference names (e.g. `@workspace`, `#file`) vary by version. Type **@** or **#** in the chat to see what's available in yours.

---

## 🛠️ Practice (7 min)

### Step 1 — Ask across the whole project

```text
@workspace Where is the greeting text defined, and which files would I change
to add a new language?
```

`@workspace` searches your project and answers with **real file names**.

### Step 2 — Reference a specific file

Type `#` and pick a file (or `#file`):

```text
Using #greetings.py, add a "fr" (French) greeting consistent with the others.
```

Now Copilot works from *that* file specifically.

### Step 3 — Ask the editor for help

```text
@vscode How do I change my keyboard shortcut for accepting a Copilot suggestion?
```

`@vscode` knows VS Code's settings and commands.

### Step 4 — Get command help

```text
@terminal How do I find and kill the process using port 5000 on Windows?
```

`@terminal` is great for shell commands you don't remember.

### Step 5 — Attach a selection

Select a few lines, open inline chat (**Ctrl+I**), and ask about *just that* — the selection is the context.

### Step 6 — Combine for precision

```text
@workspace #app.py Add a --language command-line flag and pass it through to
get_greeting. Show diffs for every file you change.
```

Specific participant + specific file + a clear ask = a grounded, reviewable answer.

---

## 🧩 Context tools

| Tool | Use it to |
|------|-----------|
| **@workspace** | Ask about / change your whole project |
| **@vscode** | Editor settings, shortcuts, commands |
| **@terminal** | Shell/command help |
| **#file / #selection** | Point at exact files or code |
| Working set (Edit/Agent) | Scope a multi-file change |

> The more precisely you scope context, the better — and the fewer surprises when you review the diff.

---

## ✅ Checkpoint

- [ ] You used **@workspace** and got answers with real file names.
- [ ] You referenced a specific file with **#**.
- [ ] You used **@vscode** and **@terminal** for editor/shell help.
- [ ] You combined a participant + a file reference in one ask.

---

## 🎯 Homework

On a multi-file project, use `@workspace` to ask "how does data flow through this app?" Then make one change scoped with a `#file` reference and review the diff. Notice how scoping context improves accuracy.

---

## 💡 Key takeaways

- **@participants** (`@workspace`, `@vscode`, `@terminal`) bring in the right kind of context.
- **# references** point Copilot at exact files, selections, or symbols.
- Precisely scoping context turns generic answers into ones grounded in **your** code.

🌐 [Polski](../../pl/lessons/08-kontekst-uczestnicy-referencje.md) · [← Prev](07-custom-instructions.md) · [Course home](../README.md) · [Next: Git & GitHub fundamentals →](09-git-and-github-fundamentals.md)
