# C1 — Schedule Scripts with Task Scheduler

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Python + `openai` + API key

🌐 [Polski](../../pl/track-c/01-harmonogram-zadan.md) · [← Track index](../README.md) · [Next: Build a pipeline →](02-pipelines.md)

---

## 🧠 Theory (3 min)

Automation means the computer does the work **without you starting it**. Windows has **Task Scheduler** built in — it runs a program on a schedule.

Our plan: a small Python script asks GPT for a daily brief, and Task Scheduler runs it **every morning**, saving the result to a file. You wake up, the brief is there.

The scheduled task runs **as your Windows user**, so it can read the `OPENAI_API_KEY` you set with `setx`.

---

## 🛠️ Practice (10 min)

### Step 1 — Write the "daily brief" script

In your course folder, create `daily_brief.py`:

```python
from openai import OpenAI
from datetime import date
from pathlib import Path

client = OpenAI()

TOPIC = "productivity and focus"

resp = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{
        "role": "user",
        "content": (
            f"Write me a short daily brief about {TOPIC}: "
            "one motivating idea, one practical tip I can use today, "
            "and one reflective question. Keep it under 150 words."
        ),
    }],
)
text = resp.choices[0].message.content

out_dir = Path.home() / "daily-briefs"
out_dir.mkdir(exist_ok=True)
out_file = out_dir / f"brief-{date.today().isoformat()}.md"
out_file.write_text(text, encoding="utf-8")
print(f"Saved: {out_file}")
```

### Step 2 — Run it once by hand

```powershell
cd $HOME\learn-ai-gpt
python daily_brief.py
```

Check `C:\Users\YourName\daily-briefs\` for the file.

### Step 3 — Find your Python path

```powershell
(Get-Command python).Source
```

Copy the printed path.

### Step 4 — Create the scheduled task

Replace both paths with **your** Python path and script path:

```powershell
schtasks /create /tn "GptDailyBrief" `
  /tr "'C:\Path\To\python.exe' 'C:\Users\YourName\learn-ai-gpt\daily_brief.py'" `
  /sc daily /st 08:00
```

### Step 5 — Test without waiting

```powershell
schtasks /run /tn "GptDailyBrief"
```

Check the folder for a fresh file. 🎉 It runs unattended.

> **Prefer clicking?** Open **Task Scheduler** → **Create Basic Task** → Daily → set time → **Start a program** → Program = your `python.exe`, arguments = the script path.

### Step 6 — Manage it

```powershell
schtasks /query /tn "GptDailyBrief"
schtasks /delete /tn "GptDailyBrief" /f
```

---

## 🧩 Why this works

| Piece | Role |
|-------|------|
| Python script | Does the AI work, saves a file |
| Task Scheduler | Starts it on a schedule |
| Runs as your user | Can read `OPENAI_API_KEY` |
| Saves to a file | You get the result without watching |

---

## ✅ Checkpoint

- [ ] `daily_brief.py` runs by hand and saves a dated file.
- [ ] You created a scheduled task.
- [ ] `schtasks /run` produced a fresh brief hands-free.

---

## 🎯 Homework

Change `TOPIC` to something you care about and set a time you'll notice. Let it run a few days — a taste of AI working for you on autopilot.

---

## 💡 Key takeaways

- **Task Scheduler** runs scripts automatically, hands-free.
- Give it the **full path** to `python.exe` and your script.
- Tasks run as your user, so they read your API key from the environment.
- Test with `schtasks /run`.

🌐 [Polski](../../pl/track-c/01-harmonogram-zadan.md) · [← Track index](../README.md) · [Next: Build a pipeline →](02-pipelines.md)
