# Lesson 15 — Grounding with Google Search

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: Python + API key (or the Gemini app)

🌐 [Polski](../../pl/lessons/15-grounding-google-search.md) · [← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Theory (4 min)

An LLM only "knows" what it learned during training, so it can be out of date or make things up. **Grounding** fixes this by connecting Gemini's answer to **live sources** — most powerfully, **Google Search**.

When grounding is on, Gemini can **search the web while answering**, then base its reply on what it found and show you the sources. This is a signature Gemini feature and Google's answer to "how do I trust the answer?"

Why it matters for beginners:
- Ask about **recent events, prices, versions** — things training data can't know.
- Get answers **with links** you can verify.
- Reduce hallucinations for factual questions.

> ⚠️ Grounding still isn't magic — sources can be wrong too. Read the cited links for anything important.

---

## 🛠️ Practice (5 min)

### Path A — In the Gemini app (no code)

1. Open **gemini.google.com**.
2. Ask a question that needs fresh info, e.g.:

```text
What are 3 recent, notable developments in electric cars this month? Include sources.
```

3. Look for **source links / citations** in the answer and click one to verify. Many answers already use Google under the hood.

### Path B — In Python (turn on Search grounding)

Google's SDK lets you attach Google Search as a **tool**. Create `grounded.py`:

```powershell
cd $HOME\learn-ai-gemini
notepad grounded.py
```

Paste and save:

```python
from google import genai
from google.genai import types

client = genai.Client()

# Enable the Google Search tool so Gemini can look things up live
grounding_tool = types.Tool(google_search=types.GoogleSearch())

response = client.models.generate_content(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(tools=[grounding_tool]),
    contents="Who won the most recent Formula 1 race, and when was it? Answer briefly.",
)

print(response.text)
```

Run it:

```powershell
python grounded.py
```

Gemini searches, then answers with up-to-date info. 🎉 Compare it to asking **without** the tool — the ungrounded answer may be stale or hedged.

### Try both

Run the same question with and without `tools=[grounding_tool]`. Seeing the difference is the whole point: grounding = fresher, source-backed answers.

---

## 🧭 When to use grounding

| Use grounding for… | Skip it for… |
|--------------------|--------------|
| Recent news, prices, releases | Timeless explanations ("what is a fraction") |
| "As of today…" questions | Creative writing / brainstorming |
| Facts you'll act on | Rewriting your own text |

---

## ✅ Checkpoint

- [ ] You asked a "fresh info" question in the app and checked a source.
- [ ] You ran `grounded.py` with the Google Search tool.
- [ ] You compared grounded vs ungrounded answers.

---

## 🎯 Homework

Pick a question where the answer changed recently (a product's latest version, a current price). Ask Gemini grounded, then click a source to confirm. That verify step is what separates smart AI users from the rest.

---

## 💡 Key takeaways

- **Grounding** connects Gemini's answers to live sources like Google Search.
- In code, add `types.Tool(google_search=types.GoogleSearch())` to the config.
- Use it for fresh/factual questions; still click the sources for anything important.

🌐 [Polski](../../pl/lessons/15-grounding-google-search.md) · [← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)
