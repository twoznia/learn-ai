# B2 — Streaming Responses

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `openai` + API key

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)

---

## 🧠 Theory (4 min)

By default, `chat.completions.create(...)` makes your program **wait** for the whole reply, then print it at once. For a long answer that's an awkward silent pause.

**Streaming** delivers the reply **as it's generated**, word by word — like the ChatGPT app. You turn it on with `stream=True`, then loop over the chunks. Each chunk carries a small piece of text at `chunk.choices[0].delta.content`.

---

## 🛠️ Practice (9 min)

### Step 1 — Compare non-streaming vs streaming

Create `stream_demo.py`:

```python
from openai import OpenAI

client = OpenAI()
prompt = "Write a short, upbeat paragraph about learning to code."

# --- Non-streaming: waits, then prints all at once ---
print("=== NON-STREAMING ===")
resp = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": prompt}],
)
print(resp.choices[0].message.content)

# --- Streaming: appears chunk by chunk ---
print("\n=== STREAMING ===")
stream = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": prompt}],
    stream=True,
)
for chunk in stream:
    piece = chunk.choices[0].delta.content
    if piece:                      # some chunks have no text — skip them
        print(piece, end="", flush=True)
print()
```

Run it:

```powershell
python stream_demo.py
```

Watch the second version type itself out. `flush=True` forces each chunk to show immediately. The `if piece:` guard skips empty chunks (the stream sends a few).

### Step 2 — Collect the full text while streaming

Stream to the screen **and** keep the whole reply (to save it or add to memory):

```python
from openai import OpenAI

client = OpenAI()

pieces = []
stream = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": "Give me 3 study tips."}],
    stream=True,
)
for chunk in stream:
    piece = chunk.choices[0].delta.content
    if piece:
        print(piece, end="", flush=True)
        pieces.append(piece)

full_reply = "".join(pieces)
print("\n\n[Captured", len(full_reply), "characters]")
```

### Step 3 — Streaming + memory (combine B1 and B2)

Create `chat_stream.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []

print("Streaming chat. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    messages.append({"role": "user", "content": user_text})

    print("GPT: ", end="", flush=True)
    pieces = []
    stream = client.chat.completions.create(
        model="gpt-5-mini", messages=messages, stream=True,
    )
    for chunk in stream:
        piece = chunk.choices[0].delta.content
        if piece:
            print(piece, end="", flush=True)
            pieces.append(piece)

    reply = "".join(pieces)
    messages.append({"role": "assistant", "content": reply})
    print("\n")
```

Now it feels like the real ChatGPT app: replies stream in, and it remembers.

---

## 🧩 Streaming essentials

| Piece | What it does |
|-------|--------------|
| `stream=True` | Turns on streaming |
| `for chunk in stream:` | Yields chunks |
| `chunk.choices[0].delta.content` | The incremental text (may be empty) |
| `if piece:` | Skip empty chunks |
| `"".join(pieces)` | Rebuild the full reply |

---

## ✅ Checkpoint

- [ ] You saw non-streaming vs streaming side by side.
- [ ] You captured the full reply by joining chunks.
- [ ] `chat_stream.py` streams **and** remembers.

---

## 🎯 Homework

Add a `system` message to `chat_stream.py` so your streaming bot has a role. Now you have a chatbot with personality, memory, and live typing.

---

## 💡 Key takeaways

- Streaming shows the reply **as it's written** — same result, better UX.
- Set `stream=True` and read `chunk.choices[0].delta.content` (guard empty ones).
- Join the pieces to keep the full reply for memory or saving.

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)
