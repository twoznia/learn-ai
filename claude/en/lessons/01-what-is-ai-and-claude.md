# Lesson 01 — What is AI and What is Claude?

⏱️ **10 minutes** · Level: Beginner · No install needed

[← Course home](../README.md) · [Next: Your first chat →](02-first-chat.md)

---

## 🧠 Theory (4 min)

### What "AI" means here

When people say **AI** today, they usually mean a **Large Language Model (LLM)** — a computer program trained on huge amounts of text so it can **predict the next words** in a sentence. That simple idea, done at massive scale, produces something that can write, summarize, explain, translate, and code.

Think of it as an extremely well-read assistant that:

- has read a huge portion of the public internet and many books,
- is great at language, reasoning, and drafting,
- but **doesn't truly "know" facts** — it predicts likely text, so it can sometimes be confidently wrong (this is called a **hallucination**).

> 🔑 **Golden rule from lesson one:** AI is a brilliant assistant, not an oracle. Use it to draft, explain, and speed up — then verify anything important.

### What Claude is

**Claude** is a family of AI models made by **Anthropic**. You can use Claude in several ways, and this course covers all of them:

| Way to use Claude | What it is | Lesson |
|-------------------|-----------|--------|
| **Claude.ai (web)** | Chat in your browser | 02 |
| **Claude Desktop** | A Windows app | 05 |
| **API** | Claude inside your own code | 09–11 |
| **Claude Code** | AI that edits code in your terminal | 13 |

### The Claude model family

Claude comes in different sizes. You pick based on the job:

| Model type | Best for | Feel |
|------------|----------|------|
| **Haiku** | Fast, cheap, simple tasks | Quick and light |
| **Sonnet** | Everyday work, great balance | The reliable default |
| **Opus** | Hardest reasoning & coding | Most capable |

You don't need to memorize version numbers. Just remember: **Haiku = fast**, **Sonnet = balanced**, **Opus = smartest**. In the chat apps, Claude usually picks a sensible default for you.

### Tokens (the unit AI counts in)

AI reads and writes in **tokens** — chunks of text. A token is roughly **¾ of a word**. "Hamburger" might be 3 tokens; "the" is 1.

Why care? Two reasons:

1. **Limits** — a model can only "see" so many tokens at once (its **context window**).
2. **Cost** — when you use the API, you pay per token (tiny fractions of a cent). More on this in Lesson 17.

---

## 🛠️ Practice (4 min)

You don't need any account yet. Let's just build intuition.

1. Open a notepad or a piece of paper.
2. Write down **three tasks** in your daily life or work that involve *words*: writing, explaining, summarizing, planning, or looking things up. Examples:
   - "Write a polite reply to a customer email."
   - "Summarize a long PDF report."
   - "Explain a tax rule in simple terms."
3. Next to each, write whether you'd trust the AI's answer **as-is** or **verify it** (hint: anything with numbers, laws, medical, or money → verify).

Keep this list. By Lesson 6 you'll be doing all three with Claude.

---

## ✅ Checkpoint

You can answer these in your head:

- [ ] What is an LLM in one sentence? *(A program that predicts text based on patterns it learned.)*
- [ ] What is a hallucination? *(When AI states something false confidently.)*
- [ ] Name the three Claude "sizes." *(Haiku, Sonnet, Opus.)*

---

## 🎯 Homework

In one sentence, describe **the single most annoying repetitive text task** in your week. That task is your target — you'll automate it later in this course.

---

## 💡 Key takeaways

- AI = a language model that predicts text; brilliant but not infallible.
- Claude is a model family (Haiku/Sonnet/Opus) you can use via web, desktop app, or code.
- Always verify anything important.

[← Course home](../README.md) · [Next: Your first chat →](02-first-chat.md)
