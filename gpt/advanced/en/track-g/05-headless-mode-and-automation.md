# G5 — Headless Mode & Automation

⏱️ **15 minutes** · Track: 🅶 Codex CLI in Depth · Needs: the Codex CLI installed & signed in

🌐 [Polski](../../pl/track-g/05-tryb-bezobslugowy-i-automatyzacja.md) · [← Prev](04-safe-editing-with-git.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

Everything so far has been **interactive** — you and Codex, back and forth. But Codex can also run **headless**: give it a task in **one command**, it does the work and prints the result, then exits. No chat.

That unlocks **automation**. A headless command can go into:

- A **script** that runs several steps in a row.
- A **scheduled task** (like the pipelines in Track C).
- A **Git hook** or CI step that checks or summarizes changes.

The command is `codex exec` (sometimes shown as a non-interactive/`exec` mode) — a task string in, a result out.

> Exact flag names and output options change over time. Check `codex --help` and the current docs; the *pattern* — one command, one result — is what matters.

---

## 🛠️ Practice (10 min)

### Step 1 — Run one task, non-interactively

From your project folder:

```powershell
codex exec "Summarize what this project does in three sentences."
```

It runs once and prints the answer — no session to manage.

### Step 2 — Keep it safe with the sandbox

Headless still respects G2's guards. For read-only automation, run it in a read-only mode so it can't change anything:

```powershell
codex exec --sandbox read-only "List any TODO comments and where they are."
```

> Match the mode to the job: **read-only** for reporting/summaries; a writing mode only when the task *should* change files — and only somewhere backed by Git (G4).

### Step 3 — Feed it your own data

Pipe content in, or point it at files, so it works on *your* material:

```powershell
git diff | codex exec "Write a concise commit message for this diff."
```

One command turns your diff into a ready-to-use message.

### Step 4 — Put it in a small script

Chain steps into a `.ps1` file:

```powershell
# review.ps1 — quick automated review of current changes
codex exec --sandbox read-only "Review the current git changes and list risks as bullets."
```

Run it any time with `./review.ps1`. This is where G1–G4 pay off: **AGENTS.md** gives context, **config** sets defaults, **prompts** are reusable, and **git** keeps it safe — all in one automated line.

### Step 5 — Schedule it (tie-in to Track C)

Point Windows **Task Scheduler** at your script (exactly like the pipelines in Track C) for a daily summary, a nightly review, or a weekly report — generated while you sleep.

### Step 6 — Know when *not* to automate

Headless is best for **repeatable, low-risk** tasks (summaries, reviews, reports). For anything ambiguous, creative, or high-stakes, stay **interactive** so you can steer.

---

## 🧩 Interactive vs headless

| | Interactive | Headless (`codex exec`) |
|--|-------------|--------------------------|
| Shape | Back-and-forth chat | One command → one result |
| Best for | Exploring, building, steering | Summaries, reviews, scripted tasks |
| Fits into | Your working session | Scripts, schedules, hooks |
| Safety | You watch every step | Set sandbox mode + rely on Git |

---

## ✅ Checkpoint

- [ ] You ran a task with `codex exec` and got a one-shot result.
- [ ] You ran a read-only headless task safely.
- [ ] You piped your own data (e.g. a diff) into a headless command.
- [ ] You put one headless command into a small script, and know when to stay interactive.

---

## 🎯 Homework

Write a small script that runs a headless Codex task you'd actually use — a diff-to-commit-message helper, a TODO lister, or a change reviewer. Run it read-only. Optionally schedule it with Task Scheduler (Track C). You've now automated your own AI assistant.

---

## 💡 Key takeaways

- **`codex exec`** runs a task **headless** — one command in, one result out — for scripts, schedules, and hooks.
- Keep it safe: pick the **sandbox mode** to match the job (read-only for reports) and lean on **Git** (G4).
- Automate **repeatable, low-risk** work; stay **interactive** for anything ambiguous or high-stakes.

🌐 [Polski](../../pl/track-g/05-tryb-bezobslugowy-i-automatyzacja.md) · [← Prev](04-safe-editing-with-git.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
