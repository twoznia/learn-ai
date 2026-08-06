# Lesson 15 — Web Search & Browsing

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: ChatGPT (app or web)

🌐 [Polski](../../pl/lessons/15-wyszukiwanie-web.md) · [← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Theory (4 min)

An LLM only "knows" what it learned during training, so it can be out of date or make things up. **Web search** fixes this: ChatGPT can **look things up on the internet while answering**, then base its reply on what it found and show you the sources.

Why it matters for beginners:
- Ask about **recent events, prices, versions** — things training data can't know.
- Get answers **with links** you can verify.
- Reduce hallucinations for factual questions.

> ⚠️ Search isn't magic — sources can be wrong too. Read the cited links for anything important.

---

## 🛠️ Practice (5 min)

### Step 1 — Ask a "fresh info" question

Open ChatGPT and ask something that needs current information:

```text
What are 3 recent, notable developments in electric cars this month? Include sources with links.
```

ChatGPT will typically search the web and answer with **citations**. Click a source to verify.

### Step 2 — Turn search on explicitly (if needed)

If it answers from memory instead of searching, look for a **Search / web** toggle or tool near the message box (a globe icon), enable it, and ask again. Or just tell it:

```text
Search the web and cite your sources for this: <your question>
```

### Step 3 — Compare with "no search"

Ask a time-sensitive question **without** search, then again **with** search:

```text
Who currently holds <some record/role that changed recently>?
```

Notice the difference: the searched answer is fresher and comes with links. That contrast is the whole point.

### Step 4 — Summarize a live page

Paste a link and ask:

```text
Read this page and summarize it in 5 bullets, then list anything I should double-check:
<paste a URL>
```

---

## 🧭 When to use web search

| Use search for… | Skip it for… |
|--------------------|--------------|
| Recent news, prices, releases | Timeless explanations ("what is a fraction") |
| "As of today…" questions | Creative writing / brainstorming |
| Facts you'll act on | Rewriting your own text |

> 💡 **For coders:** the OpenAI API also offers built-in tools (like web search) you can enable in code. That's an advanced next step — the app is the easiest place to start.

---

## ✅ Checkpoint

- [ ] You asked a "fresh info" question and got sources.
- [ ] You found or triggered the web/search option.
- [ ] You compared a searched vs unsearched answer.

---

## 🎯 Homework

Pick a question where the answer changed recently (a product's latest version, a current price). Ask ChatGPT with search, then click a source to confirm. That verify step is what separates smart AI users from the rest.

---

## 💡 Key takeaways

- **Web search** connects ChatGPT's answers to live sources with citations.
- Enable the search/web toggle, or just ask it to "search the web and cite sources".
- Use it for fresh/factual questions; still click the sources for anything important.

🌐 [Polski](../../pl/lessons/15-wyszukiwanie-web.md) · [← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)
