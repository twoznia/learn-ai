# Lesson 03 — Prompting Basics

⏱️ **10 minutes** · Level: Beginner · Needs: your claude.ai account

[← Prev](02-first-chat.md) · [Course home](../README.md) · [Next: Files and images →](04-files-and-images.md)

---

## 🧠 Theory (4 min)

A **prompt** is just your instructions to Claude. The difference between a mediocre answer and a great one is almost always the prompt.

### The 4 ingredients of a great prompt (**R-C-T-F**)

| Ingredient | Question it answers | Example |
|-----------|---------------------|---------|
| **R — Role** | Who should Claude act as? | "You are a friendly IT helpdesk agent." |
| **C — Context** | What's the situation/background? | "My mom, 70, can't open her email." |
| **T — Task** | What exactly do you want? | "Write step-by-step instructions." |
| **F — Format** | How should the answer look? | "Numbered list, max 6 steps, no jargon." |

You don't always need all four, but adding **Format** alone dramatically improves results.

### Weak vs. strong prompt

❌ **Weak:**
```text
help with email
```

✅ **Strong:**
```text
You are a friendly IT helper. My mom (age 70) uses a Windows laptop and can't
open her email. Write clear step-by-step instructions to open Outlook on the web.
Format: a numbered list, maximum 6 steps, no technical jargon.
```

Same topic, wildly different quality.

---

## 🛠️ Practice (5 min)

### Drill 1 — Add a format and watch it change

First send:
```text
Give me ideas for dinner.
```

Then, in the same chat, send:
```text
Now redo that as a table with 3 columns: Meal, Main ingredient, Time to cook.
Only include meals under 30 minutes.
```

See how "Format" reshaped everything.

### Drill 2 — Use a Role

```text
You are a patient math tutor for a 10-year-old. Explain what a fraction is
using a pizza example. Keep it under 100 words and end with one practice question.
```

### Drill 3 — Give Claude an "out"

Add this line to reduce made-up answers:
```text
If you are not sure about any fact, say "I'm not certain" instead of guessing.
```

Try it:
```text
What was the exact population of my town last Tuesday? If you are not sure,
say "I'm not certain" instead of guessing.
```

A good answer here is Claude admitting it can't know that. That's the behavior you want.

---

## 🧰 5 reusable prompt patterns (copy these)

**1. The Summarizer**
```text
Summarize the text below in 5 bullet points a busy person could read in 20 seconds.
Then add one line: "Bottom line: ...".

TEXT:
<paste text here>
```

**2. The Explainer**
```text
Explain <topic> to me like I'm a smart beginner. Use one everyday analogy,
avoid jargon, and keep it under 150 words.
```

**3. The Rewriter**
```text
Rewrite the message below to sound polite, clear, and professional.
Keep it under 4 sentences.

MESSAGE:
<paste message>
```

**4. The Brainstormer**
```text
Give me 10 ideas for <goal>. Make them varied: some safe, some bold.
One line each.
```

**5. The Step-by-Step**
```text
Give me a step-by-step plan to <task>. Number each step, keep steps short,
and tell me what to do first today.
```

---

## ✅ Checkpoint

- [ ] You can name the **R-C-T-F** ingredients.
- [ ] You saw how adding **Format** changed an answer.
- [ ] You have 5 patterns saved somewhere you can reuse.

---

## 🎯 Homework

Take your "annoying task" and write **one strong prompt** for it using all four R-C-T-F ingredients. Save it in a text file called `my-prompts.txt`. You're building a personal prompt library.

---

## 💡 Key takeaways

- Great prompts = **Role + Context + Task + Format**.
- Adding a **Format** instruction is the easiest big win.
- Give Claude permission to say "I'm not sure" to reduce hallucinations.

[← Prev](02-first-chat.md) · [Course home](../README.md) · [Next: Files and images →](04-files-and-images.md)
