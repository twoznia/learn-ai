# Capstone 08 — Test, Harden & Ship

⏱️ **16 minutes** · Level: Capstone · Needs: a working Second Brain agent (Lesson 7)

🌐 [Polski](../../pl/lessons/08-testuj-utwardz-i-wydaj.md) · [← Prev](07-run-the-agent.md) · [Capstone home](../README.md) · [↩ All courses](../../../README.md)

---

## 🧠 Theory (3 min)

You built a working agent. To make it something you **trust and keep**, finish like an engineer: **test** it, **harden** it against mistakes, and **ship** it to GitHub with docs — so it survives, improves, and could even help others.

Three fronts:

- **Test** — does each tool behave on edge cases? Does recall stay grounded?
- **Harden** — safety (scope, approvals, secrets) and reliability (better docstrings/descriptions).
- **Ship** — a README, a git history, and a GitHub repo; then extend it.

---

## 🛠️ Practice (12 min)

### Step 1 — Test the tools on edge cases

Ask the agent to probe its own tools:

```text
Test my tools: save a note with an empty title, search for something that
doesn't exist, and get a note that isn't there. Report what happened.
```

Fix anything ugly (e.g. an unhelpful message) in `brain_server.py`. This is the eval mindset from the Prompt Engineering course, applied to your tools.

### Step 2 — Harden the safety boundary

Confirm the guardrails hold:
- **Scope:** the server only touches `notes\` (verify in the code).
- **Approvals:** the agent still asks before writing — keep that on.
- **Secrets:** don't put passwords or private data in notes you'll push publicly. Add a `.gitignore` if your notes are private:

```powershell
notepad .gitignore
```

```text
# Keep private notes out of git (delete this line to version them)
notes/
.claude/settings.local.json
```

> Decide deliberately: **commit your notes** (versioned, backed up) *or* **gitignore them** (private). Either is fine — just choose on purpose.

### Step 3 — Improve reliability where it slipped

If during Lesson 7 the agent ever chose the wrong tool or a Skill didn't fire, tighten the **docstring** or the Skill **description** now. Precise "use when…" text is your reliability dial.

### Step 4 — Write a README

Ask the agent (this is the Copilot/README skill in action):

```text
Write a README.md for this project: what it is, the architecture (agent + MCP
tools + Skills + notes), how to set it up on Windows, and how to use it.
Verify the setup steps against the actual files.
```

Review it, run the steps to confirm they're accurate, and save it.

### Step 5 — Ship it to GitHub

```powershell
git add -A
git commit -m "Second Brain agent: MCP tools + Skills + docs"
```

Then publish (VS Code's **Publish to GitHub**, or create a repo on github.com and push). Decide **private or public** — private if your notes are committed.

### Step 6 — Extend it (pick one)

Your Second Brain is a platform now. Add one thing:

- **A new tool** — `delete_note`, `edit_note`, or `notes_by_date(range)`.
- **A new Skill** — a "daily capture" ritual, or a "link saver" style.
- **Automation** — schedule the weekly review with Windows Task Scheduler (Advanced course Track C) using `claude` in headless mode.
- **More reach** — add a second MCP server (e.g. a calendar) and let the review include it.

---

## 🧩 Ship checklist

| Front | Done when |
|-------|-----------|
| **Tested** | Edge cases handled; recall stays grounded |
| **Scoped** | Server only touches `notes\`; approvals on |
| **Private** | Secrets kept out; notes commit/ignore chosen |
| **Documented** | Accurate README (verified steps) |
| **Shipped** | Committed and pushed to GitHub |
| **Extended** | One new tool / Skill / automation |

---

## ✅ Checkpoint

- [ ] You tested the tools on edge cases and fixed rough spots.
- [ ] Safety is confirmed: scoped server, approvals on, secrets handled.
- [ ] You wrote and verified a README.
- [ ] The project is on GitHub, and you added one extension.

---

## 🎯 Homework

Ship your Second Brain to GitHub with a solid README, then use it daily for a week. Each time it does something awkward, fix the docstring/Skill/tool that caused it. That real-use → refine loop is exactly how professionals harden an AI product.

---

## 💡 Key takeaways

- Finish like an engineer: **test** edge cases, **harden** (scope, approvals, secrets, tighter docstrings/descriptions), and **ship** with docs.
- Choose deliberately whether to **commit or gitignore** your notes, and keep secrets out of a public repo.
- Your Second Brain is a **platform** — extend it with new tools, Skills, or scheduled automation. You've built a real agent. 🎉

🌐 [Polski](../../pl/lessons/08-testuj-utwardz-i-wydaj.md) · [← Prev](07-run-the-agent.md) · [Capstone home](../README.md) · [↩ All courses](../../../README.md)
