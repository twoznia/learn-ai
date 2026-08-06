# D4 — Skills & Connectors (MCP on Your Subscription)

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Pro/Max Claude.ai account

🌐 [Polski](../../pl/track-d/04-skille-i-konektory.md) · [← Prev](03-save-tokens-and-manage-limits.md) · [Track index](../README.md) · [Next: Agents & Claude Code →](05-agents-and-claude-code.md)

---

## 🧠 Theory (5 min)

Two features turn Claude from "a chat box" into something that plugs into your real work — and both are **included in your subscription**, no API key:

- **Skills** — packaged expertise Claude loads **when a task needs it**. For example, Skills for building **Excel** spreadsheets, **PowerPoint** decks, **Word** docs, and **PDFs**. You don't call them manually; Claude picks up the right Skill for the job.
- **Connectors (MCP)** — links from Claude to **other tools and data**: your Google Drive, a calendar, a knowledge base, or a developer server. MCP (Model Context Protocol) is the open standard behind them. In Track A you added MCP to **Claude Desktop** by editing a config file; here you use the **built-in connectors** in the Claude apps — a few clicks, no JSON.

Think of it this way: **Skills** give Claude know-how; **connectors** give Claude reach.

---

## 🛠️ Practice (9 min)

### Part 1 — Skills

1. Start a task that produces a real document, e.g.:

```text
Create a 3-slide PowerPoint summarizing these notes: <paste a few bullet points>.
Give me the .pptx file to download.
```

2. Claude recognizes the task and uses the **PowerPoint Skill** to build a real `.pptx` you can download — not just text describing slides.

3. Try another format to feel the range:

```text
Turn this data into a clean Excel file with a total row and a simple chart:
<paste a small table>.
```

You describe the outcome; the matching Skill produces the file.

> Skills load **automatically** based on the task. You don't switch them on per message — just ask for the deliverable and Claude reaches for the right one.

### Part 2 — Connectors (MCP)

1. Open **Settings → Connectors** (naming may vary by app/plan). You'll see available connectors you can enable.
2. Enable one you actually use — e.g. **Google Drive** — and complete the sign-in it prompts for. This authorizes Claude to access **only** what you approve.
3. Back in a chat, use it:

```text
Find my "Q3 plan" document in Drive and summarize its top 3 priorities.
```

Claude reaches through the connector, pulls the doc, and answers — no copy-paste.

### Part 3 — Combine a Skill and a connector

The payoff is composing them:

```text
Pull the latest figures from my "Sales" sheet in Drive, then build a one-page
PDF summary with a short chart. Give me the file.
```

Connector fetches the data; Skill builds the deliverable. That's a real workflow, all inside your subscription.

---

## 🔒 Connector safety

| Habit | Why |
|-------|-----|
| Enable only connectors you use | Fewer places Claude can reach |
| Review the access it asks for at sign-in | You approve the scope |
| Prefer read-only where offered | Lower blast radius |
| Disconnect connectors you've stopped using | Clean, minimal setup |
| You stay the reviewer of what it does | Human in the loop |

---

## 🧩 Skills vs connectors

| | **Skills** | **Connectors (MCP)** |
|---|---|---|
| Give Claude… | Know-how (build a deck, a sheet, a PDF) | Reach (your Drive, calendar, tools) |
| You turn them on by… | Nothing — auto-loaded per task | Enabling + signing in once |
| Example | "Make me a PowerPoint" | "Find my doc in Drive" |

---

## ✅ Checkpoint

- [ ] You had a Skill produce a real downloadable file (Excel / PPTX / Word / PDF).
- [ ] You enabled one connector and used it in a chat.
- [ ] You combined a connector + a Skill in a single task.

---

## 🎯 Homework

Pick one recurring deliverable you make by hand (a weekly deck, a report, a tracker). Enable the connector that holds its source data, then ask Claude to fetch the data and produce the file. Save the prompt for reuse.

---

## 💡 Key takeaways

- **Skills** give Claude know-how and load **automatically** for the task — real Excel/PPTX/Word/PDF files, no API key.
- **Connectors (MCP)** give Claude reach into your tools; enable only what you use and review the access.
- **Compose** them — connector fetches, Skill builds — for full workflows inside your subscription.

🌐 [Polski](../../pl/track-d/04-skille-i-konektory.md) · [← Prev](03-save-tokens-and-manage-limits.md) · [Track index](../README.md) · [Next: Agents & Claude Code →](05-agents-and-claude-code.md)
