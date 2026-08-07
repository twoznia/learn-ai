# D2 — The Context Window (and When to Start Fresh)

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Google account

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-plan.md) · [Track index](../README.md) · [Next: Save usage & limits →](03-save-usage-and-limits.md)

---

## 🧠 Theory (5 min)

Gemini reads your **whole conversation** every time it replies — your messages, its answers, and any files you attached. That running total is the **context**, and it lives inside a **context window**.

Gemini's window is **very large** (it can take in long documents and even multiple files at once), which is a real strength — but two things still hold:

1. **A long chat is re-read on every turn.** Turn 30 re-processes everything before it — slower and more of your usage than a short, focused chat.
2. **Bigger isn't always better.** Dumping in a huge, irrelevant pile makes answers vaguer, not sharper. Feed the **relevant** context, not everything.

The skill: know **when to keep going** vs **start fresh**, and how to carry only what matters.

```
[ you ][ Gemini ][ you ][ Gemini ] ... → all re-read every turn
                                ↑
                     context window (very large, but not free)
```

---

## 🛠️ Practice (9 min)

### Step 1 — Use the big window on purpose

Gemini's large context is great for **long inputs**. Try:

```text
Here's a 20-page document. Summarize it, then list the 5 decisions it implies.
```

One long input, one focused ask — exactly what a big window is for.

### Step 2 — But start fresh when the topic changes

New, unrelated task? **Start a new chat** rather than continuing. A fresh chat is faster and cheaper — no old context to re-read.

> Rule of thumb: **one chat = one task.** Switch topics → new chat.

### Step 3 — Feed relevant context, not everything

Don't paste a whole 50-page report to ask about one section — **paste the section** (or upload the file and point to it). More focus = sharper answers and less usage.

### Step 4 — Carry a handoff, not the whole history

To continue elsewhere, summarize instead of re-pasting:

```text
Summarize this conversation into a short handoff for a new chat: the goal,
decisions made, and current state. Keep it under 200 words.
```

Paste that into a **new** chat.

### Step 5 — Use Gems for context you reuse

Re-explaining the *same* background every time (your product, your style, your rules)? Put it in a **Gem** (Track A1):

1. Create a Gem with your standing context in its instructions.
2. Chat **with the Gem** — it already knows the background.

Now every chat with that Gem starts loaded, and you never paste it again.

### Step 6 — Watch for drift in very long chats

If a very long chat starts losing the thread, re-state the key point, **or** start fresh with a summary, **or** move the standing facts into a **Gem**.

---

## 🧩 Keep going or start fresh?

| Situation | Do this |
|-----------|---------|
| Same task, on track | Keep going |
| New, unrelated task | New chat |
| Huge chat getting slow/vague | Summarize → new chat |
| Same background reused often | Put it in a **Gem** |
| One long document to analyze | Use the big window — feed it once |

---

## ✅ Checkpoint

- [ ] You used the large context for a genuinely long input.
- [ ] You started a fresh chat for a new task instead of continuing.
- [ ] You made a handoff summary and/or a Gem to reuse context.
- [ ] You can explain why "everything" isn't the same as "relevant."

---

## 🎯 Homework

Take a long document and use the big window to summarize + extract decisions. Then take a sprawling old chat, compress it to a under-200-word handoff, and continue it in a fresh chat. Finally, put one reused background into a Gem.

---

## 💡 Key takeaways

- Gemini's window is **large** — great for long inputs — but the chat is still **re-read each turn**, so long chats cost more.
- **One chat = one task**; feed **relevant** context, not everything; carry a summary, not the whole history.
- Put **reused background** in a **Gem** so you stop pasting it.

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-plan.md) · [Track index](../README.md) · [Next: Save usage & limits →](03-save-usage-and-limits.md)
