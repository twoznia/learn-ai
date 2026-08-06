# B3 — Build a Small App: Study Buddy

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `anthropic` + API key

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (3 min)

You now have the two building blocks: **memory** (B1) and **streaming** (B2). Let's combine them with a **system prompt** into a real, useful app: a **Study Buddy** that quizzes you on any topic, remembers your answers, and adapts.

This is the pattern behind most simple AI apps:

```
system prompt (the app's personality/rules)
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

In your course folder:

```powershell
notepad study_buddy.py
```

### Step 2 — Paste this complete program and save

```python
import anthropic

client = anthropic.Anthropic()

SYSTEM = """You are Study Buddy, a friendly quiz tutor.

Rules:
- First, if the topic isn't set yet, ask the user what topic to study.
- Then ask ONE question at a time and wait for the answer.
- After each answer: say if it's right, give a one-line explanation,
  then ask the next question, slightly harder if they got it right.
- Keep it encouraging and concise. Track how many they've gotten right.
- If the user types 'score', report how many correct so far.
"""

messages = []

print("📚 Study Buddy — type 'quit' to stop, 'score' for your score.\n")

# Kick things off so the tutor asks for a topic
messages.append({"role": "user", "content": "Let's start."})

def stream_reply():
    print("Buddy: ", end="", flush=True)
    with client.messages.stream(
        model="claude-sonnet-5",
        max_tokens=500,
        system=SYSTEM,
        messages=messages,
    ) as stream:
        for text in stream.text_stream:
            print(text, end="", flush=True)
        reply = stream.get_final_message().content[0].text
    messages.append({"role": "assistant", "content": reply})
    print("\n")

stream_reply()  # first prompt: asks for a topic

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

Tell it a topic ("the solar system", "Spanish verbs", "Python basics") and answer its questions. Notice it:
- **remembers** your previous answers (memory),
- **streams** its questions (nice UX),
- **stays in character** as a tutor (system prompt).

You built a real AI app. 🎉

---

## 🚀 Extend it (optional, use Claude Code)

Open the file in Claude Code (beginner Lesson 13) and ask:

```text
Add a command 'save' that writes the whole conversation to a study-log.txt file with today's date.
```
```text
Let me pass the topic as a command-line argument so I can run: python study_buddy.py "French food vocab".
```
```text
Switch the model to claude-haiku-4-5 to save cost, and add a one-line note explaining the trade-off.
```

You describe features; the AI writes them; you review and run.

---

## 🧩 The reusable app skeleton

Every small chat app you build reuses this shape:

```text
1. SYSTEM = "...the app's rules..."
2. messages = []                     # memory
3. loop:
     read user input
     append to messages
     stream a reply (with system=SYSTEM)
     append reply to messages
```

Swap the system prompt and you have a different app: email drafter, recipe helper, code explainer…

---

## ✅ Checkpoint

- [ ] `study_buddy.py` runs and quizzes you.
- [ ] It remembers earlier answers and streams its questions.
- [ ] You can explain the system + memory + streaming skeleton.

---

## 🎯 Homework

Copy `study_buddy.py` to a new file and change **only the SYSTEM prompt** to make a different app — e.g. an "Email Drafter" or "Recipe Helper." Same skeleton, new purpose. That's how fast you can ship small AI tools now.

---

## 💡 Key takeaways

- A small app = **system prompt + memory + streaming**.
- Change the system prompt → get a completely different app from the same skeleton.
- Grow features by describing them to Claude Code.

🌐 [Polski](../../pl/track-b/03-zbuduj-aplikacje.md) · [← Prev](02-streaming.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
