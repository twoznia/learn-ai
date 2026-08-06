# G1 — CLAUDE.md & Plan Mode

⏱️ **15 minutes** · Track: 🅶 Claude Code in Depth · Needs: Claude Code installed & logged in (see D5)

🌐 [Polski](../../pl/track-g/01-claude-md-i-tryb-planowania.md) · [← Track index](../README.md) · [Next: Slash commands →](02-slash-commands.md)

---

## 🧠 Theory (4 min)

In D5 you ran Claude Code on your subscription. Now we make it *good* — starting with two habits that separate a frustrating session from a great one:

- **CLAUDE.md — project memory.** A plain Markdown file in your project that Claude Code **reads automatically** every session. Put your standing context there — what the project is, how to run it, conventions, do's and don'ts — and stop re-explaining it in every chat.
- **Plan mode — think before touching.** A mode where Claude **researches and proposes a plan first**, and doesn't edit anything until you approve. Perfect for anything non-trivial: you review the approach before code changes.

Together: Claude that **knows your project** and **plans before acting**.

---

## 🛠️ Practice (10 min)

### Step 1 — Generate a CLAUDE.md

In a real project folder, start Claude Code and run the init command:

```text
/init
```

Claude scans the project and writes a **CLAUDE.md** describing it. Open the file — it's just Markdown you can edit.

### Step 2 — Make it yours

Add the things you'd otherwise repeat every time. A good CLAUDE.md includes:

```markdown
# Project: <name>

## What this is
A short description of the project and its goal.

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

Now every session starts with this context loaded — no re-explaining.

### Step 3 — Know the two levels of memory

- **Project memory:** `CLAUDE.md` in the project (shared with anyone who has the repo).
- **Personal memory:** a CLAUDE.md in your user Claude Code folder (`~/.claude/CLAUDE.md`) for *your* global preferences across all projects (e.g. "explain changes briefly," "I'm on Windows").

Put project facts in the project file; personal habits in the user file.

### Step 4 — Enter plan mode

For a non-trivial task, switch Claude Code into **plan mode** (in the CLI, cycle input modes — e.g. press **Shift+Tab** — until it shows *plan mode*). Then ask:

```text
Add input validation to the signup form and show a friendly error message.
Plan it first — don't change any files yet.
```

Claude **investigates and proposes a plan**, and waits. You read the approach before a single edit.

### Step 5 — Approve, then let it execute

If the plan looks right, approve it and let Claude carry it out, reviewing each change. If not, refine the plan in words first — much cheaper than undoing bad edits.

### Step 6 — Build the habit

- **Small/obvious task?** Just ask directly.
- **Anything with risk or multiple steps?** Plan mode first.
- **Repeating context every session?** It belongs in CLAUDE.md.

---

## 🧩 What goes where

| Fact | Put it in |
|------|-----------|
| How to run/test this project | Project `CLAUDE.md` |
| Project conventions & no-go zones | Project `CLAUDE.md` |
| "I'm on Windows, be concise" | Personal `~/.claude/CLAUDE.md` |
| A risky/multi-step change | Plan mode (approve first) |
| A one-line obvious fix | Just ask |

---

## ✅ Checkpoint

- [ ] You generated a `CLAUDE.md` with `/init` and edited it to add real context.
- [ ] You can explain project vs personal memory.
- [ ] You used **plan mode** to get a proposal before any edits.
- [ ] You approved a plan and had Claude execute it.

---

## 🎯 Homework

Write a real CLAUDE.md for a project you care about: what it is, how to run it, conventions, and no-go zones. Then give Claude Code a genuinely multi-step task in plan mode and only approve once the plan is right.

---

## 💡 Key takeaways

- **CLAUDE.md** is auto-loaded **project memory** — put standing context there and stop re-explaining (personal habits go in `~/.claude/CLAUDE.md`).
- **Plan mode** makes Claude **propose before editing** — review the approach, then approve.
- Direct ask for small tasks; **plan first** for anything risky or multi-step.

🌐 [Polski](../../pl/track-g/01-claude-md-i-tryb-planowania.md) · [← Track index](../README.md) · [Next: Slash commands →](02-slash-commands.md)
