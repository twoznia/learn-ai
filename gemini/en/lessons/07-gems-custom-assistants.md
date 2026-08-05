# Lesson 07 — Gems: Your Custom AI Assistants

⏱️ **10 minutes** · Level: Beginner · Needs: gemini.google.com

🌐 [Polski](../../pl/lessons/07-gems-wlasni-asystenci.md) · [← Prev](06-everyday-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)

---

## 🧠 Theory (3 min)

So far, every new chat started from zero. **Gems** fix that.

A **Gem** is a custom version of Gemini with **standing instructions** you write once — its role, tone, and rules. Open the Gem and it already behaves the way you set it up, so you stop re-explaining yourself. Think of it as giving Gemini a **job description** it never forgets.

Common Gems people make:
- A **writing assistant** in your voice.
- A **coding helper** that always explains for beginners.
- A **study buddy** for a subject you're learning.

> Gems are available in the Gemini app. If you don't see them on your account, you can get most of the benefit by saving a **"context block"** you paste at the top of chats (shown below). Either way, the concept is the same.

---

## 🛠️ Practice (6 min)

### Path A — If you have Gems

1. In gemini.google.com, find **Gems** in the left sidebar (or a **Gem manager** / "New Gem" option).
2. Click **New Gem**.
3. Give it a name, e.g. **"My Assistant"**, and paste instructions:

```text
You are my personal work assistant.
- Audience: me, a busy non-technical professional.
- Tone: warm, clear, concise. No jargon unless you define it.
- Always end longer answers with a short "Next step:" line.
- If a request is ambiguous, ask one clarifying question before answering.
- If you're unsure of a fact, say so rather than guessing.
```

4. Save it. Then start a chat *with that Gem* and notice it already knows the rules — no re-explaining.

### Path B — Free equivalent (works for everyone)

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

Then type your actual request underneath.

### Test it

Try the same vague request with and without the Gem/context:
```text
help me with the newsletter
```
With instructions in place, Gemini should ask a smart clarifying question and match your tone. Without them, it guesses.

---

## 🧩 Good instruction ingredients

Steal these lines:

| Goal | Line to add |
|------|-------------|
| Consistent tone | "Write in a friendly, professional tone." |
| Shorter answers | "Default to concise; expand only if I ask." |
| Fewer wrong facts | "If unsure, say so instead of guessing." |
| Action-oriented | "End with a clear next step." |
| Your domain | "I work in <field>; assume that context." |

---

## ✅ Checkpoint

- [ ] You created a Gem **or** saved a reusable context block.
- [ ] Gemini followed your standing instructions without repeating them.
- [ ] You understand a Gem = a saved persona + rules.

---

## 🎯 Homework

Write **your own** 5-line instruction block describing how you want Gemini to behave. This is one of the highest-leverage things in the course — good standing instructions improve *every* future chat.

---

## 💡 Key takeaways

- **Gems** = custom Gemini assistants with standing instructions it never forgets.
- No Gems? Paste a **context block** at the top of chats for the same effect.
- Clear instructions make every answer better with zero extra effort.

🌐 [Polski](../../pl/lessons/07-gems-wlasni-asystenci.md) · [← Prev](06-everyday-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)
