# B1 — Conversations with Memory

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `google-genai` + API key (beginner course)

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)

---

## 🧠 Theory (4 min)

In the beginner course, each script sent **one** message via `generate_content` and got **one** reply — no memory between calls. To build a chatbot that remembers, you need **conversation history**.

The `google-genai` library gives you two ways:

1. **`client.chats`** (easy) — a chat **object keeps the history for you**. You just `send_message` each turn.
2. **Manual `contents` list** (full control) — you build a list of turns yourself.

We'll use `client.chats` — it's the clean way to get memory.

---

## 🛠️ Practice (9 min)

### Step 1 — See the problem (no memory)

Create `no_memory.py`:

```python
from google import genai

client = genai.Client()

def ask(text):
    return client.models.generate_content(
        model="gemini-2.5-flash", contents=text
    ).text

print(ask("My name is Alex."))
print(ask("What's my name?"))   # It won't know — each call is independent
```

Run it — the second answer proves there's no memory.

### Step 2 — Add memory with a chat object

Create `chat_memory.py`:

```python
from google import genai

client = genai.Client()

# A chat object remembers the whole conversation for you
chat = client.chats.create(model="gemini-2.5-flash")

print(chat.send_message("My name is Alex and I love hiking.").text)
print(chat.send_message("What's my name and one gift idea for me?").text)  # Remembers
```

Run it — the second reply knows your name **and** uses the hiking detail. 🎉 The `chat` object stored every turn.

### Step 3 — Make it an interactive loop

Create `chat_loop.py`:

```python
from google import genai

client = genai.Client()
chat = client.chats.create(model="gemini-2.5-flash")

print("Chat with Gemini. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    reply = chat.send_message(user_text).text
    print("Gemini:", reply, "\n")
```

A real chatbot that remembers the whole conversation — and you never managed a list by hand.

### Step 4 — Peek at the stored history

Add this before `break`-ing out, or at the end:

```python
for message in chat.get_history():
    print(message.role, "→", message.parts[0].text[:60])
```

`chat.get_history()` shows the turns the object is keeping. That history **is** the memory.

---

## 🧩 What you learned

| Idea | Why it matters |
|------|----------------|
| `generate_content` is one-shot | No memory between calls |
| `client.chats.create(...)` | A chat object that stores history |
| `chat.send_message(text)` | Sends a turn *and* remembers it |
| `chat.get_history()` | Inspect the stored conversation |

> ⚠️ **Cost note:** the history grows and is resent each turn, so long chats use more tokens. Start a fresh chat object for a new topic.

---

## ✅ Checkpoint

- [ ] `no_memory.py` shows independent calls forgetting.
- [ ] `chat_memory.py` remembers across two turns.
- [ ] `chat_loop.py` runs as an interactive chatbot.

---

## 🎯 Homework

Add a **system instruction** so your bot has a personality. Create the chat with:
```python
from google.genai import types
chat = client.chats.create(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(system_instruction="You are a concise, encouraging coach."),
)
```
Notice it keeps that role across every turn.

---

## 💡 Key takeaways

- `client.chats` gives you memory for free — the chat object stores history.
- `send_message` sends a turn and remembers it; `get_history()` shows it.
- Long chats cost more tokens; start a new chat for a new topic.

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)
