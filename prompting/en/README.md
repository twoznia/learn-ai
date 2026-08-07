# Prompt Engineering — Cross-Provider Lessons

🌐 **Language:** **English** · [Polski](../pl/README.md) · [↩ Course landing](../README.md) · [↩ All courses](../../README.md)

A hands-on course that teaches you to **write prompts that reliably work** — with any AI chat (Claude, Gemini, or ChatGPT). From the anatomy of a good prompt to few-shot examples, chain-of-thought, grounding against hallucinations, and testing your prompts like an engineer. ~10–12 minutes per lesson.

Every lesson has:

- 🧠 **Theory** — the idea, explained simply
- 🛠️ **Practice** — prompts you run yourself in any AI chat
- ✅ **Checkpoint** — how to know it worked
- 🎯 **Homework** — a tiny task to lock it in
- 💡 **Key takeaways**

The skills are **provider-neutral** — every technique works across Claude, Gemini, and ChatGPT. It starts easy and gets progressively deeper; no coding required.

---

## How to use this course

1. Do the lessons **in order** — each builds on the last.
2. Run every **Practice** prompt yourself in whichever AI chat you use.
3. Keep a **`my-prompts.md`** journal (Lesson 1) — by the end you'll have a reusable library.
4. Try prompts on more than one provider if you can — watch the skills transfer.

---

## Curriculum

### Part 1 — Foundations

| # | Lesson | What you'll learn |
|---|--------|-------------------|
| 01 | [What is prompt engineering?](lessons/01-what-is-prompt-engineering.md) | How LLMs read prompts; why skills transfer |
| 02 | [Anatomy of a strong prompt](lessons/02-anatomy-of-a-prompt.md) | Role, task, context, format, constraints |
| 03 | [Be specific: clarity & precision](lessons/03-be-specific.md) | Remove the room to guess wrong |
| 04 | [Context & the context window](lessons/04-context-and-context-window.md) | Supply what's needed, cut the noise |

### Part 2 — Core techniques

| # | Lesson | What you'll learn |
|---|--------|-------------------|
| 05 | [Structure & formatting](lessons/05-structure-and-formatting.md) | Delimiters, sections, output shape |
| 06 | [Few-shot prompting](lessons/06-few-shot-prompting.md) | Examples that steer the pattern |
| 07 | [Role & system prompts](lessons/07-role-and-system-prompts.md) | Personas and standing instructions |
| 08 | [Step-by-step reasoning](lessons/08-step-by-step-reasoning.md) | Chain-of-thought for hard problems |
| 09 | [Decomposition & chaining](lessons/09-decomposition-and-chaining.md) | Break tasks; feed output into input |

### Part 3 — Reliability

| # | Lesson | What you'll learn |
|---|--------|-------------------|
| 10 | [Controlling the output](lessons/10-controlling-output.md) | Length, tone, tables, JSON/schema |
| 11 | [Reducing hallucinations](lessons/11-reducing-hallucinations.md) | Ground, cite, and verify |
| 12 | [Self-critique & iteration](lessons/12-self-critique-and-iteration.md) | Treat answers as drafts to refine |
| 13 | [Working with long documents](lessons/13-long-documents.md) | Point, layer, chunk, cite |

### Part 4 — Applied & professional

| # | Lesson | What you'll learn |
|---|--------|-------------------|
| 14 | [A reusable prompt-pattern library](lessons/14-prompt-pattern-library.md) | Parameterized, tested templates |
| 15 | [Evaluating & testing prompts](lessons/15-evaluating-prompts.md) | Rubrics, test sets, A/B comparison |
| 16 | [Safety & putting it together](lessons/16-safety-and-putting-it-together.md) | Prompt injection, verification, a master prompt |

---

## Quick glossary (bookmark this)

| Term | Meaning in one line |
|------|---------------------|
| **Prompt** | The instructions you give the AI |
| **Context** | Everything the AI can see in the current conversation |
| **Context window** | How much text the model can hold at once |
| **Zero-shot** | Describing a task with no examples |
| **Few-shot** | Giving a few input→output examples |
| **Chain-of-thought** | Asking the model to reason step by step |
| **System prompt** | A standing instruction applied to every message |
| **Grounding** | Making answers rely on provided sources |
| **Hallucination** | The model stating something false as if true |
| **Prompt injection** | Hidden instructions in untrusted content |

---

## Start here 👉 [Lesson 01 — What is prompt engineering?](lessons/01-what-is-prompt-engineering.md)

*Educational material. The techniques are provider-neutral; specific product screens and features change over time, but the principles apply everywhere.*
