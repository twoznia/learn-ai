# C3 — Multi-File Projects with Claude Code

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Claude Code (beginner Lesson 13)

🌐 [Polski](../../pl/track-c/03-projekty-wieloplikowe.md) · [← Prev](02-pipelines.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

So far your scripts have been single files. Real tools have **several files**: code, config, a README, maybe tests. Managing that by hand is tedious — this is exactly where **Claude Code** (the terminal assistant from beginner Lesson 13) shines. It can create and edit **many files at once**, keep them consistent, and work through a plan step by step.

The skill here isn't typing code — it's **directing** the AI well:

1. **Describe the goal and constraints**, not just "build an app."
2. **Let it propose a plan** before writing files.
3. **Review each change** before approving.
4. **Iterate** in small steps.

---

## 🛠️ Practice (9 min)

We'll have Claude Code build a small multi-file tool: a **CLI that turns a folder of notes into an HTML page**.

### Step 1 — Start a clean project folder

```powershell
mkdir $HOME\notes-site
cd $HOME\notes-site
claude
```

### Step 2 — Describe the goal and ask for a plan first

In Claude Code, paste this — notice we ask for a **plan before code**:

```text
I want a small Python project that reads all .txt files in a "notes" subfolder
and builds a single index.html listing them, each with a Claude-generated
one-sentence summary.

Before writing any files, propose a short plan: what files you'll create and
what each does. Wait for my OK before creating anything.
```

Read its plan. This is the key habit — you approve the **design** before any files exist.

### Step 3 — Approve and let it build the files

Reply:

```text
Looks good. Create the files. Keep it simple and add a README.md explaining how to run it.
```

Claude Code will create several files (e.g. `build_site.py`, `README.md`, maybe a sample `notes/` file). It shows each one and asks to approve. **Read each** before saying yes.

### Step 4 — Run it and iterate

Follow the README it wrote (likely something like):

```powershell
python build_site.py
```

If something's off, describe the fix — don't hand-edit:

```text
The summaries are too long. Make each one max 12 words, and sort notes newest first.
```
```text
Add a simple CSS style block so the page looks clean, with a readable font and spacing.
```

Each request touches whatever files are needed; Claude Code keeps them consistent.

### Step 5 — Ask it to explain the project

```text
Give me a one-paragraph overview of how these files fit together, for a beginner.
```

Now you understand a multi-file project you didn't type — and can keep growing it.

---

## 🧩 Directing Claude Code well

| Do | Instead of |
|----|------------|
| "Here's the goal + constraints; propose a plan first" | "build me an app" |
| Approve the plan, then the files | Blindly accepting everything |
| "Fix X: make summaries shorter" | Hand-editing files yourself |
| Small iterations | One giant request |
| "Explain how it fits together" | Leaving it a black box |

> **Safety:** Claude Code asks before creating/editing files or running commands. On a real project, work in a **dedicated folder** (or a git branch) so changes are easy to review and undo.

---

## ✅ Checkpoint

- [ ] Claude Code proposed a **plan** before writing files.
- [ ] It created a multi-file project you approved file by file.
- [ ] You iterated with plain-English change requests.
- [ ] You can explain how the files fit together.

---

## 🎯 Homework

Pick a small real tool you'd find useful (a habit tracker, a link organizer, a flashcard maker) and build it with Claude Code using the plan-first workflow. Keep the requests small, review every change, and end by asking for a README.

---

## 💡 Key takeaways

- Claude Code manages **multi-file projects** — creating and editing many files consistently.
- The skill is **directing**: goal + constraints → plan → approve → iterate.
- Review every change; work in a dedicated folder or git branch.
- End by asking it to explain the project so it's not a black box.

🌐 [Polski](../../pl/track-c/03-projekty-wieloplikowe.md) · [← Prev](02-pipelines.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
