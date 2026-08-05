# Lesson 15 — MCP: Connect Claude to Your Tools

⏱️ **10 minutes** · Level: Beginner → Intermediate · Needs: Claude Desktop (L5)

[← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Theory (4 min)

So far Claude only knows what you type or upload. **MCP (Model Context Protocol)** changes that: it's a standard way to safely give Claude access to **tools and data** — like your files, a database, a calendar, or a web service.

Analogy: MCP is like giving your assistant a **set of keys** to specific rooms. You decide which keys. An **MCP server** is a small program that exposes one capability (e.g. "read files in this folder"). Claude Desktop connects to these servers and can then use them when helpful.

Why it matters:
- Ask Claude about **your actual files** without uploading each one.
- Let Claude **look things up** or take actions in tools you already use.
- You stay in control — MCP servers only expose what you allow.

> ⚠️ **Safety first:** Only connect MCP servers you trust, and only give access to folders/data you're comfortable with. Start with a harmless test folder.

---

## 🛠️ Practice (5 min)

We'll connect the official **Filesystem** MCP server so Claude Desktop can read files in one folder you choose. (You need Node.js from Lesson 13.)

### Step 1 — Make a safe test folder

In PowerShell:

```powershell
mkdir $HOME\claude-mcp-test
"Shopping list: milk, eggs, bread" | Out-File $HOME\claude-mcp-test\list.txt
"Project idea: a weather app for gardeners" | Out-File $HOME\claude-mcp-test\ideas.txt
```

### Step 2 — Open Claude Desktop's config file

1. In **Claude Desktop**: menu → **Settings** → **Developer** → **Edit Config** (this opens `claude_desktop_config.json`).
2. If it's empty, that's fine — we'll fill it in.

> The file lives at `%APPDATA%\Claude\claude_desktop_config.json`. You can also open it directly:
> ```powershell
> notepad $env:APPDATA\Claude\claude_desktop_config.json
> ```

### Step 3 — Add the Filesystem server

Paste this, replacing `YourName` with your actual Windows username, and save:

```json
{
  "mcpServers": {
    "my-files": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:\\Users\\YourName\\claude-mcp-test"
      ]
    }
  }
}
```

> This tells Claude Desktop: "start a filesystem server that can only see the `claude-mcp-test` folder." That single folder is the *only* thing it can read.

### Step 4 — Restart Claude Desktop

**Fully quit** Claude Desktop (right-click the taskbar icon → Quit) and reopen it. Look for a small tools/plug icon indicating MCP is connected.

### Step 5 — Try it

Ask Claude Desktop:

```text
What files are in my connected folder, and what do they contain?
```

```text
Summarize my ideas.txt and suggest one improvement.
```

Claude reads the real files — no uploading. 🎉 To connect a different folder later, change the path in the config.

---

## 🧭 What else MCP can do

There are MCP servers for many things (databases, GitHub, web search, calendars, and more). The pattern is always the same:

1. Add the server to `claude_desktop_config.json`.
2. Restart Claude Desktop.
3. Ask Claude to use it.

Explore official servers at **https://modelcontextprotocol.io** and Anthropic's docs. Only add ones you understand and trust.

---

## ✅ Checkpoint

- [ ] You created a safe test folder with a couple of files.
- [ ] You added the filesystem server to the config and restarted.
- [ ] Claude read and summarized a file from that folder.

---

## 🎯 Homework

Add a second file to `claude-mcp-test` (e.g. a rough to-do list) and ask Claude to turn it into a clean checklist. Notice you never uploaded anything — MCP did the reading.

---

## 💡 Key takeaways

- **MCP** safely connects Claude to tools and data you choose.
- An **MCP server** exposes one capability (e.g. read one folder).
- Configure servers in `claude_desktop_config.json`, then restart Claude Desktop.
- Only connect trusted servers and limit what they can access.

[← Prev](14-mini-project.md) · [Course home](../README.md) · [Next: Prompt engineering →](16-prompt-engineering.md)
