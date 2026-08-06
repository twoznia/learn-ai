# Lesson 09 — Get Your OpenAI API Key

⏱️ **10 minutes** · Level: Beginner · Needs: an email, a way to add a little credit

🌐 [Polski](../../pl/lessons/09-klucz-api.md) · [← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)

---

## 🧠 Theory (3 min)

Up to now you've *chatted* with ChatGPT. To make **your own code** talk to GPT, you use the **API** (Application Programming Interface) — a doorway on the internet your programs knock on.

To use that doorway you need an **API key**: a secret string like `sk-...` that identifies and bills your account.

Two important facts:

1. **The API is separate from your ChatGPT subscription.** API usage is **pay-as-you-go** — you add a small prepaid balance and pay per token. A whole day of learning usually costs a few cents.
2. **An API key is a password.** Anyone with it can spend your money. **Never** share it, email it, screenshot it publicly, or paste it into a public GitHub repo.

---

## 🛠️ Practice (6 min)

### Step 1 — Open the OpenAI Platform

1. Go to **https://platform.openai.com**
2. Sign in / sign up (you can use the same login as ChatGPT).

> ℹ️ The **Platform** (platform.openai.com) is the *developer* dashboard for API keys and billing. It's different from the *chat* app (chatgpt.com).

### Step 2 — Add a little credit

1. Go to **Settings → Billing**.
2. Add a small amount — **$5 is plenty** for this whole course.
3. Consider setting a **usage limit** (e.g. $5/month) so you can't be surprised. Do it — it's peace of mind.

### Step 3 — Create your API key

1. Go to **API keys** (in the dashboard menu).
2. Click **Create new secret key**. Name it e.g. `learn-ai-course`.
3. **Copy the key now** — you usually can't see it again after closing the dialog. If you lose it, just create a new one.

### Step 4 — Store the key safely (as an environment variable)

Don't paste the key into your code. Store it in Windows as an **environment variable** named `OPENAI_API_KEY`. Your scripts will read it automatically.

Open **PowerShell** and run (replace with your real key):

```powershell
setx OPENAI_API_KEY "sk-PASTE-YOUR-KEY-HERE"
```

You'll see `SUCCESS: Specified value was saved.`

> `setx` saves it permanently for future terminals. **Close and reopen PowerShell** for it to take effect.

### Step 5 — Verify it's saved

Open a **new** PowerShell window and run:

```powershell
echo $env:OPENAI_API_KEY
```

You should see your key. ✅ (If it's blank, reopen PowerShell — `setx` only affects *new* windows.)

---

## 🔒 API key safety rules

| ✅ Do | ❌ Don't |
|------|---------|
| Store in an environment variable | Hard-code it in scripts you share |
| Set a usage/spend limit | Post it in chats, issues, or repos |
| Delete/rotate a leaked key immediately | Email or screenshot it publicly |
| Use one key per project | Reuse a key you suspect leaked |

If a key ever leaks: Platform → **API keys** → **revoke it**, then make a new one.

---

## ✅ Checkpoint

- [ ] You have a Platform account with a small credit balance.
- [ ] You created an API key and copied it.
- [ ] `setx OPENAI_API_KEY "..."` succeeded.
- [ ] `echo $env:OPENAI_API_KEY` (in a new window) shows your key.
- [ ] You set a usage limit.

---

## 🎯 Homework

Double-check your usage limit is set. Then open the **Usage** page on the Platform so you know where to watch your spending later.

---

## 💡 Key takeaways

- The **API** lets your code use GPT; it needs an **API key** from platform.openai.com.
- API billing is **pay-as-you-go**, separate from the ChatGPT subscription.
- Store the key as the `OPENAI_API_KEY` environment variable — never in shared code.
- Treat the key like a password; set a spend limit.

🌐 [Polski](../../pl/lessons/09-klucz-api.md) · [← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)
