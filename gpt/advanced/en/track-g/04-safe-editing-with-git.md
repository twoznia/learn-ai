# G4 — Safe Editing with Git

⏱️ **15 minutes** · Track: 🅶 Codex CLI in Depth · Needs: the Codex CLI + Git installed (`git --version`)

🌐 [Polski](../../pl/track-g/04-bezpieczna-edycja-z-git.md) · [← Prev](03-config-and-custom-prompts.md) · [Track index](../README.md) · [Next: Headless mode & automation →](05-headless-mode-and-automation.md)

---

## 🧠 Theory (4 min)

When an agent edits your files, you need an **undo button** and a way to **see exactly what changed**. That tool is **Git** — and it's the single biggest safety upgrade for AI-assisted coding.

The idea is simple:

- **Commit** a clean starting point *before* you let Codex work.
- Let it make changes, then **review the diff** — the precise before/after.
- **Keep** the good changes (commit) or **throw them away** (restore) — instantly, completely.

With Git under you, no agent edit is ever permanent until *you* decide it is. This pairs directly with the sandbox from G2: the sandbox limits *where* it can write; Git lets you *undo* what it wrote.

---

## 🛠️ Practice (10 min)

### Step 1 — Start clean

In your project, make sure everything is committed first:

```powershell
git status
git add -A
git commit -m "Clean starting point before agent work"
```

A clean tree means any change you see next came from this session.

### Step 2 — Let Codex make a change

Ask for a small, real edit:

```text
Add input validation to the main function and a short comment explaining it.
```

### Step 3 — Review the diff

See exactly what changed — line by line:

```powershell
git diff
```

**Read it.** This is the habit that keeps you in control: never accept edits you haven't looked at. You can even ask Codex to walk you through its own diff.

### Step 4 — Keep it, or undo it

**Happy?** Commit:

```powershell
git add -A
git commit -m "Add input validation"
```

**Not happy?** Throw the changes away and return to your clean point:

```powershell
git restore .
```

(That discards *uncommitted* changes. Because you committed in Step 1, you lose nothing you wanted.)

### Step 5 — Work in small loops

The safe rhythm:

1. Commit a clean point.
2. Ask for **one** focused change.
3. Review the diff.
4. Commit or restore.
5. Repeat.

Small loops mean small diffs — easy to review, easy to undo.

### Step 6 — Branch for anything bigger

For a larger experiment, work on a branch so `main` stays safe:

```powershell
git switch -c experiment
```

Like it? Merge later. Don't? Delete the branch — `main` never moved.

---

## 🧩 Your safety net

| Want to… | Command |
|----------|---------|
| Save a clean starting point | `git commit -m "..."` |
| See exactly what changed | `git diff` |
| Keep the changes | `git add -A && git commit` |
| Undo uncommitted changes | `git restore .` |
| Isolate a big experiment | `git switch -c <branch>` |

> ⚠️ **Never let an agent work on uncommitted, unbacked-up work.** Commit first — then every edit is reviewable and reversible.

---

## ✅ Checkpoint

- [ ] You committed a clean starting point before letting Codex edit.
- [ ] You reviewed a change with `git diff`.
- [ ] You kept one change (commit) and undid another (`git restore`).
- [ ] You can describe the commit → change → diff → keep/undo loop.

---

## 🎯 Homework

On a real project, do three edit loops with Codex: commit a clean point, ask for one change, review the diff, then commit or restore. Keep one, undo one on purpose so you trust your undo button.

---

## 💡 Key takeaways

- **Git is your undo button** for agent edits — commit a clean point first, and nothing is permanent until you say so.
- Always **review `git diff`** before accepting changes; never merge edits you haven't read.
- Work in **small loops** (commit → change → diff → keep/undo) and **branch** for bigger experiments.

🌐 [Polski](../../pl/track-g/04-bezpieczna-edycja-z-git.md) · [← Prev](03-config-and-custom-prompts.md) · [Track index](../README.md) · [Next: Headless mode & automation →](05-headless-mode-and-automation.md)
