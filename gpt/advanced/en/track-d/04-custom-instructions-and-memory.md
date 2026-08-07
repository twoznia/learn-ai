# D4 — Custom Instructions & Memory

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a ChatGPT account (Plus recommended)

🌐 [Polski](../../pl/track-d/04-instrukcje-wlasne-i-pamiec.md) · [← Prev](03-save-usage-and-limits.md) · [Track index](../README.md) · [Next: Agents & Codex CLI →](05-agents-and-codex-cli.md)

---

## 🧠 Theory (4 min)

You can make **every** ChatGPT chat feel tailored — without repeating yourself — using two built-in controls:

- **Custom instructions** — a standing "how to respond to me" (who you are, tone, length, format) that ChatGPT applies to every new chat.
- **Memory** — facts ChatGPT remembers about you across chats (preferences, ongoing projects), so you stop re-explaining. You can review, edit, and delete what it stored.

And to keep them straight against Track A's Custom GPTs:

| Need | Use |
|------|-----|
| A global "how to talk to me" | **Custom instructions** |
| Facts ChatGPT should just know about you | **Memory** |
| A specialist for one recurring job | A **Custom GPT** (Track A1) |

> Availability and exact controls for memory vary by plan and roll out over time. Custom instructions are broadly available.

---

## 🛠️ Practice (10 min)

### Step 1 — Set custom instructions

In ChatGPT → **Settings → Personalization → Custom instructions**. Fill in the fields, e.g.:

```text
About me: I'm on Windows, I work in marketing, I prefer plain language over jargon.

How to respond: Be concise and lead with the answer. Number steps. When I ask
for code, give the code first, then a short explanation.
```

Now new chats start with *your* defaults — no re-explaining every time.

### Step 2 — Confirm it took effect

Start a fresh chat and ask something open-ended. The tone, length, and format should match your instructions. Tweak the wording until it feels right.

### Step 3 — Manage memory

In **Settings → Personalization → Memory**, review what ChatGPT has saved. You can:
- **Add** a fact directly ("Remember I use metric units").
- **Delete** anything stale or wrong.
- **Turn it off** entirely, or use a **temporary chat** that doesn't read or write memory.

Try telling ChatGPT something durable ("I'm learning Python") and check it appears in Memory.

### Step 4 — Steer tone on the fly too

Even without settings, shape any single answer:

```text
Rewrite that as three tight bullets a busy manager can skim.
```

Length and tone are yours to set — and this also saves usage (D3).

### Step 5 — Keep it clean and private

- **Review** memory occasionally; delete what no longer applies.
- Don't let memory hold **secrets** or sensitive personal data.
- Use a **temporary chat** for anything you don't want remembered.

> ⚠️ Custom instructions and memory shape every answer. Prune them so nothing outdated or private keeps influencing future chats.

---

## 🧩 Tailoring controls

| Control | Use it to |
|---------|-----------|
| **Custom instructions** | Set your global voice & format |
| **Memory** | Stop re-explaining your context (review/prune it) |
| **Custom GPT** | A specialist for one recurring task |
| **Temporary chat** | A one-off with no memory read/write |

---

## ✅ Checkpoint

- [ ] You set custom instructions and saw a new chat follow them.
- [ ] You reviewed memory and added or deleted an item.
- [ ] You can explain custom instructions vs memory vs Custom GPTs.
- [ ] You know how to use a temporary chat for privacy.

---

## 🎯 Homework

Write custom instructions that capture how you like answers (length, tone, format). Add one durable memory fact about how you work, then review Memory and delete anything stale. Try a temporary chat and confirm it doesn't save anything.

---

## 💡 Key takeaways

- **Custom instructions** set your global voice; **memory** stops you re-explaining (review and prune it).
- A **Custom GPT** is a specialist for one job — different from global personalization.
- Keep both **clean and secret-free**, and use a **temporary chat** when you don't want something remembered.

🌐 [Polski](../../pl/track-d/04-instrukcje-wlasne-i-pamiec.md) · [← Prev](03-save-usage-and-limits.md) · [Track index](../README.md) · [Next: Agents & Codex CLI →](05-agents-and-codex-cli.md)
