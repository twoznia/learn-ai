# G3 — Subagents

⏱️ **15 minutes** · Track: 🅶 Claude Code in Depth · Needs: Claude Code installed & logged in

🌐 [Polski](../../pl/track-g/03-podagenci.md) · [← Prev](02-slash-commands.md) · [Track index](../README.md) · [Next: Hooks →](04-hooks.md)

---

## 🧠 Theory (4 min)

A **subagent** is a specialized helper Claude Code can hand a focused job to — with its **own instructions, its own tools, and its own fresh context**. The main agent stays on the big picture and **delegates** the narrow task.

Why that's powerful:

- **Focus.** A "reviewer" subagent does only review; a "test-writer" does only tests. Clear role = better output.
- **Clean context.** Each subagent starts fresh, so a big investigation doesn't clog the main conversation.
- **Parallel-ish work.** The main agent can dispatch independent tasks to subagents instead of doing everything in one thread.

A subagent is defined by a small **Markdown file with a frontmatter header** — name, description, which tools it may use, optionally which model. Claude reads the description to decide when to use it.

---

## 🛠️ Practice (10 min)

### Step 1 — Create a subagent with `/agents`

In Claude Code:

```text
/agents
```

Follow the prompts to create a new subagent. It writes a Markdown file (in `.claude/agents/`) you can open and edit.

### Step 2 — Understand the file shape

A subagent file looks like this:

```markdown
---
name: reviewer
description: Reviews recent code changes for bugs, clarity, and risk. Use after edits.
tools: Read, Grep, Glob
model: sonnet
---

You are a careful code reviewer. Look only at what changed.
Report findings as a list, most severe first, each with a file:line and a one-line fix.
Do not edit files — only report.
```

- **name** — how it's referred to.
- **description** — *when* to use it (Claude reads this to delegate).
- **tools** — the narrow set it's allowed (least privilege!).
- **model** — optional; a lighter model for simple helpers saves usage.
- **body** — its system prompt / role.

### Step 3 — Let it be used automatically

Make a change, then ask the main agent to review — it should **delegate** to your reviewer:

```text
I just edited the login function. Review my recent changes.
```

Watch the main agent hand off to the `reviewer` subagent, which reports back. The main thread stays clean.

### Step 4 — Invoke one explicitly

You can also call a subagent by name:

```text
Use the reviewer subagent on the files I changed today.
```

### Step 5 — Build a small team

Add a couple more focused helpers:

- `tester` — "Write and run tests for the code I point to; report pass/fail." (tools include running tests)
- `explainer` — "Explain an unfamiliar file for a beginner." (read-only)

Give each the **narrowest tools** it needs. A read-only reviewer/explainer can't accidentally change anything.

### Step 6 — Know when NOT to delegate

Subagents add overhead (each re-establishes context). For a quick single-file edit, the main agent is faster. Delegate for **focused, independent, or repeatable** work — reviews, tests, investigations — not for trivial one-liners.

---

## 🧩 Designing good subagents

| Field | Get it right |
|-------|--------------|
| `name` | Short, role-like (`reviewer`, `tester`) |
| `description` | Say *when* to use it — Claude routes on this |
| `tools` | Narrowest set (read-only for review/explain) |
| `model` | Lighter model for simple helpers saves usage |
| body | One clear role, one clear output format |

> **Safety = least privilege.** A subagent can only use the tools you list. Keep reviewers/explainers read-only so delegation can't cause surprise edits.

---

## ✅ Checkpoint

- [ ] You created a subagent with `/agents` and read its Markdown file.
- [ ] You understand name / description / tools / model / body.
- [ ] The main agent **delegated** to your subagent automatically.
- [ ] You gave a subagent least-privilege tools.

---

## 🎯 Homework

Create a `reviewer` (read-only) and one more focused subagent for a task you repeat. Give each a precise description and the narrowest tools. Then run a real change and confirm the main agent delegates to the right one.

---

## 💡 Key takeaways

- **Subagents** are specialized helpers with their **own instructions, tools, and fresh context** — the main agent delegates focused work.
- Defined by a **Markdown file with frontmatter** (`.claude/agents/`): name, description, tools, model, body — manage with `/agents`.
- **Least privilege** and **clear descriptions** make delegation safe and accurate; don't delegate trivial one-liners.

🌐 [Polski](../../pl/track-g/03-podagenci.md) · [← Prev](02-slash-commands.md) · [Track index](../README.md) · [Next: Hooks →](04-hooks.md)
