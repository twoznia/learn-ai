# Lesson 09 — Get Your Google AI Studio API Key

⏱️ **10 minutes** · Level: Beginner · Needs: a Google account

🌐 [Polski](../../pl/lessons/09-klucz-api.md) · [← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)

---

## 🧠 Theory (3 min)

Up to now you've *chatted* with Gemini. To make **your own code** talk to Gemini, you use the **API** (Application Programming Interface) — a doorway on the internet your programs knock on.

To use that doorway you need an **API key**: a secret string that identifies your account.

Two important facts:

1. **Google AI Studio has a free tier.** For learning, you can usually get a key and make requests **without adding billing** (with rate limits). Perfect for this course. Paid usage is available when you need more.
2. **An API key is a password.** Anyone with it can use your quota (and spend money if billing is on). **Never** share it, email it, screenshot it publicly, or paste it into a public GitHub repo.

---

## 🛠️ Practice (6 min)

### Step 1 — Open Google AI Studio

1. Go to **https://aistudio.google.com**
2. Sign in with your Google account and accept the terms if prompted.

> ℹ️ **Google AI Studio** (aistudio.google.com) is the developer playground and key manager. It's different from the Gemini *chat* app (gemini.google.com).

### Step 2 — Create your API key

1. Click **Get API key** (top-left or in the menu).
2. Click **Create API key**. If asked to pick or create a Google Cloud project, accept the default it offers.
3. **Copy the key now** and keep it somewhere safe for a moment.

> Free-tier keys work immediately. You only need billing if you exceed the free limits (Lesson 17 covers this).

### Step 3 — Store the key safely (as an environment variable)

Don't paste the key into your code. Store it in Windows as an **environment variable** named `GEMINI_API_KEY`. Your scripts will read it automatically.

Open **PowerShell** and run (replace with your real key):

```powershell
setx GEMINI_API_KEY "PASTE-YOUR-KEY-HERE"
```

You'll see `SUCCESS: Specified value was saved.`

> `setx` saves it permanently for future terminals. **Close and reopen PowerShell** for it to take effect.

### Step 4 — Verify it's saved

Open a **new** PowerShell window and run:

```powershell
echo $env:GEMINI_API_KEY
```

You should see your key. ✅ (If it's blank, reopen PowerShell — `setx` only affects *new* windows.)

---

## 🔒 API key safety rules

| ✅ Do | ❌ Don't |
|------|---------|
| Store in an environment variable | Hard-code it in scripts you share |
| Watch usage/limits in AI Studio | Post it in chats, issues, or repos |
| Delete/rotate a leaked key immediately | Email or screenshot it publicly |
| Use one key per project | Reuse a key you suspect leaked |

If a key ever leaks: in AI Studio → **API keys** → **delete/revoke it**, then create a new one.

---

## ✅ Checkpoint

- [ ] You have a Google AI Studio account.
- [ ] You created an API key and copied it.
- [ ] `setx GEMINI_API_KEY "..."` succeeded.
- [ ] `echo $env:GEMINI_API_KEY` (in a new window) shows your key.

---

## 🎯 Homework

In AI Studio, open the **prompt playground** and send one test prompt right there in the browser — it's a great way to try models before writing code. Note which model is selected (e.g. `gemini-2.5-flash`).

---

## 💡 Key takeaways

- The **API** lets your code use Gemini; it needs an **API key** from Google AI Studio.
- There's a **free tier** — often no billing needed for learning.
- Store the key as the `GEMINI_API_KEY` environment variable — never in shared code.
- Treat the key like a password; rotate it if it leaks.

🌐 [Polski](../../pl/lessons/09-klucz-api.md) · [← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)
