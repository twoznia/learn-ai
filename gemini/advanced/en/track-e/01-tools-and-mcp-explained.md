# E1 — Tools & MCP Explained (with the Gemini CLI)

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: the Gemini CLI installed & signed in (see D5)

🌐 [Polski](../../pl/track-e/01-narzedzia-i-mcp.md) · [← Track index](../README.md) · [Next: GitHub with Gemini →](02-github-mcp.md)

---

## 🧠 Theory (6 min)

To do real work, Gemini needs to reach **outside tools and data**. There are three related ways it does that — know the difference:

| Way | What it is | Where |
|-----|-----------|-------|
| **Built-in tools** | Read/write files, run shell commands, search the web | The Gemini CLI, out of the box |
| **Extensions / connected apps** | Google Workspace, Maps, YouTube, etc. | The Gemini **app** (Track F) |
| **MCP servers** | An open standard for plugging in *any* external tool | The Gemini CLI (this track) |

**MCP (Model Context Protocol)** is the universal one. It's like a **standard plug**: instead of every tool inventing its own connection, MCP gives one shared socket. The **Gemini CLI is an MCP host** — it connects to MCP **servers** that expose **tools** (actions Gemini can take: create an issue, run a query, list resources).

```
Gemini CLI (host) ── connects to ──▶ MCP server ── exposes ──▶ tools
   you approve actions                (GitHub, Azure, your own)
```

Two ways a server connects:
- **Local (stdio)** — a small program launched on your PC (e.g. a filesystem server, or one you build).
- **Remote (URL)** — a hosted server you point the CLI at.

This track connects the big providers (GitHub, Atlassian, Azure) and one you build yourself — all through the Gemini CLI.

---

## 🛠️ Practice (8 min)

### Step 1 — See built-in tools

Start the Gemini CLI in a project and list its tools:

```text
/tools
```

You'll see the built-ins (file read/write, shell, web). These already make Gemini agentic — MCP *adds* to them.

### Step 2 — See MCP servers

```text
/mcp
```

This lists MCP servers connected to the CLI (empty is fine — we'll add some in the next lessons).

### Step 3 — Learn where MCP config lives

The CLI stores MCP servers in a **settings file** — user-level (`~/.gemini/settings.json`) or project-level (`.gemini/settings.json`). The shape you'll reuse:

```json
{
  "mcpServers": {
    "workspace": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "C:\\Users\\YourName\\mcp-workspace"]
    }
  }
}
```

- `command` — the program to launch (`npx`, `python`, `node`…).
- `args` — the package and any settings.

There's also a shortcut: `gemini mcp add <name> -- <command>` (you'll use it in E2).

### Step 4 — Understand a tool call

When Gemini uses an MCP tool: it **decides** a tool fits → **calls** it with structured inputs → the server **runs** it → **you approve** the result (the CLI asks before actions that change things). You stay in the loop.

### Step 5 — Map your needs

List systems you'd want Gemini to reach: code (GitHub?), tickets (Jira?), cloud (Azure?), your own files/scripts. Mark **read** vs **write** — you'll scope each server to the least it needs (E6).

---

## 🧩 Three ways to reach out

| | **Built-in tools** | **Extensions (app)** | **MCP (CLI)** |
|---|---|---|---|
| Where | Gemini CLI | Gemini app | Gemini CLI |
| Setup | None | Enable + sign in | Config / `gemini mcp add` |
| Best for | Files, shell, web | Workspace, Maps, YouTube | Any external tool, custom servers |

---

## ✅ Checkpoint

- [ ] You can name the three ways Gemini reaches tools (built-in, extensions, MCP).
- [ ] You listed built-in tools with `/tools` and MCP servers with `/mcp`.
- [ ] You know where MCP config lives (`settings.json`) and the server shape.
- [ ] You listed systems to connect, marked read vs write.

---

## 🎯 Homework

Sketch your ideal Gemini CLI setup: which MCP servers you'd add, scoped to what, read-only or not. Keep the sketch — the next lessons implement it provider by provider.

---

## 💡 Key takeaways

- Gemini reaches tools three ways: **built-in tools** and **MCP** (both in the CLI), and **extensions** (in the app).
- **MCP** is the universal plug; the **Gemini CLI is an MCP host** that connects to **servers** exposing **tools**.
- Servers are **local** (a program) or **remote** (a URL); you scope them and **approve** actions.

🌐 [Polski](../../pl/track-e/01-narzedzia-i-mcp.md) · [← Track index](../README.md) · [Next: GitHub with Gemini →](02-github-mcp.md)
