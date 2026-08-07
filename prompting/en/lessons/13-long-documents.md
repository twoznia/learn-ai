# Lesson 13 — Working with Long Documents

⏱️ **11 minutes** · Level: Advanced · Needs: any AI chat (file upload helps)

🌐 [Polski](../../pl/lessons/13-dlugie-dokumenty.md) · [← Prev](12-self-critique-and-iteration.md) · [Course home](../README.md) · [Next: A prompt-pattern library →](14-prompt-pattern-library.md)

---

## 🧠 Theory (4 min)

Long inputs — reports, transcripts, contracts, codebases — strain the context window and dilute the model's focus. Prompting well with them is its own skill.

Key tactics:

- **Point precisely.** Ask about a specific section rather than "the whole thing."
- **Summarize in layers.** Summarize each part, then summarize the summaries — a hierarchy that fits big material into a small window.
- **Chunk long inputs.** Split a huge document into pieces, process each, then combine (a chain from Lesson 9).
- **Ground and cite.** With long sources, always make the model quote where an answer came from (Lesson 11) — it's easy to lose the thread otherwise.

Modern tools with **file upload** or large windows help, but the *technique* — focus, layer, chunk, cite — is what makes answers reliable.

---

## 🛠️ Practice (6 min)

### Step 1 — Ask a targeted question

Instead of "summarize this 40-page report":

```text
From the attached report, extract only the recommendations in Section 4, as a
bulleted list, quoting the sentence each comes from.
```

### Step 2 — Layered summary

```text
Summarize each of the 5 sections in 2 sentences. Then write one 4-sentence
overall summary built from those.
```

### Step 3 — Chunk a huge input

If it won't fit, split it:

```text
This is part 1 of 3 of a transcript. Summarize just this part into 5 bullets.
I'll send parts 2 and 3, then ask you to merge.
```

Then:

```text
Here are the 3 partial summaries. Merge them into one coherent summary,
removing duplicates.
```

### Step 4 — Extract structured data

```text
From this contract, extract into a table: Clause | Obligation | Party | Deadline.
Quote the source text for each row.
```

### Step 5 — Guard against lost detail

```text
If any part is ambiguous or missing needed info, list those gaps rather than
guessing.
```

---

## 🧩 Long-input tactics

| Situation | Tactic |
|-----------|--------|
| Only need one part | Point at that section |
| Too big for the window | Chunk → summarize → merge |
| Need the big picture | Layered (hierarchical) summary |
| Need facts you'll rely on | Extract + quote sources |
| Risk of missing info | Ask it to list gaps |

> ⚠️ With long sources, un-grounded answers are riskier — always ask for **quotes/citations** and watch for lost detail.

---

## ✅ Checkpoint

- [ ] You asked a targeted question instead of "summarize everything."
- [ ] You produced a layered (hierarchical) summary.
- [ ] You chunked a long input and merged the parts.
- [ ] You extracted structured data with source quotes.

---

## 🎯 Homework

Take a long document you actually have. Get three things from it: the recommendations in one section (with quotes), a layered summary, and a structured table of key facts. Note where quoting the source caught a detail you'd have missed.

---

## 💡 Key takeaways

- For long inputs: **point precisely, summarize in layers, chunk-and-merge, and cite sources**.
- Large windows and file upload help, but the **technique** is what keeps answers reliable.
- Un-grounded answers over long sources are risky — **demand quotes** and watch for lost detail.

🌐 [Polski](../../pl/lessons/13-dlugie-dokumenty.md) · [← Prev](12-self-critique-and-iteration.md) · [Course home](../README.md) · [Next: A prompt-pattern library →](14-prompt-pattern-library.md)
