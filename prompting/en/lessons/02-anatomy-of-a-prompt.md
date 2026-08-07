# Lesson 02 — The Anatomy of a Strong Prompt

⏱️ **11 minutes** · Level: Beginner · Needs: any AI chat

🌐 [Polski](../../pl/lessons/02-anatomia-promptu.md) · [← Prev](01-what-is-prompt-engineering.md) · [Course home](../README.md) · [Next: Be specific →](03-be-specific.md)

---

## 🧠 Theory (4 min)

Most strong prompts contain the same **building blocks**. You won't use all of them every time, but knowing them turns "write a prompt" into filling in a checklist.

| Block | What it does | Example |
|-------|--------------|---------|
| **Role** | Who the AI should be | "You are a patient math tutor." |
| **Task** | The single clear goal | "Explain the Pythagorean theorem." |
| **Context** | Background it needs | "The reader is a 12-year-old beginner." |
| **Format** | Shape of the output | "Use 3 short steps and one example." |
| **Constraints** | Limits & rules | "No jargon. Under 120 words." |
| **Examples** | A model to imitate | "Like this: …" |

Think **R-T-C-F-C**: Role, Task, Context, Format, Constraints (examples when helpful). A prompt that names these leaves little room for the AI to guess wrong.

---

## 🛠️ Practice (6 min)

### Step 1 — Build one block at a time

Start minimal:

```text
Explain recursion.
```

Add a **role** and **audience/context**:

```text
You are a friendly programming tutor. Explain recursion to someone who has
never coded before.
```

Add **format** and **constraints**:

```text
You are a friendly programming tutor. Explain recursion to someone who has
never coded before. Use a real-world analogy first, then 3 short bullet points.
Keep it under 150 words and avoid code.
```

Run each version and watch the answer sharpen.

### Step 2 — Use a template

Keep this skeleton in your journal and fill it in:

```text
Role: You are a ____.
Task: ____.
Context: ____.
Format: ____.
Constraints: ____.
```

### Step 3 — Add an example (optional)

If the shape matters, show one:

```text
Format like this:
Term — one-line definition — tiny example
```

### Step 4 — Trim what you don't need

Not every prompt needs a role or examples. Include a block only when it **changes the answer**. Clarity beats length.

---

## 🧩 Fill-in template

| Block | Your prompt |
|-------|-------------|
| Role | "You are a…" |
| Task | "Your job is to…" |
| Context | "The situation is…" |
| Format | "Respond as…" |
| Constraints | "Rules: …" |

---

## ✅ Checkpoint

- [ ] You can list the main prompt blocks (role, task, context, format, constraints).
- [ ] You built a prompt by adding one block at a time and saw it improve.
- [ ] You saved the fill-in template to your journal.
- [ ] You can explain when to *leave out* a block.

---

## 🎯 Homework

Pick a real task and write it with the full R-T-C-F-C template. Then delete any block that didn't change the output. Save the lean final version — you're learning to include exactly what's needed.

---

## 💡 Key takeaways

- Strong prompts are built from **Role, Task, Context, Format, Constraints** (plus examples when useful).
- Add each block only when it **changes the answer** — clarity beats length.
- A fill-in **template** turns prompt-writing into a repeatable checklist.

🌐 [Polski](../../pl/lessons/02-anatomia-promptu.md) · [← Prev](01-what-is-prompt-engineering.md) · [Course home](../README.md) · [Next: Be specific →](03-be-specific.md)
