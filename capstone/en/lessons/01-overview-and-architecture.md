# Capstone 01 — Overview & Architecture

⏱️ **12 minutes** · Level: Capstone · Needs: curiosity (we set up tools next lesson)

🌐 [Polski](../../pl/lessons/01-przeglad-i-architektura.md) · [Capstone home](../README.md) · [Next: Set up your agent →](02-set-up-your-agent.md)

---

## 🧠 What you'll build

A **Second Brain agent**: an AI agent that captures your notes, searches them, and answers questions **grounded in your own knowledge** — running on your **Claude Pro/Max subscription** (no paid API), entirely on your Windows PC.

By the end you'll have a real, keepable tool *and* you'll have combined the three big ideas from across these courses:

- **Prompt engineering** — writing the tool descriptions and Skill instructions that make the agent reliable.
- **MCP with tools** — a custom server you build that lets the agent read and write your notes.
- **Skills** — packaged know-how that shapes *how* the agent takes notes and reviews your week.

This is the payoff project. It's guided, but it's yours to keep and extend.

---

## 🧩 The architecture

Four parts work together:

```
        You (chat)
           │
           ▼
   ┌──────────────────┐     loads     ┌───────────────┐
   │   Claude Code    │◀─────────────▶│    Skills     │
   │   (the AGENT)    │   know-how    │ note-style,   │
   │  on Claude Pro   │               │ weekly-review │
   └───────┬──────────┘               └───────────────┘
           │ calls tools (MCP)
           ▼
   ┌──────────────────┐    reads/writes   ┌───────────────┐
   │   MCP server     │──────────────────▶│  notes/ folder │
   │ (your Python)    │                   │  (Markdown)    │
   │ save/search/get  │                   │  your Second   │
   │ /list notes      │                   │  Brain data    │
   └──────────────────┘                   └───────────────┘
```

- **The agent** is **Claude Code** — it plans, decides which tool to call, and iterates, with you approving actions. It runs on your **subscription**, no API key.
- **The MCP server** is a small **Python** program *you* write (using FastMCP, like Advanced Claude Track E). It exposes **tools** — `save_note`, `search_notes`, `get_note`, `list_notes` — that operate on a local `notes/` folder.
- **Skills** are folders with instructions the agent **auto-loads** when relevant: a **note-style** Skill (how to format and tag notes) and a **weekly-review** Skill (a workflow).
- **Your notes** are plain **Markdown files** on disk — transparent, portable, and free.

---

## 🗺️ The plan (8 lessons)

| # | Lesson | You'll…|
|---|--------|--------|
| 01 | Overview & architecture | Understand the pieces (this lesson) |
| 02 | Set up your agent | Install Claude Code on your subscription + Python |
| 03 | Design your Second Brain | Decide the note model, tools, and Skills |
| 04 | Build the MCP server | Write the 4 note tools in Python |
| 05 | Connect & test the tools | Wire the server to the agent; call each tool |
| 06 | Author your Skills | Write note-style + weekly-review Skills |
| 07 | Run the agent | Capture, search, and answer over your notes |
| 08 | Test, harden & ship | Make it safe, put it on GitHub, extend it |

---

## ✅ Checkpoint

- [ ] You can name the four parts: agent, MCP server (tools), Skills, notes.
- [ ] You understand the agent runs on your **subscription** (no API key).
- [ ] You know the tools operate on **local Markdown files**.
- [ ] You can explain the difference between a **tool** (an action) and a **Skill** (know-how).

---

## 🎯 Homework

Sketch *your* Second Brain on paper. What do you want to capture (ideas, meeting notes, links, decisions)? What questions would you ask it later? Keep the sketch — you'll turn it into a real design in Lesson 3.

---

## 💡 Key takeaways

- You're building a **Second Brain agent**: Claude Code + a custom **MCP server (tools)** + **Skills** + local Markdown notes.
- It runs on your **Claude Pro/Max subscription** — no paid API, all on your PC.
- **Tools** give the agent *reach* (read/write notes); **Skills** give it *know-how* (how to take notes, how to review).

🌐 [Polski](../../pl/lessons/01-przeglad-i-architektura.md) · [Capstone home](../README.md) · [Next: Set up your agent →](02-set-up-your-agent.md)
