# Lesson 01 — What is AI and What is Gemini?

⏱️ **10 minutes** · Level: Beginner · No install needed

🌐 [Polski](../../pl/lessons/01-czym-jest-ai-i-gemini.md) · [← Course home](../README.md) · [Next: Your first chat →](02-first-chat.md)

---

## 🧠 Theory (4 min)

### What "AI" means here

When people say **AI** today, they usually mean a **Large Language Model (LLM)** — a program trained on huge amounts of text (and images, audio, and more) so it can **predict the next words**. Done at massive scale, that produces something that can write, summarize, explain, translate, and code.

Think of it as an extremely well-read assistant that:

- has learned from a huge portion of the public internet,
- is great at language, reasoning, and drafting,
- but **doesn't truly "know" facts** — it predicts likely text, so it can be confidently wrong (a **hallucination**).

> 🔑 **Golden rule:** AI is a brilliant assistant, not an oracle. Use it to draft, explain, and speed up — then verify anything important.

### What Gemini is

**Gemini** is a family of AI models made by **Google**. A key trait: Gemini is **natively multimodal** — the same model understands text, images, and more together. You can use Gemini in several ways, all covered in this course:

| Way to use Gemini | What it is | Lesson |
|-------------------|-----------|--------|
| **gemini.google.com** | Chat in your browser | 02 |
| **Chrome / Google / Workspace** | Gemini inside Google's products | 05 |
| **API** | Gemini inside your own code | 09–11 |
| **Gemini CLI** | AI that edits code in your terminal | 13 |

### The Gemini model family

Gemini comes in sizes. Pick based on the job:

| Model type | Best for | Feel |
|------------|----------|------|
| **Flash-Lite** | High-volume, simplest tasks | Fastest, cheapest |
| **Flash** | Everyday work, great balance | Fast and capable |
| **Pro** | Hardest reasoning & coding | Most capable |

You don't need to memorize version numbers. Remember: **Flash = fast and cheap**, **Pro = smartest**. In the Gemini app, Google usually picks a sensible default for you.

### Tokens (the unit AI counts in)

AI reads and writes in **tokens** — chunks of text (~¾ of a word). Why care?

1. **Limits** — a model can only "see" so many tokens at once (its **context window**; Gemini's is famously large).
2. **Cost** — with the API you pay per token, but **Google AI Studio has a generous free tier**, so learning can cost nothing.

---

## 🛠️ Practice (4 min)

You don't need an account yet. Build intuition:

1. Open a notepad or paper.
2. Write **three tasks** in your life or work that involve *words*: writing, explaining, summarizing, planning, or looking things up.
3. Next to each, note whether you'd trust the AI's answer **as-is** or **verify it** (numbers, laws, medical, money → verify).

Keep this list. By Lesson 6 you'll be doing all three with Gemini.

---

## ✅ Checkpoint

- [ ] What is an LLM in one sentence? *(A program that predicts text from patterns it learned.)*
- [ ] What does "multimodal" mean? *(One model handling text, images, audio together.)*
- [ ] Name the three Gemini "sizes." *(Flash-Lite, Flash, Pro.)*

---

## 🎯 Homework

In one sentence, describe **the single most annoying repetitive text task** in your week. That task is your target — you'll automate it later.

---

## 💡 Key takeaways

- AI = a language model that predicts text; brilliant but not infallible.
- Gemini is a **multimodal** model family (Flash-Lite/Flash/Pro) usable via web, Google apps, or code.
- Google AI Studio's **free tier** makes learning cheap; always verify anything important.

🌐 [Polski](../../pl/lessons/01-czym-jest-ai-i-gemini.md) · [← Course home](../README.md) · [Next: Your first chat →](02-first-chat.md)
