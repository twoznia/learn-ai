# A3 — Advanced MCP

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: Claude Desktop + Node.js (from the beginner course)

🌐 [Polski](../../pl/track-a/03-zaawansowane-mcp.md) · [← Prev](02-prompt-library.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (4 min)

In the beginner course you connected **one** MCP server (filesystem) to Claude Desktop. Now we go further: **multiple servers working together**, and the safety habits that matter once Claude can touch real things.

Key ideas:

- **Composing servers.** With a filesystem server *and* a fetch/search server, Claude can read your notes **and** look things up, then combine them.
- **Least privilege.** Give each server the narrowest access that still does the job. A filesystem server should point at one project folder, never your whole `C:`.
- **Know what runs.** Every MCP server is a small program launched on your PC. Only add servers you understand and trust.

---

## 🛠️ Practice (9 min)

### Step 1 — Point the filesystem server at a real working folder

Create a folder you actually want Claude to help with, e.g. a research or writing project:

```powershell
mkdir $HOME\mcp-workspace
"Draft: reasons to switch our newsletter tool" | Out-File $HOME\mcp-workspace\draft.md
```

### Step 2 — Configure two servers together

Open the Claude Desktop config:

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Paste this (replace `YourName`), which registers **two** servers — filesystem and fetch:

```json
{
  "mcpServers": {
    "workspace": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:\\Users\\YourName\\mcp-workspace"
      ]
    },
    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    }
  }
}
```

> The **fetch** server lets Claude retrieve a web page you name. If a specific server package isn't available on your machine, that's fine — the *pattern* of registering multiple servers is what matters. Keep only the ones that install cleanly.

### Step 3 — Restart Claude Desktop

Fully quit (right-click taskbar icon → Quit) and reopen. Look for the tools/plug indicator showing your servers are connected.

### Step 4 — Compose them in one task

Ask Claude Desktop something that needs **both** reading your file and fetching info:

```text
Read draft.md from my workspace. Then fetch this article <paste a URL> and
suggest 3 concrete improvements to my draft based on it. Cite what you used.
```

Claude reads locally *and* pulls the page — a workflow neither server could do alone.

### Step 5 — Practice least privilege

Ask yourself for each server: *what's the smallest scope that still works?*

- Filesystem → **one** folder, not your user directory.
- Anything that can change or send data → be extra cautious; prefer read-only servers while learning.
- Remove servers you're not actively using from the config.

---

## 🔒 MCP safety checklist

| Check | Why |
|-------|-----|
| Do I trust the source of this server? | It runs as a program on your PC |
| Is filesystem access limited to one folder? | Blast-radius control |
| Am I about to let Claude *change* or *send* things? | Read-only is safer while learning |
| Did I remove servers I don't use? | Fewer moving parts, fewer risks |
| Am I reviewing what Claude does with the tools? | You're still the human in the loop |

---

## ✅ Checkpoint

- [ ] You configured **two** servers in one config file.
- [ ] Claude combined a local file with fetched/looked-up info in one answer.
- [ ] You can state the *least privilege* for each server you added.

---

## 🎯 Homework

Design (on paper) an MCP setup for a real recurring task of yours — which servers, scoped to what, read-only or not. Then implement only the read-only parts and try one composed workflow.

---

## 💡 Key takeaways

- Multiple MCP servers can **compose** — read local files *and* fetch/look up, together.
- Apply **least privilege**: narrowest scope, prefer read-only while learning.
- Only add servers you trust; you remain the human reviewing what happens.

🌐 [Polski](../../pl/track-a/03-zaawansowane-mcp.md) · [← Prev](02-prompt-library.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
