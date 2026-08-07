# Lesson 12 — Self-Critique & Iteration

⏱️ **11 minutes** · Level: Intermediate → Advanced · Needs: any AI chat

🌐 [Polski](../../pl/lessons/12-autokrytyka-i-iteracja.md) · [← Prev](11-reducing-hallucinations.md) · [Course home](../README.md) · [Next: Working with long documents →](13-long-documents.md)

---

## 🧠 Theory (4 min)

The first answer is a **draft**, not the final word. Two of the most powerful (and underused) prompting moves are asking the model to **critique its own work** and then **improve it** — and treating the whole interaction as a loop.

Why self-critique works: reviewing is a different task from generating. Asked to *evaluate* against criteria, the model often spots weaknesses it produced moments earlier.

Why iteration works: you rarely get the perfect prompt on try one. Instead of rewriting from scratch, **refine in place** — "good, but shorter and less formal" — steering the model toward what you want.

The mindset shift: you're not asking a question, you're **running a short editing process** with the model.

---

## 🛠️ Practice (6 min)

### Step 1 — Ask for a self-critique

After an answer:

```text
Critique your previous response against these criteria: accuracy, clarity, and
whether it answered the actual question. List weaknesses, then a stronger version.
```

### Step 2 — Give the rubric up front

```text
Draft the email, then score it 1–5 on clarity, warmth, and brevity, and revise
anything under 4.
```

### Step 3 — Iterate, don't restart

Refine with small nudges instead of a new prompt:

```text
Tighter. Cut the intro. Make the last line a question.
```

### Step 4 — Ask for alternatives, then combine

```text
Give me 3 different openings with different angles. I'll pick, then you refine.
```

### Step 5 — Have it find its own errors

```text
Before I use this, list anything that might be wrong, unclear, or missing.
```

### Step 6 — Know when to stop

Iteration has diminishing returns. When the answer meets your criteria, stop — don't polish forever.

---

## 🧩 Iteration moves

| Move | Prompt |
|------|--------|
| Self-critique | "Critique this against [criteria], then improve it" |
| Self-score | "Rate 1–5 on X, Y, Z and fix anything under 4" |
| Refine in place | "Shorter, warmer, drop the intro" |
| Diverge then converge | "3 options" → "refine #2" |
| Pre-mortem | "What's wrong or missing before I use it?" |

---

## ✅ Checkpoint

- [ ] You asked the model to critique its own answer against criteria.
- [ ] You had it self-score and revise weak parts.
- [ ] You iterated with small nudges instead of rewriting the prompt.
- [ ] You stopped when the answer met your criteria.

---

## 🎯 Homework

Take any first answer you got today. Run one self-critique pass ("evaluate against accuracy, clarity, brevity; then improve") and two small refinement nudges. Compare the final to the original — that gap is the value of iterating.

---

## 💡 Key takeaways

- The first answer is a **draft** — ask the model to **critique against criteria** and improve it.
- **Iterate with small nudges** ("shorter, warmer") instead of starting the prompt over.
- Use **diverge-then-converge** (options → refine) and a **pre-mortem** — and stop when criteria are met.

🌐 [Polski](../../pl/lessons/12-autokrytyka-i-iteracja.md) · [← Prev](11-reducing-hallucinations.md) · [Course home](../README.md) · [Next: Working with long documents →](13-long-documents.md)
