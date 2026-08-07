# Lesson 10 — Controlling the Output Precisely

⏱️ **11 minutes** · Level: Intermediate → Advanced · Needs: any AI chat

🌐 [Polski](../../pl/lessons/10-kontrola-wyniku.md) · [← Prev](09-decomposition-and-chaining.md) · [Course home](../README.md) · [Next: Reducing hallucinations →](11-reducing-hallucinations.md)

---

## 🧠 Theory (4 min)

You can control not just *what* the model says but *exactly how* it's shaped — length, tone, structure, and even machine-readable formats. This matters when the output feeds a document, a spreadsheet, or another program.

Levers you control:

- **Length** — "in one sentence," "exactly 5 bullets," "under 100 words."
- **Tone & register** — "formal," "for a 10-year-old," "no contractions."
- **Structure** — a table, a template, numbered steps (Lesson 5).
- **Machine formats** — **JSON**, CSV, or a strict schema when a program will read it.

The rule: **state the constraint explicitly, and make it checkable.** "Short" is vague; "under 50 words" is enforceable.

---

## 🛠️ Practice (6 min)

### Step 1 — Pin the length

```text
Summarize this in exactly 3 bullets, each under 12 words.
```

### Step 2 — Control tone precisely

```text
Rewrite for a general audience: no jargon, friendly but not casual, and no
exclamation marks.
```

### Step 3 — Ask for JSON (for programs)

```text
Return ONLY valid JSON, no prose, in this schema:
{"title": string, "tags": string[], "priority": "low"|"medium"|"high"}
```

Asking for "only JSON" avoids the model wrapping it in chatter.

### Step 4 — Give a strict template

```text
For each book, output exactly:
Title | Author | One-line hook | Age range
```

### Step 5 — Constrain by example (few-shot)

Combine with Lesson 6 when format must be perfect:

```text
Format like: "2026-03-01 — Standup — 15m". Now format these entries: …
```

### Step 6 — Verify the constraint held

Check the output against your rule (word count, valid JSON). If it drifted, restate the constraint more firmly: "You exceeded 50 words. Redo in under 50."

---

## 🧩 Output controls

| Want | Say |
|------|-----|
| A length | "under 100 words" / "exactly 5 bullets" |
| A tone | "formal, third person, no contractions" |
| A table | "markdown table with columns …" |
| Machine-readable | "return ONLY valid JSON in this schema" |
| No preamble | "output only the result" |

> ⚠️ Even with a strict schema, **validate** machine output before a program consumes it — models can occasionally break format.

---

## ✅ Checkpoint

- [ ] You pinned an exact length and it held.
- [ ] You controlled tone with specific rules.
- [ ] You got clean JSON with "only JSON" instruction.
- [ ] You restated a constraint when the output drifted.

---

## 🎯 Homework

Take a task whose output you'll paste somewhere specific (a doc, a sheet, code). Write a prompt that nails the exact format — length, structure, or JSON schema — and validate the result. Save the prompt as a reusable template.

---

## 💡 Key takeaways

- Control **length, tone, structure, and machine formats** by stating each constraint **explicitly and checkably**.
- Ask for **"only JSON"** (or a strict template) when a program or document will consume the output.
- Always **validate** that the constraint held — restate it firmly if the output drifts.

🌐 [Polski](../../pl/lessons/10-kontrola-wyniku.md) · [← Prev](09-decomposition-and-chaining.md) · [Course home](../README.md) · [Next: Reducing hallucinations →](11-reducing-hallucinations.md)
