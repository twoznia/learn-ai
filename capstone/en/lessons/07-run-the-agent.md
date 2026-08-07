# Capstone 07 — Run the Agent End-to-End

⏱️ **15 minutes** · Level: Capstone · Needs: tools + Skills working (Lesson 6), some real notes

🌐 [Polski](../../pl/lessons/07-uruchom-agenta.md) · [← Prev](06-author-your-skills.md) · [Capstone home](../README.md) · [Next: Test, harden & ship →](08-test-harden-and-ship.md)

---

## 🧠 Theory (3 min)

Everything is wired: an agent, tools, Skills, and notes. Now you **use it as a real product**. Three core workflows show the whole thing working together:

1. **Capture** — talk, and it files well-formed notes (tools + note-style Skill).
2. **Recall** — ask questions and get answers **grounded in your notes**, with the source note cited (the anti-hallucination habit from the Prompt Engineering course).
3. **Review** — run the weekly review and get themes, open loops, and priorities.

This lesson is the payoff: your Second Brain, working end to end.

---

## 🛠️ Practice (11 min)

### Step 1 — Capture naturally

Just talk to it:

```text
Jot this down: idea for the app — a "focus mode" that hides all notes except
today's. Might pair well with the weekly review.
```

The agent titles it, tags it (`idea`), and saves it. Capture as many as you like — it's frictionless now.

### Step 2 — Recall, grounded

Ask a real question:

```text
What ideas have I saved about the app? Answer only from my notes, and name the
note each point comes from. If it's not in my notes, say so.
```

That "**only from my notes, name the note**" instruction is grounding — it keeps the agent honest and turns your notes into a trustworthy knowledge base.

### Step 3 — Connect the dots

The agent can synthesize across notes:

```text
Search my notes and tell me: what open TODOs do I have, grouped by tag?
```

It uses `search_notes`/`list_notes` and pulls the `TODO:` lines you've been leaving — value your flat files alone couldn't give you.

### Step 4 — Run the weekly review

```text
Do my weekly review.
```

The **weekly-review Skill** loads and runs your workflow: gather notes → themes → open loops → 3 priorities → offer to save the summary. Approve saving it, and it becomes a note too.

### Step 5 — Keep it grounded

If an answer ever feels invented, add the guardrail:

```text
Re-answer using only what's actually in my notes. Quote the exact lines you used.
```

If it can't quote a note, the claim wasn't really yours — exactly what you want to catch.

### Step 6 — Make it a habit loop

You now have a daily loop: **capture during the day → recall when you need it → review each week.** That loop is what turns a pile of files into a real Second Brain.

---

## 🧩 The three workflows

| Workflow | You say | Uses |
|----------|---------|------|
| **Capture** | "Jot this down…" | `save_note` + note-style Skill |
| **Recall** | "What have I noted about X? (only from my notes)" | `search_notes` / `get_note` |
| **Review** | "Do my weekly review" | weekly-review Skill + tools |

> ⚠️ For recall, always keep the **"only from my notes"** framing. It's the difference between a trustworthy Second Brain and a confident guesser.

---

## ✅ Checkpoint

- [ ] You captured notes just by talking; they came out well-formed.
- [ ] You got a **grounded** answer that named its source notes.
- [ ] The agent pulled your open TODOs across notes.
- [ ] The weekly review ran the full workflow and offered to save a summary.

---

## 🎯 Homework

Use your Second Brain for one real day: capture everything through the agent, then ask it two grounded questions and run a weekly review at the end. Notice what it surfaced that you'd forgotten — that's the whole point.

---

## 💡 Key takeaways

- Your agent does three real workflows: **capture**, **grounded recall**, and **weekly review** — tools and Skills together.
- **Grounding** ("only from my notes, name the source") is what makes recall trustworthy.
- The daily **capture → recall → review** loop is what makes it a true Second Brain.

🌐 [Polski](../../pl/lessons/07-uruchom-agenta.md) · [← Prev](06-author-your-skills.md) · [Capstone home](../README.md) · [Next: Test, harden & ship →](08-test-harden-and-ship.md)
