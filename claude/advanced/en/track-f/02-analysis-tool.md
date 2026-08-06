# F2 — The Analysis Tool (Run Code in Chat)

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: a Claude.ai account, a small CSV or spreadsheet

🌐 [Polski](../../pl/track-f/02-narzedzie-analizy.md) · [← Prev](01-artifacts.md) · [Track index](../README.md) · [Next: Research & web →](03-research-and-web.md)

---

## 🧠 Theory (4 min)

When you ask a chatbot to "add up this column," it usually **guesses** the answer from patterns — and can be wrong. The **analysis tool** fixes that: Claude **writes and runs real code** (in the chat) to compute the answer for you. Actual math, on your actual data.

Why it matters:

- **Accuracy.** Numbers are computed, not estimated. Sums, averages, counts, filters — done in code.
- **Real files.** Upload a CSV/Excel and Claude processes it programmatically.
- **Charts.** It can turn results into a visualization.
- **No coding by you.** You describe the analysis in plain English; Claude writes the code and runs it.

This is different from the API/Claude Code path — it's built into the **chat**, no setup.

---

## 🛠️ Practice (10 min)

### Step 1 — Get some data

No file handy? Ask Claude to make one:

```text
Create a sample CSV with 20 rows of fake monthly sales: columns month, region, amount.
Give me the file to download.
```

Download it (or use a real small spreadsheet of your own).

### Step 2 — Upload and ask for real numbers

Attach the CSV (📎) and ask:

```text
Using the analysis tool, compute total and average sales per region, and tell me
which region is highest and lowest. Show the numbers.
```

Claude **runs code** over the file and reports computed results — not a guess.

### Step 3 — Push on accuracy

Ask it to prove the work:

```text
Show me the exact figures per month too, and confirm the totals add up.
```

Because it's real computation, the numbers reconcile. This is the whole point — trustworthy answers on data.

### Step 4 — Get a chart

```text
Now make a simple line chart of total sales by month, and point out any trend.
```

Claude computes the series and produces a visualization you can read at a glance.

### Step 5 — Clean messy data

The analysis tool shines on cleanup:

```text
This sheet has inconsistent region names (e.g. "north", "North ", "N").
Standardize them, then redo the per-region totals.
```

It normalizes the data in code and recomputes — a task that's painful by hand.

### Step 6 — Know when to trust vs verify

The analysis tool computes correctly, but **you choose the method** by how you ask. For anything important:
- Ask it to **show the figures** and **how it grouped/filtered**.
- Sanity-check one number yourself.

```text
Explain how you grouped the rows and which ones you excluded, if any.
```

---

## 🧩 Analysis tool vs plain chat

| Task | Use |
|------|-----|
| "What's 20% of 4,318?" | Either — but analysis is exact |
| "Sum this 500-row column" | **Analysis tool** (don't trust a guess) |
| "Clean and re-total this messy sheet" | **Analysis tool** |
| "Chart sales by month" | **Analysis tool** |
| "Explain what a median is" | Plain chat |

> ⚠️ **Still your data.** Don't upload anything sensitive you wouldn't want processed. And verify important numbers — you set the method by how you phrase the ask.

---

## ✅ Checkpoint

- [ ] You uploaded a CSV and got **computed** (not guessed) totals.
- [ ] You had Claude show the per-item figures and confirm they reconcile.
- [ ] You generated a chart from the data.
- [ ] You cleaned a messy column and recomputed.

---

## 🎯 Homework

Take a real spreadsheet from your life (budget, a log, an export). Use the analysis tool to compute a summary, standardize any messy column, and produce one chart. Ask it to explain its grouping so you trust the result.

---

## 💡 Key takeaways

- The **analysis tool** makes Claude **write and run code** in chat — real, accurate computation on your files, no coding by you.
- Best for **sums/averages/filters, cleanup, and charts** where a guessed answer would be risky.
- **You steer the method** — ask it to show figures and explain grouping, and verify anything important.

🌐 [Polski](../../pl/track-f/02-narzedzie-analizy.md) · [← Prev](01-artifacts.md) · [Track index](../README.md) · [Next: Research & web →](03-research-and-web.md)
