# B3 — Build a Small App: Study Buddy

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `openai` + API key

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (3 min)

You have the two building blocks: **memory** (B1) and **streaming** (B2). Combine them with a **system message** and you have a real app: a **Study Buddy** that quizzes you on any topic, remembers your answers, and adapts.

This is the pattern behind most simple AI apps:

```
system message (the app's personality/rules)
      +
memory (the running messages list)
      +
streaming (nice live output)
      =
a small app
```

---

## 🛠️ Build it (10 min)

### Step 1 — Create the app

```powershell
cd $HOME\learn-ai-gpt
notepad study_buddy.py
```

### Step 2 — Paste this complete program and save

```python
from openai import OpenAI

client = OpenAI()

SYSTEM = """You are Study Buddy, a friendly quiz tutor.

Rules:
- First, if the topic isn't set yet, ask the user what topic to study.
- Then ask ONE question at a time and wait for the answer.
- After each answer: say if it's right, give a one-line explanation,
  then ask the next question, slightly harder if they got it right.
- Keep it encouraging and concise. Track how many they've gotten right.
- If the user types 'score', report how many correct so far.
"""

messages = [{"role": "system", "content": SYSTEM}]

print("📚 Study Buddy — type 'quit' to stop, 'score' for your score.\n")

def stream_reply():
    print("Buddy: ", end="", flush=True)
    pieces = []
    stream = client.chat.completions.create(
        model="gpt-5-mini", messages=messages, stream=True,
    )
    for chunk in stream:
        piece = chunk.choices[0].delta.content
        if piece:
            print(piece, end="", flush=True)
            pieces.append(piece)
    messages.append({"role": "assistant", "content": "".join(pieces)})
    print("\n")

# Kick things off so the tutor asks for a topic
messages.append({"role": "user", "content": "Let's start."})
stream_reply()

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        print("Nice work — see you next session! 👋")
        break
    messages.append({"role": "user", "content": user_text})
    stream_reply()
```

### Step 3 — Run it and study something

```powershell
python study_buddy.py
```

Give it a topic ("the solar system", "Spanish verbs", "Python basics") and answer its questions. Notice it:
- **remembers** your previous answers (memory),
- **streams** its questions (nice UX),
- **stays in character** as a tutor (system message).

You built a real AI app. 🎉

---

## 🚀 Extend it (optional, use Codex CLI)

Open the file in Codex CLI (beginner Lesson 13) and ask:

```text
Add a command 'save' that writes the whole conversation to a study-log.txt file with today's date.
```
```text
Let me pass the topic as a command-line argument so I can run: python study_buddy.py "French food vocab".
```

You describe features; the AI writes them; you review and run.

---

## 🧩 The reusable app skeleton

```text
1. messages = [{"role": "system", "content": "...rules..."}]   # role
2. loop:
     read user input, append to messages
     stream a reply (stream=True), collect pieces
     append the reply to messages                              # memory
```

Swap the system message and you have a different app: email drafter, recipe helper, code explainer…

---

## ✅ Checkpoint

- [ ] `study_buddy.py` runs and quizzes you.
- [ ] It remembers earlier answers and streams its questions.
- [ ] You can explain the system + memory + streaming skeleton.

---

## 🎯 Homework

Copy `study_buddy.py` to a new file and change **only the SYSTEM message** to make a different app — an "Email Drafter" or "Recipe Helper." Same skeleton, new purpose.

---

## 💡 Key takeaways

- A small app = **system message + memory + streaming**.
- Change the system message → a completely different app from the same skeleton.
- Grow features by describing them to Codex CLI.

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
