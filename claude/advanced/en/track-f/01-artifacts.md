# F1 — Artifacts: Build & Publish

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: a Claude.ai account (Pro recommended)

🌐 [Polski](../../pl/track-f/01-artefakty.md) · [← Track index](../README.md) · [Next: The analysis tool →](02-analysis-tool.md)

---

## 🧠 Theory (4 min)

Most of the course treats Claude as a text box. **Artifacts** change that: when you ask for something substantial — a document, a chart, a small app, a diagram — Claude opens a **side panel** and builds it there as a **live, editable thing** you can preview, refine, and even **publish** as a link.

What can be an artifact:

- **Documents** — reports, guides, long-form writing you'll keep editing.
- **Code** — a script, a function, a whole small file.
- **Interactive web apps** — a calculator, a quiz, a tool, a mini-game (Claude writes real HTML/JS/React and runs it in the panel).
- **Visuals** — SVG diagrams, flowcharts, charts.

The point: instead of scrolling a chat for the "final version," you **iterate on a living object** and end with something you can use or share.

---

## 🛠️ Practice (10 min)

### Step 1 — Make your first artifact

In a normal chat, ask for something substantial:

```text
Build me a small interactive "tip calculator" web page: bill amount, tip %,
number of people, and it shows tip and total per person. Make it clean.
```

Claude opens the **Artifacts panel** and builds a working page you can **actually use** right there — type numbers and watch it compute.

### Step 2 — Iterate on the living object

Don't start over — refine in place:

```text
Add a dark mode toggle and round the per-person total to the nearest cent.
```

Claude edits the **same** artifact. Notice you're shaping one object, not collecting drafts down a chat.

### Step 3 — Try a document artifact

```text
Write a one-page onboarding guide for new teammates using our tools.
Put it in an artifact so I can keep editing it.
```

Now you have a document you can revise with follow-up requests ("make the intro shorter," "add a checklist at the end").

### Step 4 — Try a visual

```text
Create an SVG flowchart of a simple support-ticket process:
new → triaged → in progress → resolved → closed. Label each arrow.
```

A real diagram appears in the panel — editable by asking for changes.

### Step 5 — Publish or share it

When an artifact is ready, use the artifact's menu to **publish/share** it. You get a link you can send to someone — they see the rendered result, not your chat.

> ⚠️ **Before you share:** you're making it viewable by anyone with the link. Don't publish anything with private data, credentials, or content that impersonates a real person or organization. Review it first.

### Step 6 — Know the good use cases

Reach for artifacts when the output is something you'll **keep, edit, or hand to someone**: a tool, a doc, a chart, a page. For a quick one-off answer, plain chat is fine.

---

## 🧩 When to use an artifact

| Want… | Artifact? |
|-------|-----------|
| A working tool/app you'll use | ✅ Yes |
| A document you'll keep editing | ✅ Yes |
| A diagram or chart | ✅ Yes |
| A quick factual answer | ❌ Plain chat |
| Something to share as a link | ✅ Yes (review first) |

---

## ✅ Checkpoint

- [ ] You built an interactive artifact and actually used it in the panel.
- [ ] You iterated on the **same** artifact instead of starting over.
- [ ] You made a document or a visual artifact too.
- [ ] You published/shared one and understand the privacy note.

---

## 🎯 Homework

Build one artifact you'd genuinely use — a personal calculator, a checklist doc, or a small tool. Iterate it three times with follow-up requests, then publish it and send yourself the link.

---

## 💡 Key takeaways

- **Artifacts** turn Claude's output into a **live, editable object** — apps, docs, diagrams — in a side panel.
- **Iterate in place** with follow-up requests instead of collecting drafts down the chat.
- You can **publish/share** an artifact as a link — review for privacy before you do.

🌐 [Polski](../../pl/track-f/01-artefakty.md) · [← Track index](../README.md) · [Next: The analysis tool →](02-analysis-tool.md)
