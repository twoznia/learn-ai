# G5 — MCP Inside Claude Code

⏱️ **15 minutes** · Track: 🅶 Claude Code in Depth · Needs: Claude Code installed & logged in (Track E helps)

🌐 [Polski](../../pl/track-g/05-mcp-w-claude-code.md) · [← Prev](04-hooks.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

Track E connected MCP servers to **Claude Desktop**. Claude Code speaks MCP too — and it's arguably the best place to use it, because Claude Code can **combine your files, the terminal, and MCP tools** in one workflow. Imagine one session where Claude reads your code, runs tests, **and** opens a GitHub issue — all through approved tools.

In Claude Code you manage MCP servers from the **command line** (or a project config), not a JSON file you hunt for. The mental model is the same as E1: **hosts** (Claude Code) connect to **servers** exposing **tools**; you keep least privilege and approve writes.

---

## 🛠️ Practice (10 min)

### Step 1 — See what's connected

In Claude Code:

```text
/mcp
```

This lists MCP servers available to the session and lets you manage them. Empty is fine — we'll add one.

### Step 2 — Add a server from the terminal

Claude Code has an `mcp` subcommand. The general shape:

```powershell
claude mcp add <name> -- <command to launch the server>
```

For example, a filesystem server scoped to one folder:

```powershell
claude mcp add workspace -- npx -y @modelcontextprotocol/server-filesystem C:\Users\YourName\mcp-workspace
```

Now that server is available in your Claude Code sessions.

> Exact flags evolve — run `claude mcp --help` (or `claude mcp add --help`) to see the current options for local (stdio) vs remote (URL) servers and per-scope config.

### Step 3 — Use MCP tools alongside files and the terminal

Start Claude Code in a project and ask something that spans capabilities:

```text
Read the TODO comments in this project, then create a short markdown checklist
of them in the workspace folder via the filesystem server. Show me before writing.
```

Claude combines reading your code (built-in) with an MCP tool (filesystem) — one workflow, several capabilities.

### Step 4 — Add a bigger provider (optional)

If you use GitHub (Track E2), you can add its server to Claude Code and get end-to-end flows:

```text
Summarize what changed in my last few commits, then draft a GitHub issue capturing
the follow-up work. Ask before creating the issue.
```

Code understanding + a real write action, gated by your approval.

### Step 5 — Scope per project

MCP config can be **project-scoped** (available in this repo) or broader. Keep servers where they belong:
- A project-specific server → project scope.
- A personal helper you use everywhere → user scope.

Run the `/mcp` command or `claude mcp` help to see and set scope.

### Step 6 — Same safety, sharper stakes

Claude Code can act on files, the terminal, **and** MCP tools together — so the discipline from Tracks E6 and G4 matters even more:
- **Least privilege** on every server.
- **Read-only while learning**; approve every write.
- Combine with a **PreToolUse hook** (G4) if you want a hard guardrail on risky actions.

---

## 🧩 Why MCP shines in Claude Code

| Capability | Example |
|------------|---------|
| Files + MCP | Read code → write a checklist via filesystem server |
| Terminal + MCP | Run tests → open a GitHub issue on failure (with approval) |
| Multi-server | Filesystem + GitHub in one task |
| Scoped config | Per-project servers vs personal ones |

> ⚠️ **More reach = more care.** Combining local files, shell, and MCP writes is powerful; keep servers narrowly scoped and keep approving actions that change or send things.

---

## ✅ Checkpoint

- [ ] You listed MCP servers with `/mcp`.
- [ ] You added a server with `claude mcp add` (checking `--help` for current flags).
- [ ] Claude Code combined a built-in capability with an MCP tool in one task.
- [ ] You can explain project vs user scope and the safety rules.

---

## 🎯 Homework

Add one MCP server to Claude Code scoped to a real project. Run a task that combines your files (or the terminal) with that server — read something, then produce or file something via MCP, approving each write. Note where a hook could add a guardrail.

---

## 💡 Key takeaways

- Claude Code speaks **MCP** and manages servers from the **CLI** (`/mcp`, `claude mcp add`) — check `--help` for current flags.
- Its edge is **combining files, the terminal, and MCP tools** in one workflow (e.g. read code → open a GitHub issue).
- **Scope per project**, keep **least privilege**, approve every write, and add a **hook** for hard guardrails.

🌐 [Polski](../../pl/track-g/05-mcp-w-claude-code.md) · [← Prev](04-hooks.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
