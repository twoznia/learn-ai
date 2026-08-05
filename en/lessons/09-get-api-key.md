# Lesson 09 — Get Your Anthropic API Key

⏱️ **10 minutes** · Level: Beginner · Needs: an email, a way to add a little credit

[← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)

---

## 🧠 Theory (3 min)

Up to now you've *chatted* with Claude. To make **your own code** talk to Claude, you use the **API** (Application Programming Interface) — a doorway on the internet your programs knock on.

To use that doorway you need an **API key**: a long secret string like `sk-ant-...` that identifies and bills your account.

Two very important facts:

1. **The API is separate from your Claude.ai chat plan.** API usage is **pay-as-you-go** — you add a few dollars of credit and pay per token. A whole day of learning usually costs a few cents. (Details in Lesson 17.)
2. **An API key is a password.** Anyone with it can spend your money. **Never** share it, email it, screenshot it publicly, or paste it into a public GitHub repo.

---

## 🛠️ Practice (6 min)

### Step 1 — Create a Console account

1. Go to **https://console.anthropic.com**
2. Sign up / log in (you can use the same email as claude.ai).

> ℹ️ The **Console** (console.anthropic.com) is the *developer* dashboard. It's different from the *chat* app (claude.ai). You manage API keys and billing here.

### Step 2 — Add a little credit

1. In the Console, find **Billing** (or **Plans & Billing**).
2. Add a small amount — **$5 is plenty** for this whole course.
3. You may also set a **monthly spend limit** (e.g. $5) so you can never be surprised. Do it — it's peace of mind.

### Step 3 — Create your API key

1. Go to **API Keys** (in the settings/left menu).
2. Click **Create Key**. Name it something like `learn-ai-course`.
3. **Copy the key now** — you usually can't see it again after closing the dialog. If you lose it, just create a new one.

### Step 4 — Store the key safely (as an environment variable)

Don't paste the key into your code. Instead store it in Windows as an **environment variable** named `ANTHROPIC_API_KEY`. Your scripts will read it automatically.

Open **PowerShell** and run (replace with your real key):

```powershell
setx ANTHROPIC_API_KEY "sk-ant-PASTE-YOUR-KEY-HERE"
```

You'll see `SUCCESS: Specified value was saved.`

> `setx` saves it permanently for future terminals. **Close and reopen PowerShell** for it to take effect.

### Step 5 — Verify it's saved

Open a **new** PowerShell window and run:

```powershell
echo $env:ANTHROPIC_API_KEY
```

You should see your key printed. ✅ (If it's blank, reopen PowerShell — `setx` only affects *new* windows.)

---

## 🔒 API key safety rules

| ✅ Do | ❌ Don't |
|------|---------|
| Store in an environment variable | Hard-code it in scripts you share |
| Set a monthly spend limit | Post it in chats, issues, or repos |
| Delete/rotate a leaked key immediately | Email or screenshot it publicly |
| Use one key per project | Reuse a key you suspect leaked |

If a key ever leaks: go to the Console → API Keys → **delete/revoke it**, then make a new one. Done.

---

## ✅ Checkpoint

- [ ] You have a Console account with a small credit balance.
- [ ] You created an API key and copied it.
- [ ] `setx ANTHROPIC_API_KEY "..."` succeeded.
- [ ] `echo $env:ANTHROPIC_API_KEY` (in a new window) shows your key.
- [ ] You set a monthly spend limit.

---

## 🎯 Homework

Double-check your spend limit is set. Then read one line of the Console's **Usage** page so you know where to watch your spending later.

---

## 💡 Key takeaways

- The **API** lets your code use Claude; it needs an **API key**.
- API billing is **pay-as-you-go**, separate from chat plans.
- Store the key as the `ANTHROPIC_API_KEY` environment variable — never in shared code.
- Treat the key like a password; set a spend limit.

[← Prev](08-install-python.md) · [Course home](../README.md) · [Next: First Python script →](10-python-first-script.md)
