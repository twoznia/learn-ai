# F3 — Research & Web Search (Cited, Up-to-Date Answers)

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: a Claude.ai account (Pro recommended)

🌐 [Polski](../../pl/track-f/03-badania-i-web.md) · [← Prev](02-analysis-tool.md) · [Track index](../README.md) · [Next: Productivity connectors →](04-productivity-connectors.md)

---

## 🧠 Theory (4 min)

By default Claude answers from what it learned during training, which has a **cutoff date** — so it can miss recent events or specific current facts. Two features fix that:

- **Web search** — Claude searches the live web mid-answer and returns results **with citations** you can click to verify.
- **Research** — an agentic mode where Claude runs **many** searches (and can pull from your connectors), then synthesizes a **sourced report**. Great for "look into X thoroughly," not just "what's the weather."

The habit to build: **know when you need fresh, verifiable info** — and then *insist on citations* so you can check the source.

> Names and availability of "Research" / advanced research vary by plan and roll out over time. If you don't see a dedicated Research button, plain **web search** still gives you cited, current answers.

---

## 🛠️ Practice (10 min)

### Step 1 — Turn on web search

Look under the message box (or the tools menu) for a **web search / tools** toggle and enable it. Now Claude can look things up when the question needs it.

### Step 2 — Ask something time-sensitive

```text
What are the current headline features of the latest Claude models? Cite your sources.
```

Claude searches, answers, and shows **citations**. Click one to confirm it says what Claude claims — that verify step is the whole discipline.

### Step 3 — Force grounding when it matters

For anything where being current changes the answer, ask explicitly:

```text
Search before answering — don't rely on memory. Give me 3 sources for each key claim.
```

This pushes Claude to ground the answer rather than recall it.

### Step 4 — Run a small research task

If you have a Research mode, use it; otherwise a multi-part web-search prompt works:

```text
Research options for backing up a Windows laptop for a non-technical person.
Compare 3 approaches, list pros/cons and rough cost, and cite sources. End with a recommendation.
```

You get a structured, **sourced** briefing instead of a vague summary.

### Step 5 — Always sanity-check sources

Citations make Claude checkable — use that:
- Click at least one source per key claim.
- Prefer answers where sources **agree**.
- Watch dates — an old page can be outdated even if it's real.

```text
Which of your sources is most recent and most authoritative, and why?
```

### Step 6 — Know when NOT to search

For timeless questions ("explain how DNS works") or your own uploaded files, searching adds noise. Reserve web/research for **current, external, verifiable** needs.

---

## 🧩 Which mode for which question

| Question | Use |
|----------|-----|
| "What happened / what's the latest…?" | Web search (cited) |
| "Compare current options for X, thoroughly" | Research |
| "Explain a stable concept" | Plain chat |
| "Summarize this file I uploaded" | Plain chat (no search) |
| Anything where being wrong costs you | Web/Research + **verify citations** |

---

## ✅ Checkpoint

- [ ] You enabled web search and got a **cited** answer.
- [ ] You clicked a citation and confirmed it supports the claim.
- [ ] You ran a small research task that produced a sourced comparison.
- [ ] You can say when searching helps vs when it just adds noise.

---

## 🎯 Homework

Pick a real decision you're researching (a purchase, a tool, a how-to). Have Claude research it with citations, verify two sources yourself, and note where the sources disagreed. Decide based on what you could actually verify.

---

## 💡 Key takeaways

- Web search and **Research** get you **current, verifiable** answers past Claude's training cutoff — with **citations**.
- **Insist on sources** and **click them** — citations are only useful if you check them.
- Use them for **current/external** needs; skip them for stable concepts and your own files.

🌐 [Polski](../../pl/track-f/03-badania-i-web.md) · [← Prev](02-analysis-tool.md) · [Track index](../README.md) · [Next: Productivity connectors →](04-productivity-connectors.md)
