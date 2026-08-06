# C2 — Build a Pipeline

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Python + `anthropic` + API key

🌐 [Polski](../../pl/track-c/02-potoki.md) · [← Prev](01-schedule-with-task-scheduler.md) · [Track index](../README.md) · [Next: Multi-file projects →](03-multi-file-projects.md)

---

## 🧠 Theory (3 min)

A **pipeline** chains steps so data flows through them automatically:

```
read input  →  ask Claude  →  save output
```

The power comes from doing this **in batch** — over many files, rows, or items — with a loop. Instead of copy-pasting into the chat 20 times, your script processes 20 files while you get coffee.

We'll build a **batch summarizer**: drop `.txt` files in a folder, run one command, and get a `.summary.md` for each.

---

## 🛠️ Practice (10 min)

### Step 1 — Make an input folder with a couple of files

```powershell
mkdir $HOME\pipeline-in
"Long meeting notes... we decided to launch in March, budget is 5000, Sara owns design." | Out-File $HOME\pipeline-in\meeting1.txt
"Notes from the call: client wants a logo refresh, deadline end of month, needs 3 concepts." | Out-File $HOME\pipeline-in\call2.txt
```

### Step 2 — Write the pipeline

In your course folder, create `summarize_folder.py`:

```python
import anthropic
from pathlib import Path

client = anthropic.Anthropic()

IN_DIR = Path.home() / "pipeline-in"
OUT_DIR = Path.home() / "pipeline-out"
OUT_DIR.mkdir(exist_ok=True)

def summarize(text):
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=400,
        messages=[{
            "role": "user",
            "content": (
                "Summarize the notes below in 3 bullet points, then list any "
                "dates, names, or amounts on a line starting 'Key facts:'.\n\n" + text
            ),
        }],
    )
    return resp.content[0].text

# The pipeline: loop over every .txt file
txt_files = sorted(IN_DIR.glob("*.txt"))
print(f"Found {len(txt_files)} file(s).")

for f in txt_files:
    print(f"Processing {f.name} ...")
    text = f.read_text(encoding="utf-8")
    summary = summarize(text)
    out_file = OUT_DIR / (f.stem + ".summary.md")
    out_file.write_text(summary, encoding="utf-8")

print(f"Done. Summaries are in {OUT_DIR}")
```

### Step 3 — Run the pipeline

```powershell
cd $HOME\learn-ai-claude
python summarize_folder.py
```

Open `C:\Users\YourName\pipeline-out\` — one summary per input file. You just processed a whole folder with one command. 🎉

### Step 4 — Add a step (chaining gets powerful)

Pipelines shine when you **chain** steps. Let's add a second stage that combines all summaries into one digest. Append this to the script (or make `digest.py`):

```python
# Second stage: combine all summaries into one digest
all_summaries = "\n\n---\n\n".join(
    p.read_text(encoding="utf-8") for p in sorted(OUT_DIR.glob("*.summary.md"))
)

resp = client.messages.create(
    model="claude-sonnet-5",
    max_tokens=500,
    messages=[{
        "role": "user",
        "content": "Combine these summaries into one short digest with the top "
                   "3 priorities across all of them:\n\n" + all_summaries,
    }],
)
(OUT_DIR / "DIGEST.md").write_text(resp.content[0].text, encoding="utf-8")
print("Wrote DIGEST.md")
```

Now the flow is: **read many files → summarize each → combine into one digest**. That's a real multi-stage pipeline.

### Step 5 — Automate it (combine with C1)

Schedule `summarize_folder.py` with Task Scheduler (Lesson C1) to run every evening. Drop notes in `pipeline-in` during the day; wake up to summaries and a digest. Automation + pipeline = leverage.

---

## 🧩 The pipeline pattern

| Stage | Code |
|-------|------|
| Read inputs | `Path.glob("*.txt")` + `read_text()` |
| Process each | a function that calls Claude |
| Save outputs | `write_text()` to an output folder |
| (Optional) combine | one more Claude call over all results |

> ⚠️ **Cost & safety:** batch jobs make many API calls — start with a few files and a cheap model (`claude-haiku-4-5`). Never point a pipeline at a folder with secrets or private data.

---

## ✅ Checkpoint

- [ ] `summarize_folder.py` produced one summary per input file.
- [ ] You added a second stage that wrote `DIGEST.md`.
- [ ] You understand read → process → save (→ combine).

---

## 🎯 Homework

Adapt the pipeline to a real folder of your own — old notes, articles you saved, exported chats. Summarize them in batch. Then schedule it (C1) so new files get processed automatically.

---

## 💡 Key takeaways

- A pipeline = **read → ask Claude → save**, run in a loop over many items.
- Chain stages (summarize each → combine) for multi-step automation.
- Combine with Task Scheduler (C1) for hands-free batch processing.
- Start small and cheap; never batch over private/secret data.

🌐 [Polski](../../pl/track-c/02-potoki.md) · [← Prev](01-schedule-with-task-scheduler.md) · [Track index](../README.md) · [Next: Multi-file projects →](03-multi-file-projects.md)
