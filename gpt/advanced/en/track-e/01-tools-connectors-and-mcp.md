# E1 — Tools, Connectors & MCP Explained

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: the Codex CLI installed & signed in (see D5)

🌐 [Polski](../../pl/track-e/01-narzedzia-konektory-i-mcp.md) · [← Track index](../README.md) · [Next: GitHub with Codex →](02-github-mcp.md)

---

## 🧠 Theory (6 min)

To do real work, GPT needs to reach **outside tools and data**. There are three related ways it does that — know the difference:

| Way | What it is | Where |
|-----|-----------|-------|
| **Connectors** | Link ChatGPT to your apps (Google Drive, GitHub, etc.) | The ChatGPT **app** (Track F) |
| **Custom GPT Actions** | Give a Custom GPT its own API calls | Custom GPTs (Track A1) |
| **MCP servers** | An open standard for plugging in *any* external tool | The Codex CLI (this track) |

**MCP (Model Context Protocol)** is the universal one. It's like a **standard plug**: instead of every tool inventing its own connection, MCP gives one shared socket. The **Codex CLI is an MCP host** — it connects to MCP **servers** that expose **tools** (actions GPT can take: create an issue, run a query, list resources).

```
Codex CLI (host) ── connects to ──▶ MCP server ── exposes ──▶ tools
   you approve actions               (GitHub, Azure, your own)
```

Two ways a server connects:
- **Local (stdio)** — a small program launched on your PC (e.g. a filesystem server, or one you build).
- **Remote (URL)** — a hosted server you point Codex at.

This track connects the big providers (GitHub, Atlassian, Azure) and one you build yourself — all through the Codex CLI.

---

## 🛠️ Practice (8 min)

### Step 1 — Find where Codex stores config

The Codex CLI keeps its settings in `~/.codex/config.toml` (that's `C:\Users\YourName\.codex\config.toml` on Windows). MCP servers live there under `[mcp_servers.<name>]`.

```powershell
notepad $HOME\.codex\config.toml
```

The shape you'll reuse (a local filesystem server):

```toml
[mcp_servers.workspace]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "C:\\Users\\YourName\\mcp-workspace"]
```

- `command` — the program to launch (`npx`, `python`, `node`…).
- `args` — the package and any settings.

There's also a shortcut subcommand: `codex mcp add <name> -- <command>` (you'll use it in E2). Run `codex mcp --help` for current options.

### Step 2 — List MCP servers

Inside Codex, list connected servers (or run `codex mcp list` in the terminal):

```text
/mcp
```

Empty is fine — we'll add some in the next lessons.

### Step 3 — Understand a tool call

When GPT uses an MCP tool: it **decides** a tool fits → **calls** it with structured inputs → the server **runs** it → **you approve** the result (Codex asks before actions that change things). You stay in the loop.

### Step 4 — Know the three surfaces apart

- **Connectors** are the easy, click-to-enable integrations in the **ChatGPT app** (Track F).
- **Custom GPT Actions** let a Custom GPT call a specific API you configure.
- **MCP** is the developer-grade, universal path in the **Codex CLI** — and where you can also run servers you build.

### Step 5 — Map your needs

List systems you'd want GPT to reach: code (GitHub?), tickets (Jira?), cloud (Azure?), your own files/scripts. Mark **read** vs **write** — you'll scope each server to the least it needs (E6).

---

## 🧩 Three ways to reach out

| | **Connectors (app)** | **Custom GPT Actions** | **MCP (Codex CLI)** |
|---|---|---|---|
| Where | ChatGPT app | Custom GPTs | Codex CLI |
| Setup | Enable + sign in | Configure an API | Config / `codex mcp add` |
| Best for | Drive, GitHub, everyday apps | One GPT's specific API | Any external tool, custom servers |

---

## ✅ Checkpoint

- [ ] You can name the three ways GPT reaches tools (connectors, Actions, MCP).
- [ ] You found `~/.codex/config.toml` and the `[mcp_servers.*]` shape.
- [ ] You listed MCP servers with `/mcp` (or `codex mcp list`).
- [ ] You listed systems to connect, marked read vs write.

---

## 🎯 Homework

Sketch your ideal Codex CLI setup: which MCP servers you'd add, scoped to what, read-only or not. Keep the sketch — the next lessons implement it provider by provider.

---

## 💡 Key takeaways

- GPT reaches tools three ways: **connectors** (app), **Custom GPT Actions**, and **MCP** (Codex CLI).
- **MCP** is the universal plug; the **Codex CLI is an MCP host** connecting to **servers** that expose **tools**.
- Servers are **local** (a program) or **remote** (a URL), configured in `~/.codex/config.toml`; you scope them and **approve** actions.

🌐 [Polski](../../pl/track-e/01-narzedzia-konektory-i-mcp.md) · [← Track index](../README.md) · [Next: GitHub with Codex →](02-github-mcp.md)
