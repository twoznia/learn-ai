# Lesson 10 — Your First Python Script with Gemini

⏱️ **10 minutes** · Level: Beginner · Needs: Python (L8), API key set (L9)

🌐 [Polski](../../pl/lessons/10-python-pierwszy-skrypt.md) · [← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)

---

## 🧠 Theory (2 min)

You'll now make **your own program** talk to Gemini. The steps are always the same:

1. **Install** the official library (`google-genai`).
2. **Create a client** (it reads your `GEMINI_API_KEY` automatically).
3. **Generate content** and print the reply.

We'll use **Gemini Flash** — fast and covered by the free tier — so learning is essentially free. Model IDs you can use:

| Model | ID (copy exactly) | Good for |
|-------|-------------------|----------|
| Flash-Lite (cheapest) | `gemini-2.5-flash-lite` | High volume, simple tasks |
| Flash (balanced) | `gemini-2.5-flash` | Learning, everyday work |
| Pro (smartest) | `gemini-2.5-pro` | Hard reasoning/coding |

---

## 🛠️ Practice (7 min)

### Step 1 — Install the library

Open **PowerShell** and go to your course folder:

```powershell
cd $HOME\learn-ai-gemini
pip install google-genai
```

This takes ~30 seconds.

### Step 2 — Create the script

```powershell
notepad first_gemini.py
```

Click **Yes** to create it, then **paste this in** and save (Ctrl+S):

```python
from google import genai

# The client automatically reads your GEMINI_API_KEY environment variable
client = genai.Client()

# Send one message to Gemini
response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents="Say hello and give me one fun fact about the moon.",
)

# Print the text reply
print(response.text)
```

### Step 3 — Run it

```powershell
python first_gemini.py
```

🎉 You should see Gemini greet you and share a moon fact. **You just built an AI app.**

### Step 4 — Make it interactive

Create `chat_once.py`:

```powershell
notepad chat_once.py
```

Paste and save:

```python
from google import genai

client = genai.Client()

# Ask the user for input
question = input("Ask Gemini anything: ")

response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents=question,
)

print("\nGemini says:\n" + response.text)
```

Run it:

```powershell
python chat_once.py
```

Type a question, press Enter, and Gemini answers. 🙌

---

## 🧩 Understanding the code (1 min)

| Line | What it does |
|------|--------------|
| `from google import genai` | Loads the library |
| `genai.Client()` | Connects using your key |
| `model="gemini-2.5-flash"` | Picks which Gemini to use |
| `contents="..."` | Your prompt |
| `response.text` | The text answer, ready to print |

> 💡 Want a "role"/system instruction? Add a config:
> ```python
> from google.genai import types
> response = client.models.generate_content(
>     model="gemini-2.5-flash",
>     config=types.GenerateContentConfig(
>         system_instruction="You are a friendly tutor. Explain simply."
>     ),
>     contents="What is an API?",
> )
> ```

---

## ✅ Checkpoint

- [ ] `pip install google-genai` succeeded.
- [ ] `first_gemini.py` printed a reply.
- [ ] `chat_once.py` answered a question you typed.

---

## 🎯 Homework

Change the model in `first_gemini.py` from `gemini-2.5-flash` to `gemini-2.5-pro`, run it again, and notice the (usually richer) answer. Then switch back to Flash to stay on the free tier.

---

## 💡 Key takeaways

- Three steps: install → client → `generate_content`.
- The reply text is simply `response.text`.
- Use **Flash** while learning; switch models by changing one string.
- Add a `system_instruction` via `GenerateContentConfig` to set a role.

🌐 [Polski](../../pl/lessons/10-python-pierwszy-skrypt.md) · [← Prev](09-get-api-key.md) · [Course home](../README.md) · [Next: PowerShell →](11-powershell.md)
