# D2 — The Context Window (and When to Start Fresh)

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a ChatGPT account

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-plan.md) · [Track index](../README.md) · [Next: Save usage & limits →](03-save-usage-and-limits.md)

---

## 🧠 Theory (5 min)

ChatGPT reads your **whole conversation** every time it replies — your messages, its answers, and any files you attached. That running total is the **context**, and it lives inside a fixed-size **context window**.

Two things follow from this:

1. **A long chat is re-read on every turn.** Turn 30 re-processes everything before it — slower and more of your usage than a short, focused chat.
2. **When the window fills up, the beginning falls out of view.** ChatGPT may "forget" what you said at the very start of a very long conversation.

The skill is knowing **when to keep going** vs **when to start a fresh chat** — and how to carry only what matters across.

```
[ you ][ GPT ][ you ][ GPT ] ... → all re-read every turn
                          ↑
                context window (fixed size)
```

> Note: **memory** (D4) is different — it's a small set of saved facts about you that persists across chats. It does **not** remove the per-chat context limit.

---

## 🛠️ Practice (9 min)

### Step 1 — See a chat "fill up"

Paste a long document into a chat and ask several follow-up questions. Notice replies get a little slower as the conversation grows — that's the whole thing being re-read each time.

### Step 2 — Start fresh when the topic changes

New, unrelated task? **Start a new chat** instead of continuing. A fresh chat is faster and cheaper — no old context to re-read.

> Rule of thumb: **one chat = one task.** Switch topics → new chat.

### Step 3 — Carry a handoff, not the whole history

To continue elsewhere, summarize instead of re-pasting:

```text
Summarize this conversation into a short handoff for a new chat: the goal,
decisions made, and current state. Keep it under 200 words.
```

Paste that into a **new** chat.

### Step 4 — Use Projects for context you reuse

Re-explaining the *same* background every time (your product, your style, your rules)? Put it in a **Project**:

1. Sidebar → **Projects** → new project, add your standing context to its instructions/files.
2. Start chats **inside** the project — GPT already knows the background.

Now every chat in that project starts loaded, and you never paste it again. A **Custom GPT** (Track A1) works similarly for a repeatable role.

### Step 5 — Paste the relevant part, not everything

Don't paste a 50-page report to ask about one section — **paste the section** (or attach the file). More focus = sharper answers and less usage.

### Step 6 — Watch for "forgetting"

In a very long chat, if GPT loses track of something from the start, that's the window filling up. Re-state the key fact, **or** start fresh with a summary, **or** move the standing facts into a **Project**.

---

## 🧩 Keep going or start fresh?

| Situation | Do this |
|-----------|---------|
| Same task, on track | Keep going |
| New, unrelated task | New chat |
| Chat is huge and slow | Summarize → new chat |
| Same background reused often | Put it in a **Project** / Custom GPT |
| GPT forgot an early detail | Re-state it, or summarize → fresh chat |

---

## ✅ Checkpoint

- [ ] You can explain why long chats get slower and cost more of your allowance.
- [ ] You started a fresh chat for a new task instead of continuing.
- [ ] You created a handoff summary and/or a Project to reuse context.
- [ ] You know memory (D4) is separate from the per-chat window.

---

## 🎯 Homework

Take one long, sprawling chat. Compress it to a under-200-word handoff, start a fresh chat with it, and confirm GPT picks up where you left off. Then create a Project for a topic you work on repeatedly.

---

## 💡 Key takeaways

- ChatGPT re-reads the **whole conversation** each turn; long chats are slower and use more of your allowance.
- **One chat = one task** — start fresh for new topics; carry a short summary, not the whole history.
- Put **reused background** in a **Project** (or Custom GPT) so you stop pasting it — memory (D4) is a separate feature.

🌐 [Polski](../../pl/track-d/02-okno-kontekstowe.md) · [← Prev](01-make-the-most-of-your-plan.md) · [Track index](../README.md) · [Next: Save usage & limits →](03-save-usage-and-limits.md)
