# Lesson 03 — Be Specific: Clarity & Precision

⏱️ **11 minutes** · Level: Beginner · Needs: any AI chat

🌐 [Polski](../../pl/lessons/03-badz-konkretny.md) · [← Prev](02-anatomy-of-a-prompt.md) · [Course home](../README.md) · [Next: Context & the context window →](04-context-and-context-window.md)

---

## 🧠 Theory (4 min)

The single most common prompting mistake is being **vague**. The AI can't read your mind, so ambiguity gets filled with the model's *average guess* — rarely what you meant.

Three habits fix most vagueness:

1. **Say exactly what you want** — the output, not a hint toward it. "Give me 5 subject lines" beats "help with my email."
2. **Remove ambiguous words** — "good," "short," "some," "better" mean nothing precise. Replace with numbers and criteria: "under 60 characters," "3 options," "more formal than the draft."
3. **State the unspoken assumptions** — audience, purpose, language, what to avoid. If it matters to you, say it.

Specificity isn't longer prompts — it's **removing the room to guess wrong**.

---

## 🛠️ Practice (6 min)

### Step 1 — Kill the vague words

Vague:

```text
Make this email better and shorter.
```

Precise:

```text
Rewrite this email to be under 90 words, more polite, and with a clear
single call to action in the last line. Keep the meeting date unchanged.
```

### Step 2 — Replace adjectives with criteria

Instead of "make it engaging," say what engaging means *here*:

```text
Open with a surprising statistic, use "you," and keep sentences under 20 words.
```

### Step 3 — Name the audience and purpose

```text
This is for non-technical executives deciding whether to fund the project.
Focus on impact and cost, not implementation.
```

### Step 4 — Add negative constraints

Tell it what **not** to do:

```text
Don't use buzzwords, don't invent numbers, and don't exceed one paragraph.
```

### Step 5 — Test your prompt on a stranger

Read your prompt as if you knew nothing. Could you produce the wrong-but-technically-valid answer? If yes, tighten it.

---

## 🧩 Vague → precise swaps

| Vague | Precise |
|-------|---------|
| "short" | "under 100 words" |
| "a few examples" | "exactly 3 examples" |
| "make it better" | "fix grammar and cut passive voice" |
| "professional tone" | "formal, no contractions, third person" |
| "soon" | "by the last line, as a call to action" |

---

## ✅ Checkpoint

- [ ] You replaced vague words with numbers and criteria.
- [ ] You stated audience and purpose explicitly.
- [ ] You added at least one negative constraint (what not to do).
- [ ] You "read it as a stranger" and tightened any ambiguity.

---

## 🎯 Homework

Find a prompt you wrote earlier that underdelivered. Rewrite it removing every vague word — replace each with a number, a criterion, or a named audience. Re-run and compare.

---

## 💡 Key takeaways

- Vagueness gets filled with the model's **average guess** — specificity removes the room to guess wrong.
- Replace adjectives ("short," "good") with **numbers and criteria**.
- State **audience, purpose, and what to avoid** — and read your prompt as a stranger would.

🌐 [Polski](../../pl/lessons/03-badz-konkretny.md) · [← Prev](02-anatomy-of-a-prompt.md) · [Course home](../README.md) · [Next: Context & the context window →](04-context-and-context-window.md)
