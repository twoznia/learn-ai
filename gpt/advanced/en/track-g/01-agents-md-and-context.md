# G1 — AGENTS.md & Project Context

⏱️ **15 minutes** · Track: 🅶 Codex CLI in Depth · Needs: the Codex CLI installed & signed in (see D5)

🌐 [Polski](../../pl/track-g/01-agents-md-i-kontekst.md) · [← Track index](../README.md) · [Next: Approval modes & the sandbox →](02-approval-modes-and-sandbox.md)

---

## 🧠 Theory (4 min)

In D5 you ran the Codex CLI on your ChatGPT plan. Now we make it *good* — starting with **context**.

An **AGENTS.md** file is plain Markdown that Codex **reads automatically** to learn about your project. Put your standing context there — what the project is, how to run it, conventions, do's and don'ts — and stop re-explaining it every session. (`AGENTS.md` is an open convention several coding agents share, so the same file helps other tools too.)

Context is **layered**, which is powerful:

- **Global** (`~/.codex/AGENTS.md`) — *your* preferences across all projects.
- **Project** (`AGENTS.md` in the repo root) — facts about this project.
- **Sub-folder** (`AGENTS.md` deeper in the tree) — details for one part.

Codex merges them, most-specific last.

---

## 🛠️ Practice (10 min)

### Step 1 — Create a project AGENTS.md

In a real project folder, create the file:

```powershell
notepad AGENTS.md
```

A good project AGENTS.md includes:

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

> Tip: you can ask Codex to draft it — "Look at this project and write an AGENTS.md describing what it is, how to run it, and its conventions." Review before saving.

### Step 2 — Set your global preferences

Create a global context file for habits that follow *you* everywhere:

```powershell
notepad $HOME\.codex\AGENTS.md
```

```markdown
# My preferences
- I'm on Windows; give PowerShell commands.
- Be concise; lead with the answer.
- Explain risky changes before making them.
```

### Step 3 — Confirm it's being used

Start Codex in the project and ask something that relies on the context:

```text
How do I run and test this project? Answer only from the project's own instructions.
```

If it echoes your AGENTS.md, the context is loading.

### Step 4 — Keep it lean and current

- Put facts Codex can't guess (how to run, conventions, no-go zones).
- Remove anything stale — a wrong AGENTS.md misleads every session.
- Don't paste secrets into it; it's shared with anyone who has the repo.

### Step 5 — Put facts where they belong

- Project facts → project `AGENTS.md`.
- Your personal habits → global `~/.codex/AGENTS.md`.
- One part's quirks → an `AGENTS.md` in that sub-folder.

---

## 🧩 Where context goes

| Fact | Put it in |
|------|-----------|
| How to run/test this project | Project `AGENTS.md` |
| Project conventions & no-go zones | Project `AGENTS.md` |
| "I'm on Windows, be concise" | Global `~/.codex/AGENTS.md` |
| One module's special rules | Sub-folder `AGENTS.md` |

---

## ✅ Checkpoint

- [ ] You created a project `AGENTS.md` with real context.
- [ ] You created a global `~/.codex/AGENTS.md` with your preferences.
- [ ] Codex answered a question using your project context.
- [ ] You can explain the global → project → sub-folder layering.

---

## 🎯 Homework

Write a real AGENTS.md for a project you care about (what it is, how to run it, conventions, no-go zones) and a global one with your personal habits. Start a session and confirm Codex follows them.

---

## 💡 Key takeaways

- **AGENTS.md** is auto-loaded **project context** — put standing facts there and stop re-explaining (personal habits go in `~/.codex/AGENTS.md`).
- It's **layered**: global (you) → project → sub-folder, merged most-specific last.
- Keep it **lean, current, and secret-free** — a wrong AGENTS.md misleads every session.

🌐 [Polski](../../pl/track-g/01-agents-md-i-kontekst.md) · [← Track index](../README.md) · [Next: Approval modes & the sandbox →](02-approval-modes-and-sandbox.md)
