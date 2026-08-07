# Capstone — Build a Second Brain Agent

🌐 **Language:** **English** · [Polski](../pl/README.md) · [↩ Capstone landing](../README.md) · [↩ All courses](../../README.md)

The capstone project that ties the whole repo together. You'll **build a real AI agent** — a **Second Brain** that captures your notes, searches them, and answers questions grounded in your own knowledge — running on your **Claude Pro/Max subscription** (no paid API), entirely on your Windows PC.

Along the way you combine the big ideas from the other courses:

- **Prompt engineering** — the tool docstrings and Skill descriptions that make the agent reliable.
- **MCP with tools** — a custom Python server you build so the agent can read and write your notes.
- **Skills** — packaged know-how that shapes how the agent takes notes and reviews your week.
- **The GitHub workflow** — testing, a README, and shipping your project.

By the end you have a working agent you'll actually keep — and the skills to build more.

---

## What you'll build

```
You ⇄ Claude Code (agent) ── loads ──▶ Skills (note-style, weekly-review)
              │
              └── calls tools (MCP) ──▶ your Python server ──▶ notes/ (Markdown)
```

- **Agent:** Claude Code, on your subscription (no API key).
- **Tools:** `save_note`, `search_notes`, `get_note`, `list_notes` — a FastMCP server you write.
- **Skills:** note-style (how to capture) + weekly-review (a workflow).
- **Data:** plain Markdown notes on your disk — free, private, portable.

---

## Prerequisites

Helpful (not all required) before starting:

- A **Claude Pro or Max** subscription (the agent runs on it — no API key).
- **Node.js** and **Python** installed (the beginner course covers both).
- Basic comfort with **PowerShell** and a folder of files.
- Recommended background: the **[Prompt Engineering course](../../prompting/en/README.md)** and **Advanced Claude** Tracks D–E (Skills, MCP, Claude Code). This capstone puts them into practice.

---

## The build (8 lessons)

| # | Lesson | You'll… |
|---|--------|---------|
| 01 | [Overview & architecture](lessons/01-overview-and-architecture.md) | See how agent + tools + Skills + notes fit |
| 02 | [Set up your agent](lessons/02-set-up-your-agent.md) | Install Claude Code on your subscription |
| 03 | [Design your Second Brain](lessons/03-design-your-second-brain.md) | Decide the note model, tools, and Skills |
| 04 | [Build the MCP server](lessons/04-build-the-mcp-server.md) | Write the four note tools in Python |
| 05 | [Connect & test the tools](lessons/05-connect-and-test-tools.md) | Wire the server to the agent; call each tool |
| 06 | [Author your Skills](lessons/06-author-your-skills.md) | Write note-style + weekly-review Skills |
| 07 | [Run the agent](lessons/07-run-the-agent.md) | Capture, grounded recall, weekly review |
| 08 | [Test, harden & ship](lessons/08-test-harden-and-ship.md) | Make it safe, document it, put it on GitHub |

---

## Start here 👉 [Capstone 01 — Overview & architecture](lessons/01-overview-and-architecture.md)

*Educational material. Product names and CLI details change over time — the architecture (agent + MCP tools + Skills + local notes) still applies. Check the current Claude Code, MCP, and Skills docs when a command has moved.*
