# G5 — Scripting the CLI (Non-Interactive Mode)

⏱️ **15 minutes** · Track: 🅶 Gemini CLI in Depth · Needs: the Gemini CLI installed & signed in

🌐 [Polski](../../pl/track-g/05-skryptowanie-cli.md) · [← Prev](04-checkpointing-and-undo.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

Everything so far used the CLI **interactively** — you type, it responds. But the Gemini CLI can also run **non-interactively**: give it a prompt on the command line, get the answer back, and move on. That unlocks **automation** — put Gemini inside scripts, scheduled tasks (Track C1), and pipelines (Track C2), all on your account.

Two shapes:

- **One-shot prompt:** `gemini -p "your prompt"` returns an answer and exits.
- **Piped input:** feed a file or command output into Gemini via a pipe.

This is how the Gemini CLI becomes a building block, not just a chat window.

> Exact flags evolve — run `gemini --help` for the current non-interactive options (prompt flag, output format, auto-approve).

---

## 🛠️ Practice (10 min)

### Step 1 — Run a one-shot prompt

In PowerShell:

```powershell
gemini -p "Give me three concise tips for writing clear commit messages."
```

You get the answer printed straight to the terminal and the CLI exits — perfect for scripts.

### Step 2 — Pipe a file in

Feed content through a pipe and ask Gemini to work on it:

```powershell
Get-Content notes.txt | gemini -p "Summarize this in 3 bullet points."
```

Gemini reads the piped text and returns the summary. Swap `notes.txt` for any file.

### Step 3 — Capture the output

Save the result to a file so a script can use it:

```powershell
gemini -p "Write a one-paragraph project status from these notes: (none — improvise a template)" > status.txt
```

Now `status.txt` holds Gemini's answer, ready for the next step of a pipeline.

### Step 4 — Put it in a tiny script

Create `daily.ps1`:

```powershell
$date = Get-Date -Format "yyyy-MM-dd"
gemini -p "Write a short, upbeat daily focus note for today ($date). Under 80 words." `
  | Out-File "$HOME\daily-notes\focus-$date.txt"
```

Run it — a Gemini-written note appears, no chat window. Combine this with **Task Scheduler (Track C1)** to run it every morning automatically.

### Step 5 — Automate safely

Non-interactive runs may need to skip the approval prompt (auto-approve) to work unattended. That's convenient but **removes your safety gate**, so:
- Use auto-approve **only** for prompts that don't edit files or run risky commands (summaries, drafts, text out).
- If a script must edit files, run it in a **dedicated folder / git branch** so every change is reversible (G4).
- Never point an unattended, auto-approving job at sensitive data or your whole disk.

### Step 6 — Connect the dots with Track C

You now have both halves: the **Gemini CLI as a command** (this lesson) and **scheduling/pipelines** (Track C). Together they let Gemini do recurring work for you — hands-free, on your account.

---

## 🧩 Interactive vs scripted

| Use | Mode |
|-----|------|
| Exploring, editing, back-and-forth | Interactive (`gemini`) |
| One answer inside a script | `gemini -p "..."` |
| Process a file/output | Pipe into `gemini -p "..."` |
| Recurring hands-free task | Script + Task Scheduler (C1) |

> ⚠️ **Automation removes the human gate.** Only auto-approve safe, read/generate prompts; keep file-editing scripts in a reversible (git) folder; never aim an unattended job at sensitive data.

---

## ✅ Checkpoint

- [ ] You ran a one-shot prompt with `gemini -p`.
- [ ] You piped a file into Gemini and got a result.
- [ ] You saved output to a file and ran it from a small script.
- [ ] You can state the safety rules for unattended, auto-approving runs.

---

## 🎯 Homework

Write a small script that pipes one of your real files into `gemini -p` and saves a summary. If you did Track C1, schedule a safe, read/generate-only version to run daily. Keep any file-editing automation in a git-tracked folder.

---

## 💡 Key takeaways

- The Gemini CLI runs **non-interactively** (`gemini -p "..."`, or piped input) — the key to putting Gemini in **scripts and pipelines**.
- Capture output to files and combine with **Task Scheduler (C1)** for hands-free recurring work.
- **Automation removes the approval gate** — auto-approve only safe prompts, keep file edits in a reversible git folder, and never target sensitive data unattended.

🌐 [Polski](../../pl/track-g/05-skryptowanie-cli.md) · [← Prev](04-checkpointing-and-undo.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
