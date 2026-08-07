# Lesson 01 — What Is Prompt Engineering?

⏱️ **10 minutes** · Level: Beginner · Needs: any AI chat (Claude, Gemini, or ChatGPT)

🌐 [Polski](../../pl/lessons/01-czym-jest-inzynieria-promptow.md) · [Course home](../README.md) · [Next: Anatomy of a prompt →](02-anatomy-of-a-prompt.md)

---

## 🧠 Theory (4 min)

**Prompt engineering** is the skill of writing instructions that get an AI to do what you actually want — reliably. The same model can give you a vague, mediocre answer or a sharp, useful one; the difference is usually the **prompt**.

To prompt well, hold a simple mental model of how these models work:

- An AI chat is a **large language model (LLM)** that predicts text. Given your words, it continues them with the most plausible next words.
- It has **no memory** between separate chats and **no hidden knowledge of your intent** — it only has what's in the current conversation (the **context**).
- It's a **pattern-matcher, not a database**. It can be fluent and *wrong*. Your prompt shapes the pattern it follows.

Because this is true of *all* modern LLMs, the skills in this course **transfer across providers** — Claude, Gemini, ChatGPT, and others. Wording and features differ; the principles don't.

> The core idea: you're not "searching," you're **directing**. A better direction gets a better performance.

---

## 🛠️ Practice (5 min)

### Step 1 — Feel the difference

Open any AI chat and send this vague prompt:

```text
Write something about dogs.
```

Then send a directed one:

```text
Write a 4-sentence intro for a blog post aimed at first-time dog owners,
warm and encouraging in tone, ending with a question that invites comments.
```

Compare. Same model — the second prompt did the work.

### Step 2 — Name what changed

The second prompt added **task**, **audience**, **length**, **tone**, and **format**. That's the whole game, and we'll build each piece across this course.

### Step 3 — Try the same prompt on two models

If you have access to more than one (Claude / Gemini / ChatGPT), send the directed prompt to each. Notice the *style* differs but both follow your direction — proof the skill transfers.

### Step 4 — Start a prompt journal

Create a note called `my-prompts.md`. Each time a prompt works well, paste it in. By Lesson 14 you'll have the start of a reusable library.

---

## 🧩 Vague vs directed

| Vague prompt | Directed prompt |
|--------------|-----------------|
| "Write about dogs" | "Write a 4-sentence intro for first-time dog owners, warm, ending in a question" |
| "Fix this" | "Find the bug that causes X and explain the fix in one paragraph" |
| "Summarize this" | "Summarize this in 5 bullet points a busy manager can skim" |

---

## ✅ Checkpoint

- [ ] You can explain what an LLM does in one sentence (predicts text from context).
- [ ] You saw a vague and a directed prompt produce very different results.
- [ ] You can name at least three things the directed prompt specified.
- [ ] You started a `my-prompts.md` journal.

---

## 🎯 Homework

Take one thing you'd genuinely ask an AI this week. Write it twice — once as you normally would, once fully directed (task, audience, length, tone, format). Run both, and save the better one to your journal.

---

## 💡 Key takeaways

- **Prompt engineering** is directing an LLM to do what you want — the prompt, not the model, is usually the bottleneck.
- LLMs **predict text from the current context**; they're fluent pattern-matchers that can be confidently wrong.
- The skills **transfer across Claude, Gemini, and ChatGPT** — principles over product quirks.

🌐 [Polski](../../pl/lessons/01-czym-jest-inzynieria-promptow.md) · [Course home](../README.md) · [Next: Anatomy of a prompt →](02-anatomy-of-a-prompt.md)
