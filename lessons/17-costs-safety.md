# Lesson 17 — Costs, Limits, Privacy, and Safety

⏱️ **10 minutes** · Level: Beginner · Needs: nothing to install

[← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)

---

## 🧠 Theory (5 min)

### How AI pricing works

Chat apps (claude.ai, Claude Desktop) use a **subscription**: free tier, or a paid **Pro** plan for more usage. Simple and predictable.

The **API** (your Python/PowerShell code) is **pay-as-you-go**, billed **per token**. Remember: a token ≈ ¾ of a word. You pay separately for **input** (what you send) and **output** (what Claude writes back).

Rough API prices (per **million** tokens — you'll usually use only thousands):

| Model | Input / 1M tokens | Output / 1M tokens | Feel |
|-------|-------------------|--------------------|------|
| **Haiku** (`claude-haiku-4-5`) | ~$1 | ~$5 | Cheapest, fast |
| **Sonnet** (`claude-sonnet-5`) | ~$3 | ~$15 | Balanced |
| **Opus** (`claude-opus-5`) | ~$5 | ~$25 | Most capable |

> A million tokens is a *lot* — roughly 750,000 words. A typical learning request (a few hundred words each way) costs a **tiny fraction of a cent**. Prices change over time; check **console.anthropic.com** for current rates.

### Keeping costs tiny (habits)

- **Use Haiku for learning and simple tasks.** Switch up only when needed.
- **Set `max_tokens` sensibly** — it caps output length (and cost).
- **Set a monthly spend limit** in the Console (you did this in Lesson 9).
- **Watch the Usage page** in the Console to see real spending.

### Rate limits & context windows

- **Rate limits**: how much you can send per minute. If you hit one, wait a moment and retry. The official libraries retry automatically.
- **Context window**: how much text Claude can "see" at once. Modern Claude models have very large windows, but huge inputs still cost more — send only what's relevant.

---

## 🔒 Privacy & safety (5 min)

### What NOT to share with AI

| ❌ Don't share | Why |
|---------------|-----|
| Passwords, API keys, secrets | They could be exposed or misused |
| Other people's private data | You may not have permission |
| Confidential/work-restricted info | Check your employer's rules first |
| Full financial/medical records | Share only what's necessary |

### Trust, but verify

AI can **hallucinate** — state wrong things confidently. Always verify:
- **Numbers, dates, laws, medical, financial** advice → double-check.
- **Quotes, citations, links** → confirm they're real.
- Add to prompts: *"If you're not certain, say so instead of guessing."*

### Your API key = a password

- Store it as the `ANTHROPIC_API_KEY` environment variable (Lesson 9), never inside code you share.
- **Never** paste it into a public place (GitHub, forums, screenshots).
- If it leaks: go to the Console → **API Keys** → delete it, make a new one.

### Use AI responsibly

- Don't use AI to deceive, harass, or impersonate.
- Give credit where appropriate; check rules for school/work.
- Treat AI output as a **helpful draft**, not the final authority — *you* are responsible for what you publish.

---

## 🧮 Quick cost sanity check

Want to estimate before running code? Ask Claude itself:

```text
If I send about 500 words and get back about 800 words using Claude Haiku,
roughly how many tokens is that and what's the ballpark cost? Show your math.
```

It'll walk you through it. (Then verify the current price on the Console.)

---

## ✅ Checkpoint

- [ ] You can explain subscription vs. pay-as-you-go.
- [ ] You know Haiku < Sonnet < Opus in cost.
- [ ] You have a monthly spend limit set.
- [ ] You know what never to share and to verify important facts.

---

## 🎯 Homework

Open the **Usage** page at console.anthropic.com and look at what your learning has cost so far (probably pennies). Confirm your spend limit is set. Peace of mind unlocked.

---

## 💡 Key takeaways

- Chat = subscription; API = pay-per-token (Haiku cheapest, Opus priciest).
- Control cost with Haiku, `max_tokens`, and a spend limit.
- Never share secrets or others' private data; verify important facts.
- Your API key is a password — protect and rotate it.

[← Prev](16-prompt-engineering.md) · [Course home](../README.md) · [Next: Where to go next →](18-next-steps.md)
