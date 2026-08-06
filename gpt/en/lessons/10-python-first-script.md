# Lesson 10 — Your First Python Script with GPT

⏱️ **10 minutes** · Level: Beginner · Needs: Python (L8), API key set (L9)

🌐 [Polski](../../pl/lessons/10-python-pierwszy-skrypt.md) · [← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)

---

## 🧠 Theory (2 min)

You'll now make **your own program** talk to GPT. The steps are always the same:

1. **Install** the official library (`openai`).
2. **Create a client** (it reads your `OPENAI_API_KEY` automatically).
3. **Send messages** and print the reply.

We'll use a **mini** model — fast and cheap — so learning costs a fraction of a cent. Model IDs you can use (check **platform.openai.com/docs/models** for the current list):

| Model | ID (copy exactly) | Good for |
|-------|-------------------|----------|
| Mini (cheapest) | `gpt-5-mini` | Learning, simple tasks |
| Flagship (smartest) | `gpt-5` | Hard reasoning/coding |

> If `gpt-5-mini` isn't available on your account, `gpt-4o-mini` is a widely available cheap alternative — just swap the string.

---

## 🛠️ Practice (7 min)

### Step 1 — Install the library

Open **PowerShell** and go to your course folder:

```powershell
cd $HOME\learn-ai-gpt
pip install openai
```

This takes ~30 seconds.

### Step 2 — Create the script

```powershell
notepad first_gpt.py
```

Click **Yes** to create it, then **paste this in** and save (Ctrl+S):

```python
from openai import OpenAI

# The client automatically reads your OPENAI_API_KEY environment variable
client = OpenAI()

# Send one message to GPT
response = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[
        {"role": "user", "content": "Say hello and give me one fun fact about the moon."}
    ],
)

# Print the text reply
print(response.choices[0].message.content)
```

### Step 3 — Run it

```powershell
python first_gpt.py
```

🎉 You should see GPT greet you and share a moon fact. **You just built an AI app.**

### Step 4 — Make it interactive

Create `chat_once.py`:

```powershell
notepad chat_once.py
```

Paste and save:

```python
from openai import OpenAI

client = OpenAI()

# Ask the user for input
question = input("Ask GPT anything: ")

response = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[
        {"role": "user", "content": question}
    ],
)

print("\nGPT says:\n" + response.choices[0].message.content)
```

Run it:

```powershell
python chat_once.py
```

Type a question, press Enter, and GPT answers. 🙌

---

## 🧩 Understanding the code (1 min)

| Line | What it does |
|------|--------------|
| `from openai import OpenAI` | Loads the library |
| `OpenAI()` | Connects using your key |
| `model="gpt-5-mini"` | Picks which GPT to use |
| `messages=[{"role": "user", ...}]` | Your prompt |
| `response.choices[0].message.content` | The text answer, ready to print |

> 💡 Want a "role"/system prompt? Add a system message first:
> ```python
> messages=[
>     {"role": "system", "content": "You are a friendly tutor. Explain simply."},
>     {"role": "user", "content": "What is an API?"},
> ]
> ```

---

## ✅ Checkpoint

- [ ] `pip install openai` succeeded.
- [ ] `first_gpt.py` printed a reply.
- [ ] `chat_once.py` answered a question you typed.

---

## 🎯 Homework

Change the model in `first_gpt.py` from `gpt-5-mini` to `gpt-5`, run it again, and notice the (usually richer) answer. Then switch back to mini to keep costs tiny.

---

## 💡 Key takeaways

- Three steps: install → client → `chat.completions.create`.
- The reply text is `response.choices[0].message.content`.
- Use a **mini** model while learning; switch by changing one string.
- Add a `{"role": "system", ...}` message to set a role.

🌐 [Polski](../../pl/lessons/10-python-pierwszy-skrypt.md) · [← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)
