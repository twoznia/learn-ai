# Lesson 17 — Costs, Limits, Privacy, and Safety

⏱️ **10 minutes** · Level: Beginner · Needs: nothing to install

🌐 [Polski](../../pl/lessons/17-koszty-bezpieczenstwo.md) · [← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)

---

## 🧠 Theory (5 min)

### How pricing works

The **ChatGPT app** uses a **subscription**: a free tier, or paid plans (Plus/Pro) for more usage and top models. Simple and predictable.

The **API** (your Python/PowerShell code) is **pay-as-you-go**, billed **per token** (a token ≈ ¾ of a word), separately for input and output. You add a small prepaid balance and it draws down as you use it.

Rough idea of relative cost (mini/nano < flagship):

| Model | Cost | Feel |
|-------|------|------|
| **nano / mini** (e.g. `gpt-5-mini`) | Cheapest | Fast, simple tasks |
| **flagship** (e.g. `gpt-5`) | Higher | Most capable |

> A typical learning request (a few hundred words each way) costs a **tiny fraction of a cent**. Exact prices change — check **https://openai.com/api/pricing** for current rates.

### Keeping costs tiny (habits)

- **Use a mini model** for learning; switch up only when needed.
- **Set a usage limit** on the Platform (you did this in Lesson 9).
- **Watch the Usage page** on platform.openai.com.
- Keep prompts focused — huge inputs use more tokens.

### Rate limits & context windows

- **Rate limits**: how much you can send per minute. If you hit one, wait and retry (official libraries retry automatically).
- **Context window**: how much text GPT sees at once. Big inputs still cost more — send only what's relevant.

---

## 🔒 Privacy & safety (5 min)

### What NOT to share with AI

| ❌ Don't share | Why |
|---------------|-----|
| Passwords, API keys, secrets | Could be exposed or misused |
| Other people's private data | You may not have permission |
| Confidential/work-restricted info | Check your employer's rules first |
| Full financial/medical records | Share only what's necessary |

### Trust, but verify

AI can **hallucinate**. Always verify:
- **Numbers, dates, laws, medical, financial** advice → double-check.
- **Quotes, citations, links** → confirm they're real (web search helps — Lesson 15).
- Add to prompts: *"If you're not certain, say so instead of guessing."*

### Your API key = a password

- Store it as the `OPENAI_API_KEY` environment variable (Lesson 9), never in shared code.
- **Never** paste it into a public place (GitHub, forums, screenshots).
- If it leaks: Platform → **API keys** → revoke it, make a new one.

### Use AI responsibly

- Don't use AI to deceive, harass, or impersonate.
- Give credit where appropriate; check school/work rules.
- Treat AI output as a helpful **draft**, not the final authority — *you* are responsible for what you publish.

---

## 🧮 Quick cost sanity check

Want to estimate before running code? Ask ChatGPT itself:

```text
If I send about 500 words and get back about 800 words using a small GPT model,
roughly how many tokens is that? Then remind me to check openai.com/api/pricing for the current rate.
```

---

## ✅ Checkpoint

- [ ] You can explain subscription vs pay-as-you-go.
- [ ] You know mini/nano < flagship in cost.
- [ ] You have a usage limit set.
- [ ] You know what never to share and to verify important facts.

---

## 🎯 Homework

Open the **Usage** page at platform.openai.com and look at what your learning has cost so far (probably cents). Confirm your usage limit is set. Peace of mind unlocked.

---

## 💡 Key takeaways

- App = subscription; API = pay-per-token (mini cheapest, flagship priciest).
- Control cost with a mini model, focused prompts, and a usage limit.
- Never share secrets or others' private data; verify important facts.
- Your API key is a password — protect and rotate it.

🌐 [Polski](../../pl/lessons/17-koszty-bezpieczenstwo.md) · [← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)
