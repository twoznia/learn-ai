# Lesson 07 — Projects and Custom Instructions

⏱️ **10 minutes** · Level: Beginner · Needs: your Claude account (web or desktop)

[← Prev](06-desktop-daily-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)

---

## 🧠 Theory (3 min)

So far, every new chat started from zero. **Projects** fix that.

A **Project** is a workspace where you store:

- **Custom instructions** — standing orders Claude follows in every chat there (your role, your tone, rules).
- **Knowledge files** — documents Claude can reference across all chats in that project (a style guide, a product list, your resume).

Think of a Project as giving Claude a **job description + a filing cabinet** that it never forgets — so you stop re-explaining yourself.

> Projects are available on paid plans. If you're on the free tier, you can still get most of the benefit by saving a **"context block"** you paste at the top of chats (shown below). Either way, the concept is the same.

---

## 🛠️ Practice (6 min)

### Path A — If you have Projects

1. In claude.ai or Claude Desktop, find **Projects** in the left sidebar → **+ Create Project**.
2. Name it e.g. **"My Assistant"**.
3. Open **Instructions** (sometimes "Set custom instructions") and paste:

```text
You are my personal work assistant.
- Audience: me, a busy non-technical professional.
- Tone: warm, clear, concise. No jargon unless you define it.
- Always end longer answers with a short "Next step:" line.
- If a request is ambiguous, ask one clarifying question before answering.
- If you're unsure of a fact, say so rather than guessing.
```

4. Add a knowledge file if you have one (e.g. a PDF about your job, a style guide). Click **Add content / files**.
5. Start a chat *inside* the project and notice it already "knows" the rules — no re-explaining.

### Path B — Free-tier equivalent (works for everyone)

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

Try the same vague request with and without the context/instructions:
```text
help me with the newsletter
```
With instructions in place, Claude should ask a smart clarifying question and match your tone. Without them, it guesses.

---

## 🧩 Good custom-instruction ingredients

Steal these lines for your instructions:

| Goal | Line to add |
|------|-------------|
| Consistent tone | "Write in a friendly, professional tone." |
| Shorter answers | "Default to concise; expand only if I ask." |
| Fewer wrong facts | "If unsure, say so instead of guessing." |
| Action-oriented | "End with a clear next step." |
| Your domain | "I work in <field>; assume that context." |

---

## ✅ Checkpoint

- [ ] You created a Project **or** saved a reusable context block.
- [ ] Claude followed your standing instructions without you repeating them.
- [ ] You understand knowledge files = documents Claude remembers across chats.

---

## 🎯 Homework

Write **your own** 5-line custom-instruction block that describes how you want Claude to behave. This is one of the highest-leverage things in the whole course — a good instruction block improves *every* future chat.

---

## 💡 Key takeaways

- **Projects** = standing instructions + reference files Claude never forgets.
- No Projects? Paste a **context block** at the top of chats for the same effect.
- Clear standing instructions make every answer better with zero extra effort.

[← Prev](06-desktop-daily-tasks.md) · [Course home](../README.md) · [Next: Install Python →](08-install-python.md)
