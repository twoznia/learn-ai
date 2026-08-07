# Lesson 15 — Evaluating & Testing Your Prompts

⏱️ **11 minutes** · Level: Advanced · Needs: any AI chat

🌐 [Polski](../../pl/lessons/15-ewaluacja-promptow.md) · [← Prev](14-prompt-pattern-library.md) · [Course home](../README.md) · [Next: Safety & putting it together →](16-safety-and-putting-it-together.md)

---

## 🧠 Theory (4 min)

"Feels good" isn't a measure. If you rely on a prompt — especially a reused one — you should be able to say **why** it's good and **whether a change made it better**. That's prompt **evaluation**.

The essentials, borrowed from how engineers test anything:

- **Define success first.** What does a good answer contain? Write criteria *before* judging.
- **Test on several inputs.** A prompt that works on one example may fail on others. Try easy, hard, and edge cases.
- **Compare fairly (A/B).** Change **one thing** between two prompt versions and run both on the same inputs.
- **Watch consistency.** Run the same prompt a few times — does it hold up, or is it a lucky one-off?

You don't need fancy tooling — a rubric and a handful of test cases beat gut feel.

---

## 🛠️ Practice (6 min)

### Step 1 — Write a success rubric

Before judging outputs, define good:

```text
A good summary: (1) ≤5 bullets, (2) covers all key points, (3) no invented
facts, (4) readable by a non-expert.
```

### Step 2 — Make a small test set

Pick 3–5 representative inputs — including a tricky one and an edge case. Save them with your prompt.

### Step 3 — Run an A/B test

Version A vs Version B (one change — say, adding an example). Run both on every test input and score against your rubric. Keep the winner.

### Step 4 — Check consistency

```text
Run the same prompt on the same input 3 times.
```

If results swing wildly, tighten the prompt (more structure, examples, constraints).

### Step 5 — Let the model help grade

For subjective output, use a rubric-based check (an "LLM as judge"):

```text
Score this answer 1–5 on each rubric criterion and justify each score.
```

Use it as a *signal*, not the final word — spot-check yourself.

### Step 6 — Log what wins

In `my-prompts.md`, note which version won and why. Your library gets measurably better over time.

---

## 🧩 A lightweight eval loop

| Step | Do |
|------|-----|
| 1. Criteria | Define "good" before judging |
| 2. Test set | 3–5 inputs incl. hard/edge |
| 3. A/B | Change one thing, run both |
| 4. Consistency | Repeat; watch for swings |
| 5. Judge | Rubric scoring (self + model) |
| 6. Log | Record the winner and why |

---

## ✅ Checkpoint

- [ ] You wrote success criteria before judging outputs.
- [ ] You built a small test set with a hard/edge case.
- [ ] You A/B-tested two versions on the same inputs.
- [ ] You checked consistency across repeated runs.

---

## 🎯 Homework

Take your most-used pattern. Write a rubric, pick 4 test inputs, and A/B-test two variants (change one thing). Score both, keep the winner, and log the result in your library. You've just made a prompt provably better.

---

## 💡 Key takeaways

- Evaluate prompts with **criteria defined first**, a **small test set**, and **one-change A/B** comparisons.
- Check **consistency** across repeated runs; tighten prompts that swing.
- Use **rubric scoring** (yourself + the model as a signal) and **log the winners**.

🌐 [Polski](../../pl/lessons/15-ewaluacja-promptow.md) · [← Prev](14-prompt-pattern-library.md) · [Course home](../README.md) · [Next: Safety & putting it together →](16-safety-and-putting-it-together.md)
