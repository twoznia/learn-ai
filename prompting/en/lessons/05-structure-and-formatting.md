# Lesson 05 — Structure & Formatting Your Prompt

⏱️ **11 minutes** · Level: Intermediate · Needs: any AI chat

🌐 [Polski](../../pl/lessons/05-struktura-i-formatowanie.md) · [← Prev](04-context-and-context-window.md) · [Course home](../README.md) · [Next: Few-shot prompting →](06-few-shot-prompting.md)

---

## 🧠 Theory (4 min)

A wall of text confuses both people and models. **Structure** makes your intent unambiguous — and it lets you control the **shape of the output**.

Two structuring moves do most of the work:

1. **Separate the parts of your prompt.** Use headings, numbered steps, or **delimiters** (like `"""` or `---` or XML-style tags) to clearly divide *instructions* from *the content to work on*. This prevents the model from confusing your data for your commands.
2. **Specify the output format.** Ask for exactly the shape you want — a table, bullets, numbered steps, JSON, a specific template. If you don't specify, you get the model's default.

Structure in → structure out. A well-organized prompt is easier for the model to follow *and* easier for you to reuse.

---

## 🛠️ Practice (6 min)

### Step 1 — Delimit instructions from content

```text
Summarize the text between the triple quotes in 3 bullets.

"""
[paste the text here]
"""
```

Now the model knows the quoted block is data, not instructions.

### Step 2 — Use tags for multiple inputs

When you have several pieces, label them:

```text
<article>…</article>
<audience>busy nurses</audience>

Task: rewrite <article> for <audience> at a 9th-grade reading level.
```

### Step 3 — Specify the exact output shape

```text
Return a markdown table with columns: Option | Pros | Cons | Best for.
```

Or a strict template:

```text
For each item, output exactly:
- Name:
- One-line summary:
- Risk (low/med/high):
```

### Step 4 — Number multi-step instructions

```text
Do these in order:
1. List the key claims.
2. Rate each as supported / unsupported by the text.
3. Give one overall verdict.
```

### Step 5 — Ask for *only* the output

To avoid preamble:

```text
Return only the table, no explanation before or after.
```

---

## 🧩 Structuring tools

| Tool | Use for |
|------|---------|
| `"""` / `---` / tags | Separating instructions from content |
| Numbered steps | Ordered, multi-part tasks |
| "Return a table/JSON with…" | Controlling output shape |
| A fixed template | Consistent, reusable output |
| "Only output X" | Removing preamble |

---

## ✅ Checkpoint

- [ ] You used delimiters to separate instructions from content.
- [ ] You labeled multiple inputs with tags.
- [ ] You specified an exact output format (table/template/JSON).
- [ ] You got clean output with no unwanted preamble.

---

## 🎯 Homework

Take a prompt that mixes instructions and pasted content. Rewrite it with clear delimiters and a specified output format (a table or template). Notice how much more consistent the result is — and how reusable the prompt becomes.

---

## 💡 Key takeaways

- **Delimiters/tags** separate your instructions from the content, preventing confusion.
- **Specify the output format** (table, template, JSON, steps) — otherwise you get the default.
- Structured input yields **structured, reusable** output.

🌐 [Polski](../../pl/lessons/05-struktura-i-formatowanie.md) · [← Prev](04-context-and-context-window.md) · [Course home](../README.md) · [Next: Few-shot prompting →](06-few-shot-prompting.md)
