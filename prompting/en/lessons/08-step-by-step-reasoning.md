# Lesson 08 — Step-by-Step Reasoning

⏱️ **11 minutes** · Level: Intermediate · Needs: any AI chat

🌐 [Polski](../../pl/lessons/08-rozumowanie-krok-po-kroku.md) · [← Prev](07-role-and-system-prompts.md) · [Course home](../README.md) · [Next: Decomposition & chaining →](09-decomposition-and-chaining.md)

---

## 🧠 Theory (4 min)

On problems that need **reasoning** — math, logic, multi-step decisions, careful analysis — asking the model to **work through it step by step** dramatically improves accuracy. This is often called **chain-of-thought** prompting.

Why: when a model tries to jump straight to an answer, it can commit to a wrong guess. Giving it room to reason first lets it "show its work," catch its own missteps, and arrive at a better final answer.

How to trigger it:

- "Think step by step before answering."
- "Work through this carefully, then give the final answer."
- "Show your reasoning, then a clear conclusion."

Two notes:
- Modern **"reasoning" models** may do this internally — but explicitly asking still helps on hard problems, and lets *you* inspect the logic.
- For simple factual asks, step-by-step is unnecessary overhead. Use it where reasoning matters.

---

## 🛠️ Practice (6 min)

### Step 1 — See the difference

Ask directly:

```text
A shirt costs $40 after a 20% discount. What was the original price?
```

Then ask for reasoning:

```text
A shirt costs $40 after a 20% discount. Think step by step, then give the
original price.
```

The second is more likely correct on trickier versions — and you can check the steps.

### Step 2 — Separate reasoning from the answer

```text
First, reason through the trade-offs. Then, on a new line starting with
"ANSWER:", give your one-sentence recommendation.
```

This gives you both the thinking and a clean takeaway.

### Step 3 — Ask it to consider options

For decisions:

```text
List the 3 most plausible options, weigh each briefly, then pick one and explain
why it beats the others.
```

### Step 4 — Have it check its own work

```text
Solve it, then verify your answer by plugging it back in. If it doesn't check
out, redo it.
```

### Step 5 — Know when to skip it

For "What's the capital of Japan?" you don't need reasoning. Reserve chain-of-thought for problems where a wrong quick answer is likely.

---

## 🧩 When to ask for reasoning

| Task | Step-by-step? |
|------|---------------|
| Math / logic puzzle | ✅ Yes |
| Multi-factor decision | ✅ Yes |
| Careful analysis / diagnosis | ✅ Yes |
| Simple fact lookup | ❌ Skip |
| Quick rewrite | ❌ Skip |

> Want a tidy result? Ask it to reason **first**, then give a clearly labeled final answer you can lift out.

---

## ✅ Checkpoint

- [ ] You compared a direct answer with a step-by-step one.
- [ ] You separated the reasoning from a labeled final answer.
- [ ] You asked the model to verify its own result.
- [ ] You can name tasks where step-by-step is *not* worth it.

---

## 🎯 Homework

Take a problem you'd normally eyeball (a calculation, a plan, a trade-off). Prompt it two ways — direct, and "think step by step, then answer." Compare accuracy and note where the reasoning caught a mistake.

---

## 💡 Key takeaways

- For reasoning tasks, **"think step by step"** improves accuracy and lets you inspect the logic.
- Ask for reasoning **first**, then a **labeled final answer** you can extract cleanly.
- Skip chain-of-thought for **simple factual** asks — use it where a wrong quick answer is likely.

🌐 [Polski](../../pl/lessons/08-rozumowanie-krok-po-kroku.md) · [← Prev](07-role-and-system-prompts.md) · [Course home](../README.md) · [Next: Decomposition & chaining →](09-decomposition-and-chaining.md)
