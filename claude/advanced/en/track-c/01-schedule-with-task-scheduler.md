# C1 — Schedule Scripts with Task Scheduler

⏱️ **15 minutes** · Track: 🅲 Automator · Needs: Python + `anthropic` + API key (beginner course)

🌐 [Polski](../../pl/track-c/01-harmonogram-zadan.md) · [← Track index](../README.md) · [Next: Build a pipeline →](02-pipelines.md)

---

## 🧠 Theory (3 min)

Automation means the computer does the work **without you starting it**. Windows has a built-in tool for this: **Task Scheduler**. It can run a program on a schedule — every morning, every hour, at login.

Our plan: write a small Python script that asks Claude for something useful (a daily brief), then have Task Scheduler run it **automatically every morning** and save the result to a file. You wake up, the brief is already there.

One important detail: the scheduled task runs **as your Windows user**, so it can read the `ANTHROPIC_API_KEY` you set with `setx`. That's why we stored the key as a user environment variable in the beginner course.

---

## 🛠️ Practice (10 min)

### Step 1 — Write the "daily brief" script

In your course folder, create `daily_brief.py`:

```python
import anthropic
from datetime import date
from pathlib import Path

client = anthropic.Anthropic()

# What you want a brief about. Edit freely.
TOPIC = "productivity and focus"

resp = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{
        "role": "user",
        "content": (
            f"Write me a short daily brief about {TOPIC}: "
            "one motivating idea, one practical tip I can use today, "
            "and one reflective question. Keep it under 150 words."
        ),
    }],
)
text = resp.content[0].text

# Save to a dated file in a 'briefs' folder next to this script
out_dir = Path.home() / "daily-briefs"
out_dir.mkdir(exist_ok=True)
out_file = out_dir / f"brief-{date.today().isoformat()}.md"
out_file.write_text(text, encoding="utf-8")

print(f"Saved: {out_file}")
```

### Step 2 — Run it once by hand

```powershell
cd $HOME\learn-ai-claude
python daily_brief.py
```

Check that a file appeared in `C:\Users\YourName\daily-briefs\`. If yes, it's ready to automate.

### Step 3 — Find your Python path

Task Scheduler needs the **full path** to Python. Get it:

```powershell
(Get-Command python).Source
```

Copy the path it prints (e.g. `C:\Users\YourName\AppData\Local\Programs\Python\Python312\python.exe`).

### Step 4 — Create the scheduled task (quick way: `schtasks`)

In PowerShell, run this — replace the two paths with **your** Python path and script path:

```powershell
schtasks /create /tn "DailyBrief" `
  /tr "'C:\Path\To\python.exe' 'C:\Users\YourName\learn-ai-claude\daily_brief.py'" `
  /sc daily /st 08:00
```

- `/tn` = task name, `/tr` = what to run, `/sc daily` = schedule, `/st 08:00` = 8 AM.

### Step 5 — Test the task without waiting until morning

```powershell
schtasks /run /tn "DailyBrief"
```

Check your `daily-briefs` folder for a fresh file. 🎉 It works unattended.

> **Prefer clicking?** Open **Task Scheduler** (Start → type it) → **Create Basic Task** → name it → **Daily** → set the time → **Start a program** → Program = your `python.exe`, Add arguments = the script path. Same result, with a wizard.

### Step 6 — Manage it

```powershell
schtasks /query /tn "DailyBrief"     # see its status
schtasks /delete /tn "DailyBrief" /f  # remove it when you're done experimenting
```

---

## 🧩 Why this works

| Piece | Role |
|-------|------|
| Python script | Does the AI work and saves a file |
| Task Scheduler | Starts the script on a schedule |
| Runs as your user | Can read your `ANTHROPIC_API_KEY` |
| Saves to a file | You get the result without watching |

---

## ✅ Checkpoint

- [ ] `daily_brief.py` runs by hand and saves a dated file.
- [ ] You created a scheduled task (schtasks or the wizard).
- [ ] `schtasks /run` produced a fresh brief without you typing anything.

---

## 🎯 Homework

Change `TOPIC` to something you actually care about, and set the schedule to a time you'll notice (e.g. right before you start work). Let it run for a few days — a small taste of AI working for you on autopilot.

---

## 💡 Key takeaways

- **Task Scheduler** runs your scripts automatically, hands-free.
- Give it the **full path** to `python.exe` and to your script.
- Tasks run as your user, so they can read your API key from the environment.
- Test with `schtasks /run` instead of waiting for the scheduled time.

🌐 [Polski](../../pl/track-c/01-harmonogram-zadan.md) · [← Track index](../README.md) · [Next: Build a pipeline →](02-pipelines.md)
