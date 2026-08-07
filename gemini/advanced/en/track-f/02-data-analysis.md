# F2 — Data Analysis (Run Code on Your Data)

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: the Gemini app, a small CSV or spreadsheet

🌐 [Polski](../../pl/track-f/02-analiza-danych.md) · [← Prev](01-canvas-build-and-ship.md) · [Track index](../README.md) · [Next: Connected apps & Workspace →](03-connected-apps.md)

---

## 🧠 Theory (4 min)

When you ask a chatbot to "add up this column," it often **guesses** from patterns — and can be wrong. Gemini can do better: it can **write and run code** to compute the answer on your actual data. Real math, not estimation.

Why it matters:

- **Accuracy.** Numbers are computed, not guessed — sums, averages, counts, filters in code.
- **Real files.** Upload a CSV/Excel and Gemini processes it.
- **Charts.** It can turn results into a visualization.
- **No coding by you.** You describe the analysis; Gemini writes and runs the code.

> Code execution / data analysis behavior can differ between the Gemini app and **Google AI Studio** (aistudio.google.com), where you can explicitly turn on a code-execution tool. If the app won't run code on your file, AI Studio is the reliable place to try it.

---

## 🛠️ Practice (10 min)

### Step 1 — Get some data

No file handy? Ask Gemini to make one:

```text
Create a sample CSV with 20 rows of fake monthly sales: columns month, region, amount.
Give me the file to download.
```

Download it (or use a small real spreadsheet).

### Step 2 — Upload and ask for real numbers

Attach the CSV and ask:

```text
Compute total and average sales per region, and tell me which region is highest
and lowest. Run the calculation and show the numbers.
```

Gemini computes and reports results — not a guess.

### Step 3 — Push on accuracy

```text
Show me the exact figures per month too, and confirm the totals add up.
```

Because it's real computation, the numbers reconcile. That's the point — trustworthy answers on data.

### Step 4 — Get a chart

```text
Now make a simple line chart of total sales by month, and point out any trend.
```

### Step 5 — Clean messy data

```text
This sheet has inconsistent region names (e.g. "north", "North ", "N").
Standardize them, then redo the per-region totals.
```

Painful by hand; quick with code.

### Step 6 — Trust but verify

You steer the method by how you ask. For anything important:
- Ask it to **show the figures** and **how it grouped/filtered**.
- Sanity-check one number yourself.

```text
Explain how you grouped the rows and which ones you excluded, if any.
```

---

## 🧩 Analysis vs plain chat

| Task | Use |
|------|-----|
| "What's 20% of 4,318?" | Either — but computed is exact |
| "Sum this 500-row column" | **Run code** (don't trust a guess) |
| "Clean and re-total this messy sheet" | **Run code** |
| "Chart sales by month" | **Run code** |
| "Explain what a median is" | Plain chat |

> ⚠️ **Still your data.** Don't upload anything sensitive you wouldn't want processed. Verify important numbers — you set the method by how you phrase the ask.

---

## ✅ Checkpoint

- [ ] You uploaded a CSV and got **computed** (not guessed) totals.
- [ ] You had Gemini show per-item figures and confirm they reconcile.
- [ ] You generated a chart from the data.
- [ ] You cleaned a messy column and recomputed (in the app or AI Studio).

---

## 🎯 Homework

Take a real spreadsheet (budget, a log, an export). Compute a summary, standardize a messy column, and produce one chart. Ask Gemini to explain its grouping so you trust the result.

---

## 💡 Key takeaways

- Gemini can **write and run code** on your files — accurate computation, no coding by you (use **AI Studio** if the app won't).
- Best for **sums/averages/filters, cleanup, and charts** where a guess would be risky.
- **You steer the method** — ask it to show figures and explain grouping, and verify anything important.

🌐 [Polski](../../pl/track-f/02-analiza-danych.md) · [← Prev](01-canvas-build-and-ship.md) · [Track index](../README.md) · [Next: Connected apps & Workspace →](03-connected-apps.md)
