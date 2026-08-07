# Lesson 14 — Build a Reusable Prompt-Pattern Library

⏱️ **11 minutes** · Level: Intermediate · Needs: any AI chat, your `my-prompts.md`

🌐 [Polski](../../pl/lessons/14-biblioteka-wzorcow-promptow.md) · [← Prev](13-long-documents.md) · [Course home](../README.md) · [Next: Evaluating prompts →](15-evaluating-prompts.md)

---

## 🧠 Theory (4 min)

The pros don't reinvent prompts each time — they reuse **patterns**: proven templates with blanks to fill. After 13 lessons you have the pieces; now you organize them into a personal **library** you draw from instantly.

A good pattern is:
- **Parameterized** — fixed structure, blanks for the variable bits (`[topic]`, `[audience]`).
- **Tested** — you've seen it work, so you trust it.
- **Labeled** — named by the job it does, so you can find it.

Some patterns worth having: **Summarize**, **Rewrite in style**, **Extract to table/JSON**, **Explain simply**, **Critique & improve**, **Compare options**, **Draft then refine**. Build yours from real tasks.

---

## 🛠️ Practice (6 min)

### Step 1 — Turn a win into a template

Take a prompt that worked and replace specifics with slots:

```text
[ROLE]. Summarize [CONTENT] for [AUDIENCE] in [N] bullets, each under [LIMIT]
words. Focus on [FOCUS]. Output only the bullets.
```

### Step 2 — Write 3 core patterns

Add these to `my-prompts.md`, each with slots:

```text
## Extract to table
From [SOURCE], extract into a table: [COL1] | [COL2] | [COL3].
Quote the source text for each row. Output only the table.
```
```text
## Explain simply
You are a patient tutor. Explain [CONCEPT] to [AUDIENCE] with one analogy,
then a 1-sentence precise definition. Under [N] words, no jargon.
```
```text
## Critique & improve
Critique the text below against [CRITERIA]. List weaknesses, then a stronger
version. Text: """[TEXT]"""
```

### Step 3 — Organize by job

Group patterns under headings: *Writing, Analysis, Data, Learning, Coding*. Finding the right one fast is the whole point.

### Step 4 — Note when each works

Under each pattern, add a line: *"Best for… / not for…"* so future-you picks correctly.

### Step 5 — Reuse standing patterns

For patterns you use constantly, promote them to your tool's **saved assistants** (Custom GPT, Gem, Claude Project) or custom instructions (Lesson 7) — a pattern you never have to paste again.

---

## 🧩 Starter library

| Pattern | Job |
|---------|-----|
| Summarize | Condense to N bullets for an audience |
| Rewrite in style | Match a tone/register |
| Extract to table/JSON | Pull structured data |
| Explain simply | Teach a concept |
| Critique & improve | Self-editing loop |
| Compare options | Decision tables |

---

## ✅ Checkpoint

- [ ] You converted a working prompt into a parameterized template.
- [ ] You saved at least 3 core patterns, organized by job.
- [ ] Each pattern has a "best for / not for" note.
- [ ] You promoted one pattern to a saved assistant or custom instructions.

---

## 🎯 Homework

Grow your library to 6–8 tested patterns covering the tasks you do most. Use one this week straight from the library (fill the slots, run it) and refine the template based on the result.

---

## 💡 Key takeaways

- Reuse **parameterized, tested, labeled patterns** instead of rewriting prompts each time.
- Organize your library **by job** with "best for / not for" notes.
- Promote your most-used patterns to **saved assistants / custom instructions** so you never paste them again.

🌐 [Polski](../../pl/lessons/14-biblioteka-wzorcow-promptow.md) · [← Prev](13-long-documents.md) · [Course home](../README.md) · [Next: Evaluating prompts →](15-evaluating-prompts.md)
