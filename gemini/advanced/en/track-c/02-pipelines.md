# C2 — Build a Pipeline

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Python + `google-genai` + API key

🌐 [Polski](../../pl/track-c/02-potoki.md) · [← Prev](01-schedule-with-task-scheduler.md) · [Track index](../README.md) · [Next: Multi-file projects →](03-multi-file-projects.md)

---

## 🧠 Theory (3 min)

A **pipeline** chains steps so data flows through automatically:

```
read input  →  ask Gemini  →  save output
```

The power comes from doing this **in batch** — over many files — with a loop. Instead of pasting into the app 20 times, your script processes 20 files while you get coffee.

We'll build a **batch summarizer**: drop `.txt` files in a folder, run one command, get a `.summary.md` for each.

---

## 🛠️ Practice (10 min)

### Step 1 — Make an input folder with a couple of files

```powershell
mkdir $HOME\pipeline-in
"Long meeting notes... launch in March, budget 5000, Sara owns design." | Out-File $HOME\pipeline-in\meeting1.txt
"Call notes: client wants a logo refresh, deadline end of month, needs 3 concepts." | Out-File $HOME\pipeline-in\call2.txt
```

### Step 2 — Write the pipeline

Create `summarize_folder.py`:

```python
from google import genai
from pathlib import Path

client = genai.Client()

IN_DIR = Path.home() / "pipeline-in"
OUT_DIR = Path.home() / "pipeline-out"
OUT_DIR.mkdir(exist_ok=True)

def summarize(text):
    resp = client.models.generate_content(
        model="gemini-2.5-flash",
        contents=(
            "Summarize the notes below in 3 bullet points, then list any "
            "dates, names, or amounts on a line starting 'Key facts:'.\n\n" + text
        ),
    )
    return resp.text

txt_files = sorted(IN_DIR.glob("*.txt"))
print(f"Found {len(txt_files)} file(s).")

for f in txt_files:
    print(f"Processing {f.name} ...")
    summary = summarize(f.read_text(encoding="utf-8"))
    (OUT_DIR / (f.stem + ".summary.md")).write_text(summary, encoding="utf-8")

print(f"Done. Summaries are in {OUT_DIR}")
```

### Step 3 — Run it

```powershell
cd $HOME\learn-ai-gemini
python summarize_folder.py
```

Open `C:\Users\YourName\pipeline-out\` — one summary per input file. 🎉

### Step 4 — Add a second stage (chaining)

Append this to combine all summaries into a digest:

```python
all_summaries = "\n\n---\n\n".join(
    p.read_text(encoding="utf-8") for p in sorted(OUT_DIR.glob("*.summary.md"))
)

resp = client.models.generate_content(
    model="gemini-2.5-pro",
    contents="Combine these summaries into one short digest with the top "
             "3 priorities across all of them:\n\n" + all_summaries,
)
(OUT_DIR / "DIGEST.md").write_text(resp.text, encoding="utf-8")
print("Wrote DIGEST.md")
```

Now the flow is: **read many files → summarize each → combine into one digest** — a real multi-stage pipeline.

### Step 5 — Automate it (combine with C1)

Schedule `summarize_folder.py` with Task Scheduler (C1) to run every evening. Drop notes in `pipeline-in` during the day; wake up to summaries and a digest.

---

## 🧩 The pipeline pattern

| Stage | Code |
|-------|------|
| Read inputs | `Path.glob("*.txt")` + `read_text()` |
| Process each | a function that calls Gemini |
| Save outputs | `write_text()` to an output folder |
| (Optional) combine | one more Gemini call over all results |

> ⚠️ **Cost & safety:** batch jobs make many API calls — start with a few files and `gemini-2.5-flash` (free tier). Never point a pipeline at a folder with secrets or private data.

---

## ✅ Checkpoint

- [ ] `summarize_folder.py` produced one summary per input file.
- [ ] You added a second stage that wrote `DIGEST.md`.
- [ ] You understand read → process → save (→ combine).

---

## 🎯 Homework

Adapt the pipeline to a real folder — old notes, saved articles. Summarize in batch, then schedule it (C1) so new files get processed automatically.

---

## 💡 Key takeaways

- A pipeline = **read → ask Gemini → save**, in a loop over many items.
- Chain stages (summarize each → combine) for multi-step automation.
- Combine with Task Scheduler (C1) for hands-free batch processing.
- Start small on the free tier; never batch over private data.

🌐 [Polski](../../pl/track-c/02-potoki.md) · [← Prev](01-schedule-with-task-scheduler.md) · [Track index](../README.md) · [Next: Multi-file projects →](03-multi-file-projects.md)
