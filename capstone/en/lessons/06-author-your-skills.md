# Capstone 06 — Author Your Skills

⏱️ **15 minutes** · Level: Capstone · Needs: a working agent + tools (Lesson 5)

🌐 [Polski](../../pl/lessons/06-napisz-swoje-skille.md) · [← Prev](05-connect-and-test-tools.md) · [Capstone home](../README.md) · [Next: Run the agent →](07-run-the-agent.md)

---

## 🧠 Theory (4 min)

Tools give the agent **reach**; **Skills** give it **know-how**. A Skill is a small folder with a `SKILL.md` file: some **instructions**, plus a **name** and **description** in the header. The agent reads the description and **auto-loads the Skill when it's relevant** — you don't invoke it manually.

We'll author two:

- **note-style** — your rules for a good note (loads when the agent creates/edits notes).
- **weekly-review** — your review workflow (loads when you ask for a review).

In Claude Code, project Skills live in a `.claude\skills\` folder inside your project, so they ship with your repo.

> The exact Skills location and file format evolve, and Claude Desktop/apps manage Skills through their own settings — check the current docs. The concept is stable: **a named, described set of instructions the agent loads when it fits the task.**

---

## 🛠️ Practice (10 min)

### Step 1 — Create the Skills folder

In your project:

```powershell
mkdir .claude\skills\note-style
mkdir .claude\skills\weekly-review
```

### Step 2 — Write the note-style Skill

```powershell
notepad .claude\skills\note-style\SKILL.md
```

```markdown
---
name: note-style
description: Rules for writing and tagging notes in this Second Brain. Use
  whenever creating, editing, or saving a note with save_note.
---

# Note style

When saving a note, follow these rules:

- **One idea per note.** If the user dumps several topics, split them into
  separate notes with `save_note`.
- **Title** is a specific, searchable phrase — not "Notes" or "Stuff".
- **Tags**: choose 1–3 from this taxonomy: `work`, `idea`, `person`,
  `decision`, `learning`, `todo`. Add a new tag only if none fit.
- **Action line**: if there's a follow-up, end the note with `TODO: …`.
- Keep the user's own words; tidy lightly, don't rewrite their meaning.

After saving, confirm the title and tags you used.
```

### Step 3 — Write the weekly-review Skill

```powershell
notepad .claude\skills\weekly-review\SKILL.md
```

```markdown
---
name: weekly-review
description: A workflow to review the week's notes. Use when the user asks for
  a weekly review, a recap, or "what did I capture this week?".
---

# Weekly review

Run these steps in order:

1. Use `list_notes` (and `search_notes` if needed) to gather notes, focusing on
   recent ones.
2. Group them into 2–4 themes. Name each theme.
3. Collect every `TODO:` line into one "Open loops" list.
4. Propose the **3 most important priorities** for next week, each one line.
5. Offer to save the summary as a note titled "Weekly review — <date>"
   (tags: `review`) — but ask first.

Keep it concise and grounded ONLY in the actual notes. If something is unclear
or missing, say so rather than inventing it.
```

### Step 4 — Confirm the Skills are seen

Restart Claude Code in the project. Ask something that should trigger note-style:

```text
Save a note: "met Alex about the new onboarding flow, they'll send the draft
Friday, I need to review it."
```

A good result: the agent titles it well, tags it (`work`, `person`, maybe `todo`), and adds a `TODO:` line — because the **note-style Skill loaded**.

### Step 5 — Notice the description does the triggering

The Skill's **description** is what makes the agent load it at the right moment — just like a tool's docstring. Vague description → it won't trigger. Precise "use when…" → it fires reliably. (Prompt Engineering, applied again.)

---

## 🧩 Tools vs Skills (recap)

| | Tools (Lesson 4) | Skills (this lesson) |
|--|------------------|----------------------|
| Give the agent | Reach (do things) | Know-how (how to do them well) |
| Defined by | `@mcp.tool()` + docstring | `SKILL.md` + description |
| Triggered by | The agent choosing to act | The description matching the task |
| Example | `save_note(...)` | "note-style" formatting rules |

---

## ✅ Checkpoint

- [ ] `.claude\skills\note-style\SKILL.md` and `weekly-review\SKILL.md` exist.
- [ ] Each has a **name** and a precise **description** ("use when…").
- [ ] Saving a note now follows your note-style rules automatically.
- [ ] You can explain how a Skill's **description** triggers auto-loading.

---

## 🎯 Homework

Refine your note-style Skill after using it on 3–4 real notes: are the titles searchable? Are the tags consistent? Tighten the rules (and the description) until the agent's notes come out the way *you* want by default.

---

## 💡 Key takeaways

- **Skills** package know-how in a `SKILL.md`; the agent **auto-loads** them when the **description** matches the task.
- You authored **note-style** (how to capture) and **weekly-review** (a workflow) — both shipping in `.claude\skills\`.
- A Skill's **description** is its trigger — write it as precisely as a tool docstring.

🌐 [Polski](../../pl/lessons/06-napisz-swoje-skille.md) · [← Prev](05-connect-and-test-tools.md) · [Capstone home](../README.md) · [Next: Run the agent →](07-run-the-agent.md)
