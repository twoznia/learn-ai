# G1 — GEMINI.md & Context (Project Memory)

⏱️ **15 minutes** · Track: 🅶 Gemini CLI in Depth · Needs: the Gemini CLI installed & signed in (see D5)

🌐 [Polski](../../pl/track-g/01-gemini-md-i-kontekst.md) · [← Track index](../README.md) · [Next: Custom commands →](02-custom-commands.md)

---

## 🧠 Theory (4 min)

In D5 you ran the Gemini CLI on your account. Now we make it *good* — starting with **context files**.

A **GEMINI.md** file is plain Markdown the CLI **reads automatically** to learn about your project. Put your standing context there — what the project is, how to run it, conventions, do's and don'ts — and stop re-explaining it every session.

Context is **hierarchical**, which is powerful:

- **Global** (`~/.gemini/GEMINI.md`) — *your* preferences across all projects.
- **Project** (`GEMINI.md` in the project root) — facts about this project.
- **Sub-folder** (`GEMINI.md` deeper in the tree) — details for one part.

The CLI merges them, most-specific last. You manage them with the `/memory` command.

---

## 🛠️ Practice (10 min)

### Step 1 — Generate a project GEMINI.md

In a real project folder, start the CLI and run:

```text
/init
```

The CLI scans the project and writes a **GEMINI.md** describing it. Open the file — it's just Markdown you can edit.

### Step 2 — Make it yours

Add the things you'd otherwise repeat. A good project GEMINI.md includes:

```markdown
# Project: <name>

## What this is
A short description and its goal.

## How to run
- Install: <command>
- Run: <command>
- Test: <command>

## Conventions
- Language/style rules to follow.
- Folders and what lives where.

## Do / Don't
- Do: keep changes small and explained.
- Don't: touch <x>, or add dependencies without asking.
```

Now every session starts with this loaded — no re-explaining.

### Step 3 — Set your global preferences

Create a global context file for habits that follow *you* everywhere:

```powershell
notepad $HOME\.gemini\GEMINI.md
```

```markdown
# My preferences
- I'm on Windows; give PowerShell commands.
- Be concise; lead with the answer.
- Explain risky changes before making them.
```

### Step 4 — Inspect what's loaded

```text
/memory show
```

This shows the combined context the CLI is using. If you edit a GEMINI.md while running:

```text
/memory refresh
```

### Step 5 — Add a quick note without editing files

```text
/memory add Always prefer the built-in libraries over new dependencies.
```

Handy for a fact you want remembered mid-session.

### Step 6 — Put facts where they belong

- Project facts → project `GEMINI.md`.
- Your personal habits → global `~/.gemini/GEMINI.md`.
- One part's quirks → a `GEMINI.md` in that sub-folder.

---

## 🧩 Where context goes

| Fact | Put it in |
|------|-----------|
| How to run/test this project | Project `GEMINI.md` |
| Project conventions & no-go zones | Project `GEMINI.md` |
| "I'm on Windows, be concise" | Global `~/.gemini/GEMINI.md` |
| One module's special rules | Sub-folder `GEMINI.md` |
| A mid-session reminder | `/memory add` |

---

## ✅ Checkpoint

- [ ] You generated a `GEMINI.md` with `/init` and edited it to add real context.
- [ ] You created a global `~/.gemini/GEMINI.md` with your preferences.
- [ ] You viewed the combined context with `/memory show`.
- [ ] You can explain the global → project → sub-folder hierarchy.

---

## 🎯 Homework

Write a real project GEMINI.md (what it is, how to run, conventions, no-go zones) and a global one with your personal habits. Start a session and confirm with `/memory show` that both are loaded.

---

## 💡 Key takeaways

- **GEMINI.md** is auto-loaded **context/memory** — put standing facts there and stop re-explaining.
- Context is **hierarchical**: global (you) → project → sub-folder, merged most-specific last.
- Manage it with **`/memory show`, `/memory refresh`, `/memory add`**.

🌐 [Polski](../../pl/track-g/01-gemini-md-i-kontekst.md) · [← Track index](../README.md) · [Next: Custom commands →](02-custom-commands.md)
