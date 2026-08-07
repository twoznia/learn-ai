# Capstone 03 — Design Your Second Brain

⏱️ **13 minutes** · Level: Capstone · Needs: your setup from Lesson 2

🌐 [Polski](../../pl/lessons/03-zaprojektuj-drugi-mozg.md) · [← Prev](02-set-up-your-agent.md) · [Capstone home](../README.md) · [Next: Build the MCP server →](04-build-the-mcp-server.md)

---

## 🧠 Theory (5 min)

Before writing code, **design**. A little planning here makes the build in Lesson 4 straightforward. We decide three things: the **note model**, the **tools**, and the **Skills**.

### The note model

Each note is one **Markdown file** in `notes\` with a small **frontmatter** header:

```markdown
---
title: Team sync — Q3 priorities
tags: [work, meeting]
created: 2026-08-07
---

We agreed to focus on onboarding. Owner: me. Follow up next week.
```

Plain files mean your Second Brain is **transparent, portable, and yours** — readable without any special app.

### The tools (what the MCP server exposes)

Four tools cover capture and recall. Notice each has a clear **name**, **inputs**, and **output** — and a precise **docstring**, because that's how the agent knows when to use it (straight from the Prompt Engineering course):

| Tool | Inputs | Returns | Job |
|------|--------|---------|-----|
| `save_note` | title, content, tags | the saved file path | Capture a new note |
| `search_notes` | query | matching notes (title + snippet) | Find relevant notes |
| `get_note` | title | the full note content | Read one note |
| `list_notes` | tag (optional) | note titles | Browse/overview |

### The Skills (know-how the agent auto-loads)

- **note-style** — how to write a good note: a clear title, the right tags, splitting big dumps into separate notes. Loads when the agent is *creating* notes.
- **weekly-review** — a workflow: gather the week's notes, find themes, surface open loops and to-dos, propose next actions. Loads when you ask for a review.

---

## 🛠️ Practice (7 min)

### Step 1 — Write your tool contracts

In a scratch file, write one precise sentence per tool describing exactly what it does and returns. Example:

```text
save_note(title, content, tags): Save a new note as a Markdown file with
frontmatter (title, tags, created date). Returns the file path. Use when the
user wants to capture information.
```

These sentences become your **docstrings** in Lesson 4 — and good docstrings are what make the agent call the right tool.

### Step 2 — Decide your tag taxonomy

Pick 5–8 starter tags that fit *your* life: e.g. `work`, `idea`, `person`, `decision`, `learning`, `todo`. A small, consistent set makes search and review far better than freeform tags.

### Step 3 — Draft your note-style rules

Write 4–5 rules for a good note (you'll paste these into the Skill in Lesson 6):

```text
- One idea per note; split big dumps.
- Title is a specific, searchable phrase.
- Tag with 1–3 tags from the taxonomy.
- End with an action line if there's a follow-up ("TODO: …").
```

### Step 4 — Sketch the weekly-review workflow

List the steps you'd want:

```text
1. List notes created this week.
2. Group them into themes.
3. Pull out all TODO lines.
4. Propose 3 priorities for next week.
```

### Step 5 — Confirm it's all free & local

Everything reads/writes local files, and the agent runs on your subscription. No external services, no API keys, no cost beyond your plan.

---

## 🧩 Your design at a glance

| Layer | Your decision |
|-------|---------------|
| Note model | Markdown + frontmatter (title, tags, created) |
| Tools | save / search / get / list notes |
| Tags | Your 5–8 starter taxonomy |
| note-style Skill | Your 4–5 note rules |
| weekly-review Skill | Your review steps |

---

## ✅ Checkpoint

- [ ] You wrote a one-sentence contract (future docstring) for each of the 4 tools.
- [ ] You chose a small tag taxonomy.
- [ ] You drafted your note-style rules.
- [ ] You sketched the weekly-review steps.

---

## 🎯 Homework

Finalize your design in a `DESIGN.md` file in your project. It's your blueprint for the next lessons — and a great example of the "design before you build" habit that makes AI-assisted projects go smoothly.

---

## 💡 Key takeaways

- Design first: a **note model**, four **tools**, and two **Skills**.
- Tool **docstrings** (from your one-sentence contracts) are how the agent picks the right tool — write them precisely.
- A small, consistent **tag taxonomy** and clear **note rules** make search and review far better.

🌐 [Polski](../../pl/lessons/03-zaprojektuj-drugi-mozg.md) · [← Prev](02-set-up-your-agent.md) · [Capstone home](../README.md) · [Next: Build the MCP server →](04-build-the-mcp-server.md)
