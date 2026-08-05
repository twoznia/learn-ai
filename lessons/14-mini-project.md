# Lesson 14 — Build a Mini Project: An AI Notes Assistant

⏱️ **10 minutes** (plus optional tinkering) · Level: Beginner · Needs: Python + API key

[← Prev](13-claude-code-cli.md) · [Course home](../README.md) · [Next: MCP intro →](15-mcp-intro.md)

---

## 🧠 Theory (2 min)

Time to build something you'll actually keep: a **command-line notes assistant**. You write messy notes; Claude cleans them up, summarizes them, and pulls out action items. This ties together everything from Lessons 8–10.

New concept: a **system prompt**. It's a standing instruction that shapes how Claude behaves for the whole request — like the "custom instructions" from Lesson 7, but in code.

---

## 🛠️ Build it (7 min)

### Step 1 — Create the file

```powershell
cd $HOME\learn-ai-claude
notepad notes_assistant.py
```

### Step 2 — Paste this complete program and save

```python
import anthropic

client = anthropic.Anthropic()

# A "system prompt" sets Claude's role and rules for the whole conversation.
SYSTEM = """You are a tidy notes assistant.
Given messy notes, you always respond with exactly three sections:

## Clean Summary
(2-4 clear sentences)

## Key Points
(bullet list of the most important facts)

## Action Items
(a checklist of tasks; write 'None' if there are no tasks)

Keep it concise and friendly. If something is unclear, note it briefly."""

print("Paste your messy notes below. Press Enter, then Ctrl+Z and Enter to finish:\n")

# Read everything the user types until they signal end-of-input
import sys
notes = sys.stdin.read()

if not notes.strip():
    print("No notes given. Exiting.")
    raise SystemExit

response = client.messages.create(
    model="claude-sonnet-5",
    max_tokens=800,
    system=SYSTEM,
    messages=[
        {"role": "user", "content": notes}
    ],
)

print("\n" + "=" * 50 + "\n")
for block in response.content:
    if block.type == "text":
        print(block.text)
```

### Step 3 — Run it

```powershell
python notes_assistant.py
```

Then paste some messy notes, for example:

```text
meeting w/ sam tuesday. talked about the new website. sam will send logo files by friday. we need to pick colors. budget maybe 2000. launch hopefully next month. i should email the printer about business cards
```

To finish input on Windows: press **Enter**, then **Ctrl+Z**, then **Enter**.

Claude returns a clean summary, key points, and a checklist. ✅

---

## 🧩 What you just learned

| Feature | Why it matters |
|---------|----------------|
| **System prompt** (`system=`) | Sets Claude's role and output format once, reliably |
| **Structured output** (the three `##` sections) | Predictable, reusable format |
| **Reading multi-line input** (`sys.stdin.read()`) | Handle real paragraphs, not one line |

---

## 🚀 Make it yours (optional, use Claude Code!)

Open this project in **Claude Code** (Lesson 13) and ask for upgrades in plain English:

```text
Change notes_assistant.py so it reads notes from a file called notes.txt instead of pasting.
```

```text
Save Claude's cleaned-up result to a file called summary.md with today's date in the filename.
```

```text
Add a friendly error message if the API key is missing.
```

Let the AI build the features — you review and approve. This is exactly how real developers now work.

---

## ✅ Checkpoint

- [ ] `notes_assistant.py` runs and returns 3 sections.
- [ ] You understand what the `system` prompt does.
- [ ] (Bonus) You added at least one feature via Claude Code.

---

## 🎯 Homework

Use your notes assistant on something real this week — a meeting, a lecture, a brain-dump. Notice how much faster it is than organizing by hand.

---

## 💡 Key takeaways

- A **system prompt** reliably shapes Claude's role and output format.
- Asking for a fixed structure (sections/checklists) makes results reusable.
- You can grow a small script into a real tool by describing features to Claude Code.

[← Prev](13-claude-code-cli.md) · [Course home](../README.md) · [Next: MCP intro →](15-mcp-intro.md)
