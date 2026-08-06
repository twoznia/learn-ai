# C3 — Multi-File Projects with Codex CLI

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Codex CLI (beginner Lesson 13)

🌐 [Polski](../../pl/track-c/03-projekty-wieloplikowe.md) · [← Prev](02-pipelines.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

So far your scripts have been single files. Real tools have **several files**: code, config, a README. Managing that by hand is tedious — this is where **Codex CLI** (the terminal assistant from beginner Lesson 13) shines. It creates and edits **many files at once**, keeps them consistent, and works through a plan step by step.

The skill isn't typing code — it's **directing** the AI well:

1. **Describe the goal and constraints**, not just "build an app."
2. **Let it propose a plan** before writing files.
3. **Review each change** before approving.
4. **Iterate** in small steps.

---

## 🛠️ Practice (9 min)

We'll have Codex build a small multi-file tool: a **CLI that turns a folder of notes into an HTML page**.

### Step 1 — Start a clean project folder

```powershell
mkdir $HOME\notes-site
cd $HOME\notes-site
codex
```

### Step 2 — Describe the goal and ask for a plan first

```text
I want a small Python project that reads all .txt files in a "notes" subfolder
and builds a single index.html listing them, each with a GPT-generated
one-sentence summary.

Before writing any files, propose a short plan: what files you'll create and
what each does. Wait for my OK before creating anything.
```

Read its plan. You approve the **design** before any files exist.

### Step 3 — Approve and let it build

```text
Looks good. Create the files. Keep it simple and add a README.md explaining how to run it.
```

Codex creates several files and shows each for approval. **Read each** before saying yes.

### Step 4 — Run it and iterate

Follow the README it wrote (likely `python build_site.py`). If something's off, describe the fix — don't hand-edit:

```text
The summaries are too long. Make each one max 12 words, and sort notes newest first.
```
```text
Add a simple CSS style block so the page looks clean, with a readable font and spacing.
```

Each request touches whatever files are needed; Codex keeps them consistent.

### Step 5 — Ask it to explain the project

```text
Give me a one-paragraph overview of how these files fit together, for a beginner.
```

Now you understand a multi-file project you didn't type — and can keep growing it.

---

## 🧩 Directing Codex well

| Do | Instead of |
|----|------------|
| "Here's the goal + constraints; propose a plan first" | "build me an app" |
| Approve the plan, then the files | Blindly accepting everything |
| "Fix X: make summaries shorter" | Hand-editing files yourself |
| Small iterations | One giant request |
| "Explain how it fits together" | Leaving it a black box |

> **Safety:** Codex asks before creating/editing files or running commands. On a real project, work in a **dedicated folder** (or a git branch) so changes are easy to review and undo.

---

## ✅ Checkpoint

- [ ] Codex proposed a **plan** before writing files.
- [ ] It created a multi-file project you approved file by file.
- [ ] You iterated with plain-English change requests.
- [ ] You can explain how the files fit together.

---

## 🎯 Homework

Pick a small real tool you'd find useful (a habit tracker, a link organizer, a flashcard maker) and build it with Codex using the plan-first workflow. Keep requests small, review every change, end by asking for a README.

---

## 💡 Key takeaways

- Codex CLI manages **multi-file projects** — creating and editing many files consistently.
- The skill is **directing**: goal + constraints → plan → approve → iterate.
- Review every change; work in a dedicated folder or git branch.
- End by asking it to explain the project so it's not a black box.

🌐 [Polski](../../pl/track-c/03-projekty-wieloplikowe.md) · [← Prev](02-pipelines.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
