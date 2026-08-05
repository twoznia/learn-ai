# Lesson 16 — Prompt Engineering That Actually Works

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: any Gemini (web/code)

🌐 [Polski](../../pl/lessons/16-prompt-engineering.md) · [← Prev](15-grounding-google-search.md) · [Course home](../README.md) · [Next: Costs & safety →](17-costs-safety.md)

---

## 🧠 Theory (4 min)

You learned the basics (R-C-T-F) in Lesson 3. Here are the **patterns professionals use** for consistently great results. None require code — they work anywhere you chat with Gemini.

### 1. Give examples (few-shot)

Show the pattern you want, then ask for more.

```text
Turn product names into catchy taglines. Examples:

"Solar Charger" → "Power from the sky, wherever you are."
"Noise-cancelling headphones" → "Your quiet, on demand."

Now do these:
"Reusable water bottle"
"Standing desk"
```

### 2. Ask Gemini to think before answering

For tricky reasoning, add:

```text
Think through this step by step before giving your final answer.
```

This visibly improves math, logic, and planning.

### 3. Assign a clear role + audience

```text
You are a pediatric nurse explaining to a worried parent. Explain what a
fever of 38.5°C means and when to see a doctor. Warm tone, simple words.
```

### 4. Constrain the output format

```text
Answer ONLY as valid JSON with keys: "summary", "risk_level" (low/medium/high),
and "next_step". No extra text.
```

### 5. Let it ask you questions first

```text
I want to plan a birthday party. Before giving advice, ask me up to 4
questions you need to give a great plan.
```

### 6. Iterate — the answer is a draft

```text
Make it shorter.
Now make it funnier.
Now rewrite it for LinkedIn.
```

---

## 🛠️ Practice (5 min)

Try each on your own content in gemini.google.com:

### Drill 1 — Few-shot
Give Gemini 2 examples of the tone you use in work emails, then ask for a new one in that same tone.

### Drill 2 — Step-by-step reasoning
```text
A shop offers "buy 2 get 1 free" on socks at $6 each. I want 9 pairs.
Think step by step, then tell me the total cost.
```

### Drill 3 — Strict format
```text
Extract the details from this text as JSON with keys "name", "date", "location".
Text: "Lunch with Priya on March 3rd at Cafe Rio."
Return only JSON.
```

### Drill 4 — Clarifying questions
```text
Help me write a resume summary. Ask me what you need to know first.
```

---

## 🧰 Copy-paste "power prompt" template

Keep this in your `my-prompts.txt` and fill the blanks:

```text
Role: You are <who>.
Audience: <who is this for>.
Task: <what you want>.
Context: <background, constraints, examples>.
Format: <how the answer should look>.
Rules:
- If you're unsure of a fact, say so.
- Ask me a clarifying question if anything is ambiguous.
- Keep it <length/tone>.

Here is the input:
<paste your content>
```

---

## ⚠️ Common mistakes to avoid

| Mistake | Fix |
|---------|-----|
| Vague request | Add Role + Format |
| Trusting facts blindly | Ask it to flag uncertainty; verify important things (or use grounding, Lesson 15) |
| One giant prompt for many tasks | Split into steps; iterate |
| Accepting the first draft | Refine with quick follow-ups |
| Not giving examples | Show 1–2 examples of what "good" looks like |

---

## ✅ Checkpoint

- [ ] You used few-shot examples.
- [ ] You used "think step by step" and saw better reasoning.
- [ ] You got Gemini to return strict JSON.
- [ ] You let Gemini ask *you* clarifying questions.

---

## 🎯 Homework

Rewrite the "annoying task" prompt from Lesson 1 using the **power prompt template**. Save the final version — a tool you'll reuse for months.

---

## 💡 Key takeaways

- Show examples, assign a role, and pin the output format.
- "Think step by step" boosts reasoning tasks.
- Let Gemini ask questions; treat first answers as drafts and iterate.
- For facts, combine good prompts with **grounding** (Lesson 15).

🌐 [Polski](../../pl/lessons/16-prompt-engineering.md) · [← Prev](15-grounding-google-search.md) · [Course home](../README.md) · [Next: Costs & safety →](17-costs-safety.md)
