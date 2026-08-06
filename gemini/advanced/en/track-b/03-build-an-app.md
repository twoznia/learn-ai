# B3 — Build a Small App: Study Buddy

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `google-genai` + API key

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (3 min)

You have the two building blocks: **memory** (B1, via `client.chats`) and **streaming** (B2). Add a **system instruction** and you have a real app: a **Study Buddy** that quizzes you on any topic, remembers your answers, and adapts.

This is the pattern behind most simple AI apps:

```
system instruction (the app's personality/rules)
      +
chat memory (client.chats keeps history)
      +
streaming (nice live output)
      =
a small app
```

---

## 🛠️ Build it (10 min)

### Step 1 — Create the app

```powershell
cd $HOME\learn-ai-gemini
notepad study_buddy.py
```

### Step 2 — Paste this complete program and save

```python
from google import genai
from google.genai import types

client = genai.Client()

SYSTEM = """You are Study Buddy, a friendly quiz tutor.

Rules:
- First, if the topic isn't set yet, ask the user what topic to study.
- Then ask ONE question at a time and wait for the answer.
- After each answer: say if it's right, give a one-line explanation,
  then ask the next question, slightly harder if they got it right.
- Keep it encouraging and concise. Track how many they've gotten right.
- If the user types 'score', report how many correct so far.
"""

chat = client.chats.create(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(system_instruction=SYSTEM),
)

print("📚 Study Buddy — type 'quit' to stop, 'score' for your score.\n")

def stream_reply(message):
    print("Buddy: ", end="", flush=True)
    for chunk in chat.send_message_stream(message):
        print(chunk.text, end="", flush=True)
    print("\n")

stream_reply("Let's start.")  # first prompt: asks for a topic

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        print("Nice work — see you next session! 👋")
        break
    stream_reply(user_text)
```

### Step 3 — Run it and study something

```powershell
python study_buddy.py
```

Give it a topic ("the solar system", "Spanish verbs", "Python basics") and answer its questions. Notice it:
- **remembers** your previous answers (chat memory),
- **streams** its questions (nice UX),
- **stays in character** as a tutor (system instruction).

You built a real AI app. 🎉

---

## 🚀 Extend it (optional, use Gemini CLI)

Open the file in Gemini CLI (beginner Lesson 13) and ask:

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
1. SYSTEM = "...the app's rules..."
2. chat = client.chats.create(model=..., config=system_instruction)   # memory
3. loop:
     read user input
     stream a reply with chat.send_message_stream(...)
```

Swap the system instruction and you have a different app: email drafter, recipe helper, code explainer…

---

## ✅ Checkpoint

- [ ] `study_buddy.py` runs and quizzes you.
- [ ] It remembers earlier answers and streams its questions.
- [ ] You can explain the system + memory + streaming skeleton.

---

## 🎯 Homework

Copy `study_buddy.py` to a new file and change **only the SYSTEM instruction** to make a different app — an "Email Drafter" or "Recipe Helper." Same skeleton, new purpose.

---

## 💡 Key takeaways

- A small app = **system instruction + chat memory + streaming**.
- Change the system instruction → a completely different app from the same skeleton.
- Grow features by describing them to Gemini CLI.

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
