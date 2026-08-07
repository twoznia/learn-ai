# Lesson 04 — Prompting Copilot Well

⏱️ **11 minutes** · Level: Beginner → Intermediate · Needs: VS Code + Copilot

🌐 [Polski](../../pl/lessons/04-dobre-promptowanie-copilota.md) · [← Prev](03-copilot-chat-basics.md) · [Course home](../README.md) · [Next: Edits & Agent mode →](05-edits-and-agent-mode.md)

---

## 🧠 Theory (4 min)

Copilot is only as good as the **context and instructions** you give it. The single biggest skill is **being specific** — about what you want, the constraints, and the shape of the answer.

Three levers control the quality of a suggestion:

1. **Context** — which files are open, what you selected, and what you reference. Copilot reads your open editor and project.
2. **Intent** — a clear comment or chat instruction ("write X that does Y, handling Z").
3. **Constraints** — language, style, libraries to use or avoid, edge cases.

A vague ask gets a generic guess; a precise ask gets usable code.

---

## 🛠️ Practice (7 min)

### Step 1 — Compare vague vs specific

In chat, ask the vague version:

```text
Write a function to process a file.
```

Then the specific version:

```text
Write a Python function read_csv_totals(path) that reads a CSV with columns
"region" and "amount", returns a dict of total amount per region, and raises
FileNotFoundError with a clear message if the file is missing.
```

Notice how much more useful the second answer is.

### Step 2 — Give context by opening the right files

Copilot uses your **open editor**. Before asking "add a function like the others," open the file that has those others — so Copilot matches their style.

### Step 3 — Guide completions with comments

In a file, a precise comment steers ghost text:

```python
# Convert a temperature in Celsius to Fahrenheit, rounded to 1 decimal place
def c_to_f(celsius):
```

### Step 4 — Ask for the shape you want

Tell Copilot the format:

```text
Refactor this into smaller functions. Show only the changed code, and add a
one-line comment above each new function.
```

### Step 5 — Iterate, don't restart

If the answer's close, refine in the same chat:

```text
Good, but use pathlib instead of os.path, and add a type hint on the return value.
```

### Step 6 — Provide examples

For tricky formats, show an example input and expected output. Copilot mirrors patterns well:

```text
Given input "2026-08-07" return "Aug 7, 2026". Write a function that does this.
```

---

## 🧩 Prompt quality checklist

| Include | Example |
|---------|---------|
| **What** | "a function that parses a CSV" |
| **Inputs/outputs** | "takes a path, returns a dict" |
| **Constraints** | "use pathlib; handle missing file" |
| **Style/shape** | "small functions, type hints" |
| **Example** | "input X → output Y" |

> ⚠️ Always **read** generated code before accepting it. Copilot can be confidently wrong — you're the reviewer.

---

## ✅ Checkpoint

- [ ] You saw the difference between a vague and a specific prompt.
- [ ] You opened relevant files to give Copilot context.
- [ ] You steered a completion with a precise comment.
- [ ] You iterated on an answer instead of starting over.

---

## 🎯 Homework

Take a real task you have (parsing, formatting, a small utility). Write it once with a vague prompt and once with a fully specified prompt including inputs, constraints, and an example. Compare the results, and note what made the difference.

---

## 💡 Key takeaways

- Quality comes from **context + clear intent + constraints** — be specific.
- Copilot reads your **open files and selection**; open the right ones before asking.
- **Iterate** in the same conversation, give **examples**, and always **review** the output.

🌐 [Polski](../../pl/lessons/04-dobre-promptowanie-copilota.md) · [← Prev](03-copilot-chat-basics.md) · [Course home](../README.md) · [Next: Edits & Agent mode →](05-edits-and-agent-mode.md)
