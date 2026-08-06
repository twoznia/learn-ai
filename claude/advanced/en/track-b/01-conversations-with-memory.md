# B1 — Conversations with Memory

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `anthropic` + API key (beginner course)

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)

---

## 🧠 Theory (4 min)

In the beginner course, each script sent **one** message and got **one** reply. But the API is **stateless** — it doesn't remember anything between calls. So how does the ChatGPT-style "it remembers what I said" work?

**You** keep the memory. You maintain a **list of messages** and send the *whole conversation* every time. Each turn you append two things:

1. the **user** message,
2. Claude's **assistant** reply.

Next request includes all of it, so Claude "remembers." Memory is just the growing `messages` list.

```
messages = [ user, assistant, user, assistant, user ]  →  send all  →  new assistant reply
```

---

## 🛠️ Practice (9 min)

### Step 1 — A one-shot with no memory (to see the problem)

Create `no_memory.py` in your course folder:

```python
import anthropic

client = anthropic.Anthropic()

def ask(text):
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=300,
        messages=[{"role": "user", "content": text}],
    )
    return resp.content[0].text

print(ask("My name is Alex."))
print(ask("What's my name?"))   # It won't know — no memory
```

Run it — the second answer proves the API forgot.

### Step 2 — Add memory with a message list

Create `chat_memory.py`:

```python
import anthropic

client = anthropic.Anthropic()

messages = []  # this list IS the memory

def chat(user_text):
    # 1. add the user's turn
    messages.append({"role": "user", "content": user_text})

    # 2. send the WHOLE conversation
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=500,
        messages=messages,
    )
    reply = resp.content[0].text

    # 3. save the assistant's turn so it's remembered next time
    messages.append({"role": "assistant", "content": reply})
    return reply

print(chat("My name is Alex and I love hiking."))
print(chat("What's my name and one gift idea for me?"))  # Now it remembers
```

Run it — the second answer knows your name **and** uses the hiking detail. 🎉

### Step 3 — Make it a real interactive loop

Create `chat_loop.py`:

```python
import anthropic

client = anthropic.Anthropic()
messages = []

print("Chat with Claude. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    messages.append({"role": "user", "content": user_text})
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=messages,
    )
    reply = resp.content[0].text
    messages.append({"role": "assistant", "content": reply})
    print("Claude:", reply, "\n")
```

Now you have a real chatbot that remembers the whole conversation.

---

## 🧩 What you learned

| Idea | Why it matters |
|------|----------------|
| The API is **stateless** | You must resend history each call |
| The `messages` list **is** the memory | Append user + assistant every turn |
| Roles alternate `user`/`assistant` | That's how Claude tracks who said what |

> ⚠️ **Cost note:** every turn resends the whole history, so long chats cost more tokens. Later you can trim old turns or summarize them — but for learning, this is exactly right.

---

## ✅ Checkpoint

- [ ] `no_memory.py` shows the API forgetting.
- [ ] `chat_memory.py` remembers across two turns.
- [ ] `chat_loop.py` runs as an interactive chatbot.

---

## 🎯 Homework

Add a **system prompt** to `chat_loop.py` (the `system="..."` parameter) so your bot has a consistent personality — e.g. "You are a concise, encouraging coach." Notice it keeps that role across every turn.

---

## 💡 Key takeaways

- Memory = **you** resending a growing `messages` list each call.
- Append both the user turn and Claude's reply every round.
- Long conversations cost more tokens (resent history) — trim later if needed.

🌐 [Polski](../../pl/track-b/01-rozmowy-z-pamiecia.md) · [← Track index](../README.md) · [Next: Streaming →](02-streaming.md)
