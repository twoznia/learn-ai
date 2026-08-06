# D3 — Save Tokens & Manage Your Usage Limits

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Claude.ai account

🌐 [Polski](../../pl/track-d/03-oszczedzaj-tokeny-i-limity.md) · [← Prev](02-context-window.md) · [Track index](../README.md) · [Next: Skills & connectors →](04-skills-and-connectors.md)

---

## 🧠 Theory (5 min)

Your Pro/Max plan gives you a **generous but not unlimited** amount of usage. It refills on a **rolling window** (a new allowance opens up after a few hours), and Max plans add a higher weekly ceiling. You don't pay per message — but if you burn through the window, you wait for it to reset.

Everything you send **and** everything Claude generates counts toward that usage. So the two levers are:

1. **Send less unnecessary stuff** (shorter context, the right model).
2. **Ask for less unnecessary output** (be specific about length and format).

Being efficient isn't about cramming — it's about **not wasting the window on things you didn't need.**

---

## 🛠️ Practice (9 min)

### Step 1 — Find your usage

**Settings → Usage** (or the plan page) shows how much you've used and when it resets. Check it once so you know where you stand — and check it if replies suddenly say you're near a limit.

### Step 2 — Right-size the model

Heavier models use your allowance faster. Match the model to the task (from D1):

- **Haiku / Sonnet** for quick or routine work.
- **Opus** only when the task genuinely needs the deepest reasoning.

Switching a simple lookup from Opus to Sonnet is a free win.

### Step 3 — Keep context lean

From D2: a long chat re-reads everything each turn, which spends usage. Concretely:
- **One chat = one task**; start fresh for new topics.
- Don't paste a whole 50-page PDF to ask about one paragraph — **paste the paragraph**.
- Attach files instead of pasting huge blocks when you can.

### Step 4 — Ask for the output you actually want

Unbounded answers waste tokens. Steer the length and shape:

```text
Answer in 3 bullet points, one line each. No preamble.
```
```text
Just give me the final SQL query — no explanation.
```
```text
Summarize in under 100 words.
```

You get what you need and stop paying for paragraphs you'll skip.

### Step 5 — Reuse instead of re-generating

- Save good prompts (see Track A's prompt library) so you're not re-crafting them.
- Put standing context in a **Project** so you never re-paste it.
- If you already have a good answer, **edit** it yourself rather than regenerating the whole thing.

### Step 6 — Batch small things

Instead of ten tiny back-and-forths, ask for several related things in **one** well-structured message. Fewer turns = less re-reading of the growing context.

---

## 🧩 Token-saving cheat sheet

| Habit | Why it saves |
|-------|-------------|
| Right-size the model | Lighter models use less allowance |
| One chat = one task | No stale context re-read every turn |
| Paste the relevant part, not the whole doc | Less input to process |
| Specify length/format | No wasted output |
| Use Projects for standing context | Stop re-pasting background |
| Batch related asks | Fewer turns, less re-reading |
| Edit instead of regenerate | Don't pay twice for the same answer |

---

## ✅ Checkpoint

- [ ] You found your usage/limits page and know when it resets.
- [ ] You applied at least three token-saving habits in a real chat.
- [ ] You can explain why both **input** and **output** count toward usage.

---

## 🎯 Homework

Take a task you'd normally do in a long, messy chat. Redo it efficiently: right model, lean context, a length instruction, and one batched message. Notice how much shorter and faster it is — that's usage you just saved.

---

## 💡 Key takeaways

- Usage counts **both** what you send and what Claude generates; save on both sides.
- Right-size the **model**, keep **context lean**, and **specify** the output you want.
- **Projects** + saved prompts + editing (instead of regenerating) stop repeated waste.

🌐 [Polski](../../pl/track-d/03-oszczedzaj-tokeny-i-limity.md) · [← Prev](02-context-window.md) · [Track index](../README.md) · [Next: Skills & connectors →](04-skills-and-connectors.md)
