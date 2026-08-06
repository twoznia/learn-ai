# D2 — The Context Window (and When to Start Fresh)

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Claude.ai account

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-subscription.md) · [Track index](../README.md) · [Next: Save tokens & manage limits →](03-save-tokens-and-manage-limits.md)

---

## 🧠 Theory (5 min)

Claude reads your **whole conversation** every time it replies — your messages, its answers, and any files you attached. That running total is the **context**, and it lives inside a fixed-size **context window**.

Two things follow from this:

1. **A long chat is re-read on every turn.** Turn 30 re-processes everything from turns 1–29. That's slower and uses more of your allowance than a short, focused chat.
2. **When the window fills up, the beginning falls out of view.** Claude may "forget" what you said at the very start of a very long conversation.

The skill is knowing **when to keep going** vs **when to start a fresh chat** — and how to carry only what matters across.

```
[ your msg ][ Claude ][ your msg ][ Claude ] ... → all re-read every turn
                                    ↑
                          context window (fixed size)
```

---

## 🛠️ Practice (9 min)

### Step 1 — See a chat "fill up"

Open a normal chat and paste a long document, then ask several follow-up questions about it. Notice replies get a little slower as the conversation grows — that's the whole thing being re-read each time.

### Step 2 — Start fresh when the topic changes

New task? **Start a new chat** instead of continuing an unrelated one. A fresh chat is faster and cheaper because there's no old context to re-read.

> Rule of thumb: **one chat = one task.** When you switch to something unrelated, open a new chat.

### Step 3 — Carry only what matters across

When you *do* want to continue elsewhere, don't paste the whole old chat. Ask Claude to summarize the essentials:

```text
Summarize this conversation into a short handoff I can paste into a new chat:
the goal, the decisions we made, and the current state. Keep it under 200 words.
```

Copy that summary into a **new** chat. You keep the useful context and drop the bulk.

### Step 4 — Use Projects for context you reuse

If you keep re-explaining the *same* background (your product, your style, your rules), don't paste it every time — put it in a **Project**.

1. Left sidebar → **Projects** → **New Project**.
2. Add your standing context to **Project knowledge** (or project instructions).
3. Start chats **inside** the project — Claude already knows the background.

Now every chat in that project starts with the context loaded, and you never paste it again.

### Step 5 — Watch for "forgetting"

In a very long chat, if Claude loses track of something from the start, that's the window filling up. Fixes:
- Re-state the key fact briefly, **or**
- Start a fresh chat with a short summary (Step 3), **or**
- Move the standing facts into a **Project** (Step 4).

---

## 🧩 Keep going or start fresh?

| Situation | Do this |
|-----------|---------|
| Same task, still on track | Keep the chat going |
| New, unrelated task | New chat |
| Chat is huge and getting slow | Summarize → new chat |
| Same background reused often | Put it in a **Project** |
| Claude forgot an early detail | Re-state it, or summarize → fresh chat |

---

## ✅ Checkpoint

- [ ] You can explain why long chats get slower and cost more of your allowance.
- [ ] You started a fresh chat for a new task instead of continuing an old one.
- [ ] You created a handoff summary and/or a Project to reuse context.

---

## 🎯 Homework

Take one long, sprawling chat you have. Summarize it into a under-200-word handoff, start a fresh chat with it, and confirm Claude picks up right where you left off. Then create a Project for a topic you work on repeatedly.

---

## 💡 Key takeaways

- Claude re-reads the **whole conversation** each turn; long chats are slower and use more of your allowance.
- **One chat = one task** — start fresh for new topics; carry a short summary, not the whole history.
- Put **reused background** in a **Project** so you stop pasting it.

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-subscription.md) · [Track index](../README.md) · [Next: Save tokens & manage limits →](03-save-tokens-and-manage-limits.md)
