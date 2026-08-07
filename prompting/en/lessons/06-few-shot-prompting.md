# Lesson 06 — Few-Shot Prompting (Examples That Steer)

⏱️ **11 minutes** · Level: Intermediate · Needs: any AI chat

🌐 [Polski](../../pl/lessons/06-few-shot.md) · [← Prev](05-structure-and-formatting.md) · [Course home](../README.md) · [Next: Role & system prompts →](07-role-and-system-prompts.md)

---

## 🧠 Theory (4 min)

Sometimes the fastest way to explain what you want is to **show** it. Giving the model a few input→output **examples** in your prompt is called **few-shot prompting** (as opposed to **zero-shot**, where you just describe the task).

Why it works: LLMs are superb pattern-matchers. A couple of good examples pin down tone, format, and edge-case handling far more precisely than adjectives can.

When to use which:

- **Zero-shot** — the task is common and clear ("translate this to French"). Describing is enough.
- **Few-shot** — the output shape is specific, the style is subtle, or you keep getting *almost* the right thing. Show 2–4 examples.

The examples teach the *pattern*; the model applies it to your new input.

---

## 🛠️ Practice (6 min)

### Step 1 — Turn a fuzzy ask into examples

Instead of "make product names catchy," show the pattern:

```text
Rewrite each feature as a catchy name. Examples:

Feature: syncs files automatically → Name: "Always in Sync"
Feature: works without internet → Name: "Offline-Ready"

Now do these:
Feature: shares with one click →
Feature: backs up every hour →
```

### Step 2 — Use examples to fix format drift

If the model keeps varying the format, one example locks it:

```text
Classify the sentiment. Format exactly like the example.

Input: "The app crashes constantly." → Output: NEGATIVE (reliability)

Input: "Love the new design!" →
```

### Step 3 — Show an edge case

Examples are great for teaching exceptions:

```text
Extract the date as YYYY-MM-DD. If no date is present, output "NONE".

"Meeting on March 3, 2026" → 2026-03-03
"Call me sometime" → NONE

"Ship it by 12/25/2026" →
```

### Step 4 — Keep examples consistent

Your examples are a contract. If they're inconsistent, the output will be too. Make every example follow the *exact* pattern you want.

### Step 5 — Don't over-shoot

2–4 strong, varied examples usually beat ten repetitive ones (and cost less context). Add an example only when it teaches something new.

---

## 🧩 Zero-shot vs few-shot

| | Zero-shot | Few-shot |
|--|-----------|----------|
| You give | A description | A description + examples |
| Best when | Common, clear task | Specific format, subtle style, edge cases |
| Cost | Cheapest | A bit more context |
| Superpower | Fast | Precise, consistent |

---

## ✅ Checkpoint

- [ ] You wrote a few-shot prompt with 2–4 consistent examples.
- [ ] You used an example to lock a specific output format.
- [ ] You taught an edge case via an example.
- [ ] You can say when zero-shot is enough vs when to add examples.

---

## 🎯 Homework

Take a task where the AI keeps giving *almost* the right format. Add 2–3 examples that demonstrate the exact pattern (including one edge case). Confirm the output now matches, and save the few-shot prompt to your journal.

---

## 💡 Key takeaways

- **Few-shot** = show 2–4 input→output examples; **zero-shot** = just describe the task.
- Use examples when the **format is specific, the style is subtle, or you need edge-case handling**.
- Examples are a **contract** — keep them consistent, varied, and minimal.

🌐 [Polski](../../pl/lessons/06-few-shot.md) · [← Prev](05-structure-and-formatting.md) · [Course home](../README.md) · [Next: Role & system prompts →](07-role-and-system-prompts.md)
