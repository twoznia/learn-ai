# E1 — MCP Explained Properly

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: Claude Desktop (from the beginner course)

🌐 [Polski](../../pl/track-e/01-czym-jest-mcp.md) · [← Track index](../README.md) · [Next: GitHub MCP →](02-github-mcp.md)

---

## 🧠 Theory (6 min)

**MCP (Model Context Protocol)** is an open standard that lets Claude talk to **outside tools and data** in a consistent way. Think of it as a **universal plug**: instead of every app inventing its own way to connect AI, MCP gives one shared socket.

Three roles:

| Role | What it is | Examples |
|------|-----------|----------|
| **Host / Client** | The app you use, which *connects to* servers | Claude Desktop, Claude Code, the Claude web app |
| **Server** | A small program that *exposes* capabilities | GitHub, Atlassian, Azure, a filesystem server, one you build |
| **You** | Approve access and review what happens | 🧑 |

A server can expose three kinds of things:

- **Tools** — actions Claude can take (create an issue, run a query, list files).
- **Resources** — data Claude can read (a file, a page, a record).
- **Prompts** — ready-made prompt templates the server offers.

For most work, **tools** are the star: they're how Claude *does* things in your systems.

### Two ways a server connects

```
LOCAL (stdio)                         REMOTE (connector, URL + OAuth)
Claude Desktop ──launches──▶ program   Claude ──HTTPS──▶ hosted server
on your PC, via config file            you sign in once, no install
e.g. filesystem, your own server       e.g. GitHub, Atlassian
```

- **Local servers** run *on your machine*. You register them in a config file; Claude Desktop launches them. Great for filesystem access and servers you build.
- **Remote servers (connectors)** are *hosted*. You enable them in the app and sign in with OAuth — a few clicks, nothing to install. Great for big services like GitHub and Atlassian.

This track uses **both**: connectors for the big providers (E2–E4), and a local server you build yourself (E5).

---

## 🛠️ Practice (8 min)

### Step 1 — See where local servers live

Open the Claude Desktop config (create it if missing):

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Every local server is an entry under `mcpServers`. Here's the minimal shape you'll reuse all track:

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
- `args` — what to pass it (the package, then any settings).

### Step 2 — See where remote connectors live

In the Claude app: **Settings → Connectors**. These are remote MCP servers — you enable and sign in, no config file. Notice the difference from Step 1: no `command`, no install, just an authorized link.

### Step 3 — Learn the anatomy of a tool call

When Claude uses an MCP tool, four things happen:

1. Claude **decides** a tool fits the task.
2. It **calls** the tool with structured inputs (e.g. `create_issue(title, body)`).
3. The server **runs** it and returns a result.
4. You **see and approve** it (Claude asks before actions that change things).

You stay in the loop — MCP gives Claude *reach*, not *free rein*.

### Step 4 — Map your own needs

On paper, list the systems you'd want Claude to reach: code (GitHub?), tickets (Jira?), cloud (Azure?), your own files or scripts. Next to each, note **read** vs **write** — you'll scope servers to the least you need (E6).

---

## 🧩 Local vs remote at a glance

| | **Local server (stdio)** | **Remote connector (URL)** |
|---|---|---|
| Runs | On your PC | Hosted by the provider |
| Setup | Edit config file | Enable + OAuth sign-in |
| Install needed | Usually yes (`npx`/`python`) | No |
| Best for | Filesystem, custom servers you build | GitHub, Atlassian, big SaaS |
| Auth | Local / tokens you set | OAuth, you approve scopes |

---

## ✅ Checkpoint

- [ ] You can name the three MCP roles (host/client, server, you).
- [ ] You can explain tools vs resources vs prompts.
- [ ] You found both the local config file **and** the Connectors screen.
- [ ] You listed the systems you want Claude to reach, marked read vs write.

---

## 🎯 Homework

Sketch your ideal MCP setup: which providers you'd connect remotely, which servers you'd run locally, and the least access each needs. Keep the sketch — the next lessons implement it provider by provider.

---

## 💡 Key takeaways

- MCP is a **universal plug**: hosts (Claude) connect to **servers** that expose **tools**, **resources**, and **prompts**.
- Servers are either **local** (config file, run on your PC) or **remote connectors** (URL + OAuth, nothing to install).
- Claude gets **reach**, not free rein — you approve actions and scope each server.

🌐 [Polski](../../pl/track-e/01-czym-jest-mcp.md) · [← Track index](../README.md) · [Next: GitHub MCP →](02-github-mcp.md)
