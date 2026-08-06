# B2 — Streaming Responses

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `anthropic` + API key

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)

---

## 🧠 Theory (4 min)

When you call `messages.create(...)`, your program **waits** for the entire reply, then prints it all at once. For a long answer, that's an awkward silent pause.

**Streaming** delivers the reply **as it's generated**, word by word — exactly like you see in the Claude app. Same result, much better feel. It also lets you show progress and start reading sooner.

The `anthropic` library makes it easy with `client.messages.stream(...)` and a `for` loop over `stream.text_stream`.

---

## 🛠️ Practice (9 min)

### Step 1 — Compare: non-streaming vs streaming

Create `stream_demo.py`:

```python
import anthropic

client = anthropic.Anthropic()

prompt = "Write a short, upbeat paragraph about learning to code."

# --- Non-streaming: one big wait, then all at once ---
print("=== NON-STREAMING (waits, then prints) ===")
resp = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": prompt}],
)
print(resp.content[0].text)

# --- Streaming: appears word by word ---
print("\n=== STREAMING (appears as it's written) ===")
with client.messages.stream(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": prompt}],
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
print()
```

Run it:

```powershell
python stream_demo.py
```

Watch the difference — the second version types itself out. `flush=True` forces each chunk to show immediately.

### Step 2 — Get the full text after streaming

Sometimes you want to stream to the screen **and** keep the whole reply (e.g. to save it or add to memory):

```python
import anthropic

client = anthropic.Anthropic()

with client.messages.stream(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": "Give me 3 study tips."}],
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)

    final = stream.get_final_message()   # the complete message object

print("\n\n[Tokens used:", final.usage.output_tokens, "]")
```

`get_final_message()` gives you the assembled reply plus usage info — handy for logging cost.

### Step 3 — Streaming + memory (combine B1 and B2)

Create `chat_stream.py` — a chatbot that streams *and* remembers:

```python
import anthropic

client = anthropic.Anthropic()
messages = []

print("Streaming chat. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    messages.append({"role": "user", "content": user_text})

    print("Claude: ", end="", flush=True)
    with client.messages.stream(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=messages,
    ) as stream:
        for text in stream.text_stream:
            print(text, end="", flush=True)
        reply = stream.get_final_message().content[0].text

    messages.append({"role": "assistant", "content": reply})
    print("\n")
```

Now it feels like the real Claude app: replies stream in, and it remembers.

---

## 🧩 Streaming essentials

| Piece | What it does |
|-------|--------------|
| `with client.messages.stream(...) as stream:` | Opens the stream |
| `for text in stream.text_stream:` | Yields chunks of text |
| `print(text, end="", flush=True)` | Prints each chunk immediately |
| `stream.get_final_message()` | The full message + usage after streaming |

---

## ✅ Checkpoint

- [ ] You saw non-streaming vs streaming side by side.
- [ ] You captured the full reply with `get_final_message()`.
- [ ] `chat_stream.py` streams **and** remembers the conversation.

---

## 🎯 Homework

Add a `system` prompt to `chat_stream.py` so your streaming bot has a role, and print the running token total after each turn (from `get_final_message().usage`). Now you have a chatbot with personality, live typing, and cost awareness.

---

## 💡 Key takeaways

- Streaming shows the reply **as it's written** — same result, better UX.
- Use `messages.stream(...)` + `for text in stream.text_stream`.
- `get_final_message()` gives you the full text and usage to save or log.

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)
