# B1 — Conversations with Memory

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `openai` + API key (beginner course)

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)

---

## 🧠 Theory (4 min)

In the beginner course, each script sent **one** message and got **one** reply. But the API is **stateless** — it doesn't remember anything between calls. So how does ChatGPT-style "it remembers what I said" work?

**You** keep the memory. You maintain a **list of messages** and send the *whole conversation* every time. Each turn you append two things:

1. the **user** message,
2. GPT's **assistant** reply.

Next request includes all of it, so GPT "remembers." Memory is just the growing `messages` list.

```
messages = [ user, assistant, user, assistant, user ]  →  send all  →  new assistant reply
```

---

## 🛠️ Practice (9 min)

### Step 1 — See the problem (no memory)

Create `no_memory.py`:

```python
from openai import OpenAI

client = OpenAI()

def ask(text):
    resp = client.chat.completions.create(
        model="gpt-5-mini",
        messages=[{"role": "user", "content": text}],
    )
    return resp.choices[0].message.content

print(ask("My name is Alex."))
print(ask("What's my name?"))   # It won't know — no memory
```

Run it — the second answer proves the API forgot.

### Step 2 — Add memory with a message list

Create `chat_memory.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []  # this list IS the memory

def chat(user_text):
    messages.append({"role": "user", "content": user_text})     # 1. user turn
    resp = client.chat.completions.create(                       # 2. send WHOLE history
        model="gpt-5-mini",
        messages=messages,
    )
    reply = resp.choices[0].message.content
    messages.append({"role": "assistant", "content": reply})    # 3. remember reply
    return reply

print(chat("My name is Alex and I love hiking."))
print(chat("What's my name and one gift idea for me?"))  # Now it remembers
```

Run it — the second answer knows your name **and** uses the hiking detail. 🎉

### Step 3 — Make it an interactive loop

Create `chat_loop.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []

print("Chat with GPT. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    messages.append({"role": "user", "content": user_text})
    resp = client.chat.completions.create(model="gpt-5-mini", messages=messages)
    reply = resp.choices[0].message.content
    messages.append({"role": "assistant", "content": reply})
    print("GPT:", reply, "\n")
```

A real chatbot that remembers the whole conversation.

---

## 🧩 What you learned

| Idea | Why it matters |
|------|----------------|
| The API is **stateless** | You must resend history each call |
| The `messages` list **is** the memory | Append user + assistant every turn |
| Roles `user`/`assistant`/`system` | How GPT tracks who said what |

> ⚠️ **Cost note:** every turn resends the whole history, so long chats cost more tokens. Trim old turns later if needed.

---

## ✅ Checkpoint

- [ ] `no_memory.py` shows the API forgetting.
- [ ] `chat_memory.py` remembers across two turns.
- [ ] `chat_loop.py` runs as an interactive chatbot.

---

## 🎯 Homework

Add a **system message** as the first item in `messages` so your bot has a consistent personality:
```python
messages = [{"role": "system", "content": "You are a concise, encouraging coach."}]
```
Notice it keeps that role across every turn.

---

## 💡 Key takeaways

- Memory = **you** resending a growing `messages` list each call.
- Append both the user turn and GPT's reply every round.
- A `system` message at the front sets a lasting role.

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)
