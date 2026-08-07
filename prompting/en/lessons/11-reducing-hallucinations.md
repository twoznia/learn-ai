# Lesson 11 — Reducing Hallucinations & Grounding Answers

⏱️ **12 minutes** · Level: Advanced · Needs: any AI chat

🌐 [Polski](../../pl/lessons/11-ograniczanie-halucynacji.md) · [← Prev](10-controlling-output.md) · [Course home](../README.md) · [Next: Self-critique & iteration →](12-self-critique-and-iteration.md)

---

## 🧠 Theory (4 min)

A **hallucination** is when the model states something false as if it were true — an invented fact, a fake citation, a made-up API. It happens because the model predicts *plausible* text, and plausible isn't always correct. You can't eliminate it, but good prompting **greatly reduces** it.

Core tactics:

1. **Ground the answer in provided sources.** Give the model the text to use and say "answer only from this." It can't invent what it's told to stick to.
2. **Give it an out.** Explicitly allow "I don't know." Models hallucinate partly because they act as if they must always answer.
3. **Ask for uncertainty and sources.** "Flag anything you're unsure of" and "cite where each claim comes from" surface shaky parts.
4. **Verify independently.** For anything that matters, check the claim yourself — especially names, numbers, quotes, and citations.

---

## 🛠️ Practice (7 min)

### Step 1 — Ground it in your text

```text
Answer using ONLY the document below. If the answer isn't in it, say
"Not stated in the document." Do not use outside knowledge.

"""
[paste the source]
"""

Question: …
```

### Step 2 — Give permission to say "I don't know"

```text
If you're not confident, say so instead of guessing. It's better to say
"I'm not sure" than to invent an answer.
```

### Step 3 — Ask it to separate fact from inference

```text
Mark each statement as [FROM SOURCE] or [MY INFERENCE], so I can see what's
grounded vs. reasoned.
```

### Step 4 — Demand checkable citations

```text
For each claim, quote the exact sentence from the source it's based on.
```

If it can't quote a source, that claim is suspect.

### Step 5 — Stress-test a risky answer

```text
What would make this answer wrong? List assumptions that, if false, break it.
```

### Step 6 — Verify what matters

Treat names, statistics, quotes, legal/medical/financial claims, and citations as **unverified** until you check them yourself. Cited ≠ correct.

---

## 🧩 Anti-hallucination toolkit

| Tactic | Prompt move |
|--------|-------------|
| Ground | "Answer only from this source" |
| Allow uncertainty | "Say 'I don't know' if unsure" |
| Separate | "Mark fact vs inference" |
| Cite | "Quote the sentence each claim uses" |
| Verify | You check names/numbers/citations |

> ⚠️ These reduce, not remove, hallucination. For high-stakes answers, **independent verification is non-negotiable**.

---

## ✅ Checkpoint

- [ ] You grounded an answer in a provided source and it declined to go beyond it.
- [ ] You gave the model permission to say "I don't know."
- [ ] You had it separate facts from inferences (or cite sentences).
- [ ] You verified a factual claim yourself.

---

## 🎯 Homework

Ask the AI a factual question in your field two ways: once open, once grounded in a source you paste with "answer only from this; say if it's not there." Compare. Then fact-check one claim from the open answer — did it hold up?

---

## 💡 Key takeaways

- **Hallucinations** come from predicting *plausible* text — reduce them by **grounding** answers in provided sources.
- **Give the model an out** ("I don't know") and ask it to **cite sentences** and **flag uncertainty**.
- These tactics reduce but don't remove the risk — **verify anything that matters yourself**.

🌐 [Polski](../../pl/lessons/11-ograniczanie-halucynacji.md) · [← Prev](10-controlling-output.md) · [Course home](../README.md) · [Next: Self-critique & iteration →](12-self-critique-and-iteration.md)
