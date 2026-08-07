# G4 — Checkpointing & Safe Editing

⏱️ **15 minutes** · Track: 🅶 Gemini CLI in Depth · Needs: the Gemini CLI installed & signed in; git helps

🌐 [Polski](../../pl/track-g/04-checkpointy-i-cofanie.md) · [← Prev](03-tools-and-approvals.md) · [Track index](../README.md) · [Next: Scripting the CLI →](05-scripting-the-cli.md)

---

## 🧠 Theory (5 min)

Agents edit real files, so the confidence to let them work comes from being able to **undo**. The Gemini CLI supports **checkpointing** — it can snapshot your project **before** it makes changes, so you can **restore** to that point if an edit goes wrong.

Two safety nets, used together:

- **Checkpointing** — the CLI's own snapshot-and-restore (via the `/restore` command). Great for undoing a specific tool action.
- **Git** — your version control. A clean branch + small commits means you can always diff and revert.

With these, letting the CLI edit is low-risk: mistakes are reversible, not scary.

> Checkpointing may need to be enabled in settings, and details evolve. If `/restore` isn't available, **git is your reliable undo** — this lesson leans on both.

---

## 🛠️ Practice (9 min)

### Step 1 — Start from a clean git state

Working where git is set up makes everything reversible:

```powershell
git status
```

Commit or stash anything pending so you have a clean baseline. (No git yet? `git init` a scratch project for practice.)

### Step 2 — Let the CLI make a change

Ask for an edit and approve it:

```text
Add a "## Notes" section to the README with two example bullets.
```

### Step 3 — Restore with checkpointing

If checkpointing is on, you can roll back the last tool action:

```text
/restore
```

The CLI lists restore points (snapshots taken before edits) and puts the project back. This is your instant "undo that."

### Step 4 — Undo with git

Git is the dependable net. To see and revert:

```powershell
git diff            # what changed
git restore .       # discard unstaged changes
```

Or, if you committed and want to go back a step, use your normal git flow. The point: **nothing the CLI does is permanent** when you work in git.

### Step 5 — Build the safe-editing habit

- **New task / risky edit?** Start from a clean git state so the diff is meaningful.
- **Small commits** as you go — each is a restore point.
- **Review the diff** after the CLI edits, before you accept it into your work.

### Step 6 — Combine with the approval flow (G3)

Approvals stop bad actions *before* they happen; checkpointing/git undo them *after*. Together they make agent editing genuinely safe: you gate changes, and you can reverse any that slip through.

---

## 🧩 Your two undo nets

| Net | Use it to |
|-----|-----------|
| **Checkpointing (`/restore`)** | Roll back a specific tool action fast |
| **Git (`diff`, `restore`, commits)** | Review and revert reliably, always |
| **Both** | Confident, low-risk agent editing |

> ⚠️ **Reversibility is the safety.** Work in git, keep commits small, and review diffs. If you ever let the CLI run in a faster auto-approve mode, do it **only** in a clean git branch so every change is recoverable.

---

## ✅ Checkpoint

- [ ] You started from a clean git state before letting the CLI edit.
- [ ] You restored a change with `/restore` (or reverted with git).
- [ ] You reviewed a diff after an edit before accepting it.
- [ ] You can explain how approvals + undo make editing safe.

---

## 🎯 Homework

In a git-tracked scratch project, let the CLI make a few edits, then practice both undo paths: `/restore` and `git restore`. Get comfortable reviewing the diff after each change so accepting or reverting is a quick, confident decision.

---

## 💡 Key takeaways

- **Checkpointing** (`/restore`) snapshots your project before edits so you can roll back a tool action.
- **Git** (clean branch, small commits, diffs) is your dependable, always-available undo.
- Approvals stop bad actions up front; **undo** reverses anything after — together they make agent editing safe.

🌐 [Polski](../../pl/track-g/04-checkpointy-i-cofanie.md) · [← Prev](03-tools-and-approvals.md) · [Track index](../README.md) · [Next: Scripting the CLI →](05-scripting-the-cli.md)
