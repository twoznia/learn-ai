# Lesson 10 — Your First Python Script with Claude

⏱️ **10 minutes** · Level: Beginner · Needs: Python (L8), API key set (L9)

[← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)

---

## 🧠 Theory (2 min)

You'll now make **your own program** talk to Claude. The steps are always the same:

1. **Install** the official library (`anthropic`).
2. **Create a client** (it reads your `ANTHROPIC_API_KEY` automatically).
3. **Send a message** and print the reply.

We'll use **Claude Haiku** — the fast, cheapest model — so learning costs a fraction of a cent. Model IDs you can use:

| Model | ID (copy exactly) | Good for |
|-------|-------------------|----------|
| Haiku (cheapest) | `claude-haiku-4-5` | Learning, simple tasks |
| Sonnet (balanced) | `claude-sonnet-5` | Everyday work |
| Opus (smartest) | `claude-opus-5` | Hard reasoning/coding |

---

## 🛠️ Practice (7 min)

### Step 1 — Install the library

Open **PowerShell** and go to your course folder:

```powershell
cd $HOME\learn-ai-claude
pip install anthropic
```

You'll see it download and install. This takes ~30 seconds.

### Step 2 — Create the script

We'll create a file called `first_claude.py`. Run this to create it in Notepad:

```powershell
notepad first_claude.py
```

Click **Yes** to create it, then **paste this in** and save (Ctrl+S):

```python
import anthropic

# The client automatically reads your ANTHROPIC_API_KEY environment variable
client = anthropic.Anthropic()

# Send one message to Claude
response = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=300,
    messages=[
        {"role": "user", "content": "Say hello and give me one fun fact about the moon."}
    ],
)

# The reply comes back in "content blocks" — print the text
for block in response.content:
    if block.type == "text":
        print(block.text)
```

### Step 3 — Run it

Back in PowerShell:

```powershell
python first_claude.py
```

🎉 You should see Claude greet you and share a moon fact. **You just built an AI app.**

### Step 4 — Make it interactive

Let's make it ask *you* a question. Create `chat_once.py`:

```powershell
notepad chat_once.py
```

Paste and save:

```python
import anthropic

client = anthropic.Anthropic()

# Ask the user for input
question = input("Ask Claude anything: ")

response = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=500,
    messages=[
        {"role": "user", "content": question}
    ],
)

for block in response.content:
    if block.type == "text":
        print("\nClaude says:\n" + block.text)
```

Run it:

```powershell
python chat_once.py
```

Type a question, press Enter, and Claude answers. 🙌

---

## 🧩 Understanding the code (1 min)

| Line | What it does |
|------|--------------|
| `import anthropic` | Loads the library |
| `anthropic.Anthropic()` | Connects using your key |
| `model="claude-haiku-4-5"` | Picks which Claude to use |
| `max_tokens=300` | Caps the reply length (cost control) |
| `messages=[{"role": "user", ...}]` | Your prompt |
| `for block in response.content` | Reads the reply (it's a list of blocks) |

---

## ✅ Checkpoint

- [ ] `pip install anthropic` succeeded.
- [ ] `first_claude.py` printed a reply.
- [ ] `chat_once.py` answered a question you typed.

---

## 🎯 Homework

Change the model in `first_claude.py` from `claude-haiku-4-5` to `claude-sonnet-5`, run it again, and notice the (usually richer) answer. Then switch it back to Haiku to keep costs tiny.

---

## 💡 Key takeaways

- Three steps: install → client → `messages.create`.
- Replies live in `response.content`; loop and print `block.text`.
- Use **Haiku** while learning; switch models by changing one string.
- `max_tokens` limits reply length and cost.

[← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)
