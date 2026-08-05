# Lesson 17 — Costs, Limits, Privacy, and Safety

⏱️ **10 minutes** · Level: Beginner · Needs: nothing to install

🌐 [Polski](../../pl/lessons/17-koszty-bezpieczenstwo.md) · [← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)

---

## 🧠 Theory (5 min)

### How Gemini pricing works

The **Gemini app** (gemini.google.com) uses a **subscription**: a free tier, or paid plans (Google AI Pro/Ultra, often via Google One) for more usage and top models. Simple and predictable.

The **API** (your Python/PowerShell code) has a **free tier** *and* pay-as-you-go:

- **Free tier (Google AI Studio):** make requests with **no billing**, subject to rate limits. Great for learning — much of this course costs nothing.
- **Paid tier:** when you exceed free limits, you pay **per token** (a token ≈ ¾ of a word), billed separately for input and output.

Rough idea of relative cost (Flash-Lite < Flash < Pro):

| Model | Cost | Feel |
|-------|------|------|
| **Flash-Lite** (`gemini-2.5-flash-lite`) | Cheapest | Fastest, simple tasks |
| **Flash** (`gemini-2.5-flash`) | Low | Balanced, everyday |
| **Pro** (`gemini-2.5-pro`) | Highest | Most capable |

> Exact prices and free-tier limits change. Check current rates at **https://ai.google.dev/pricing**.

### Keeping costs tiny (habits)

- **Start on the free tier** and use **Flash** for learning.
- **Don't add billing** until you actually hit free limits.
- Watch usage in **Google AI Studio**.
- Keep prompts focused — huge inputs use more tokens.

### Rate limits & context windows

- **Rate limits**: how many requests per minute the free tier allows. If you hit one, wait and retry.
- **Context window**: how much text Gemini sees at once — Gemini's is very large, but bigger inputs still cost more on the paid tier.

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
- **Quotes, citations, links** → confirm they're real (grounding helps — Lesson 15).
- Add to prompts: *"If you're not certain, say so instead of guessing."*

### Your API key = a password

- Store it as the `GEMINI_API_KEY` environment variable (Lesson 9), never in shared code.
- **Never** paste it into a public place (GitHub, forums, screenshots).
- If it leaks: Google AI Studio → **API keys** → delete it, make a new one.

### Use AI responsibly

- Don't use AI to deceive, harass, or impersonate.
- Give credit where appropriate; check school/work rules.
- Treat AI output as a helpful **draft**, not the final authority — *you* are responsible for what you publish.

---

## 🧮 Quick cost sanity check

Want to estimate before running code? Ask Gemini itself:

```text
If I send about 500 words and get back about 800 words using Gemini 2.5 Flash,
roughly how many tokens is that? Then remind me to check ai.google.dev/pricing for the current rate.
```

---

## ✅ Checkpoint

- [ ] You can explain free tier vs pay-as-you-go.
- [ ] You know Flash-Lite < Flash < Pro in cost.
- [ ] You know where to check pricing (ai.google.dev/pricing).
- [ ] You know what never to share and to verify important facts.

---

## 🎯 Homework

Open **Google AI Studio** and find where usage/limits are shown. Confirm you're on the free tier and haven't accidentally enabled billing you don't need.

---

## 💡 Key takeaways

- App = subscription; API = **free tier** + pay-per-token (Flash-Lite cheapest, Pro priciest).
- Learn on the free tier with Flash; add billing only when needed.
- Never share secrets or others' private data; verify important facts.
- Your API key is a password — protect and rotate it.

🌐 [Polski](../../pl/lessons/17-koszty-bezpieczenstwo.md) · [← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)
