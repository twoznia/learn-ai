# Lesson 07 — Custom GPTs & Projects

⏱️ **10 minutes** · Level: Beginner · Needs: your ChatGPT account

🌐 [Polski](../../pl/lessons/07-wlasne-gpt-i-projekty.md) · [← Prev](06-everyday-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)

---

## 🧠 Theory (3 min)

So far, every new chat started from zero. Two ChatGPT features fix that:

- **Custom instructions** — settings that tell ChatGPT how to respond in *all* your chats (who you are, your tone, your rules).
- **Custom GPTs** — a saved version of ChatGPT with its own instructions (and optionally files), so you open it and it already behaves how you set it up.
- **Projects** — a workspace that groups related chats and can hold **files + instructions** they all share.

Think of these as giving ChatGPT a **job description** it never forgets — so you stop re-explaining yourself.

> Availability varies by plan (some features are on paid tiers). If one isn't available, you can get most of the benefit by saving a **"context block"** you paste at the top of chats (shown below).

---

## 🛠️ Practice (6 min)

### Path A — Custom instructions (available to most)

1. In ChatGPT, open **Settings → Personalization → Custom instructions** (or click your name/avatar).
2. Fill in the boxes — for "How would you like ChatGPT to respond?", paste:

```text
- Audience: me, a busy non-technical professional.
- Tone: warm, clear, concise. No jargon unless you define it.
- Always end longer answers with a short "Next step:" line.
- If a request is ambiguous, ask one clarifying question before answering.
- If you're unsure of a fact, say so rather than guessing.
```

3. Save. Now every chat follows these rules automatically.

### Path B — A Custom GPT or Project (if available)

1. In the sidebar, look for **GPTs / "Explore GPTs" → Create**, or **Projects → New project**.
2. Give it a name (e.g. **"My Assistant"**) and paste the same instructions as above.
3. Add a file if useful (a style guide, your resume). Start a chat *inside* it — it already knows the rules.

### Path C — Free equivalent (works for everyone)

Save this as `context-block.txt` and paste it at the **start** of any chat:

```text
CONTEXT FOR THIS CHAT (follow these rules):
- Act as my personal work assistant.
- I'm non-technical; keep it simple and jargon-free.
- Be concise and end with a "Next step:" line.
- Ask one clarifying question if my request is unclear.
- Say "I'm not certain" rather than guessing facts.

My request:
```

### Test it

Try the same vague request with and without the instructions:
```text
help me with the newsletter
```
With instructions in place, ChatGPT should ask a smart clarifying question and match your tone. Without them, it guesses.

---

## 🧩 Good instruction ingredients

| Goal | Line to add |
|------|-------------|
| Consistent tone | "Write in a friendly, professional tone." |
| Shorter answers | "Default to concise; expand only if I ask." |
| Fewer wrong facts | "If unsure, say so instead of guessing." |
| Action-oriented | "End with a clear next step." |
| Your domain | "I work in <field>; assume that context." |

---

## ✅ Checkpoint

- [ ] You set custom instructions **or** saved a reusable context block.
- [ ] ChatGPT followed your standing instructions without repeating them.
- [ ] You understand GPTs/Projects = saved instructions (+ files) it remembers.

---

## 🎯 Homework

Write **your own** 5-line instruction block describing how you want ChatGPT to behave. This is one of the highest-leverage things in the course — good standing instructions improve *every* future chat.

---

## 💡 Key takeaways

- **Custom instructions / GPTs / Projects** = standing instructions (and files) ChatGPT never forgets.
- No access? Paste a **context block** at the top of chats for the same effect.
- Clear instructions make every answer better with zero extra effort.

🌐 [Polski](../../pl/lessons/07-wlasne-gpt-i-projekty.md) · [← Prev](06-everyday-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)
