# B2 — Streaming Responses

⏱️ **15 minutes** · Track: 🅱️ Builder · Needs: Python + `google-genai` + API key

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)

---

## 🧠 Theory (4 min)

`generate_content(...)` makes your program **wait** for the whole reply, then print it at once. For long answers that's an awkward silent pause.

**Streaming** delivers the reply **as it's generated**, word by word — like the Gemini app. Same result, much better feel. The `google-genai` library gives you streaming variants:

- `client.models.generate_content_stream(...)` for one-shot streaming.
- `chat.send_message_stream(...)` for streaming inside a chat with memory.

Both yield **chunks**; each chunk has a `.text` you print immediately.

---

## 🛠️ Practice (9 min)

### Step 1 — Compare non-streaming vs streaming

Create `stream_demo.py`:

```python
from google import genai

client = genai.Client()
prompt = "Write a short, upbeat paragraph about learning to code."

# --- Non-streaming: waits, then prints all at once ---
print("=== NON-STREAMING ===")
print(client.models.generate_content(model="gemini-2.5-flash", contents=prompt).text)

# --- Streaming: appears chunk by chunk ---
print("\n=== STREAMING ===")
for chunk in client.models.generate_content_stream(
    model="gemini-2.5-flash", contents=prompt
):
    print(chunk.text, end="", flush=True)
print()
```

Run it:

```powershell
python stream_demo.py
```

Watch the second version type itself out. `flush=True` forces each chunk to show immediately.

### Step 2 — Streaming inside a chat (memory + streaming)

Create `chat_stream.py`:

```python
from google import genai

client = genai.Client()
chat = client.chats.create(model="gemini-2.5-flash")

print("Streaming chat. Type 'quit' to exit.\n")

while True:
    user_text = input("You: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    print("Gemini: ", end="", flush=True)
    for chunk in chat.send_message_stream(user_text):
        print(chunk.text, end="", flush=True)
    print("\n")
```

`send_message_stream` streams the reply **and** the chat object still remembers it — you get live typing *and* memory in one call.

### Step 3 — Collect the full text while streaming

Sometimes you want to stream to the screen **and** keep the whole reply (to save it):

```python
from google import genai

client = genai.Client()

pieces = []
for chunk in client.models.generate_content_stream(
    model="gemini-2.5-flash", contents="Give me 3 study tips."
):
    print(chunk.text, end="", flush=True)
    pieces.append(chunk.text)

full_reply = "".join(pieces)
print("\n\n[Captured", len(full_reply), "characters]")
```

Joining the chunks gives you the complete text to log or save.

---

## 🧩 Streaming essentials

| Piece | What it does |
|-------|--------------|
| `generate_content_stream(...)` | One-shot streaming |
| `chat.send_message_stream(...)` | Streaming with memory |
| `for chunk in ...: chunk.text` | Each incremental piece |
| `print(text, end="", flush=True)` | Show each chunk immediately |
| `"".join(pieces)` | Rebuild the full reply |

---

## ✅ Checkpoint

- [ ] You saw non-streaming vs streaming side by side.
- [ ] `chat_stream.py` streams **and** remembers.
- [ ] You captured a full reply by joining chunks.

---

## 🎯 Homework

Add a `system_instruction` (via `config=`) to `chat_stream.py` so your streaming bot has a role. Now you have a chatbot with personality, memory, and live typing.

---

## 💡 Key takeaways

- Streaming shows the reply **as it's written** — same result, better UX.
- Use `generate_content_stream` (one-shot) or `send_message_stream` (with memory).
- Join the chunks' `.text` to keep the full reply.

🌐 [Polski](../../pl/track-b/02-streaming.md) · [← Prev](01-conversations-with-memory.md) · [Track index](../README.md) · [Next: Build an app →](03-build-an-app.md)
