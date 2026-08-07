# Capstone 05 — Connect & Test the Tools

⏱️ **14 minutes** · Level: Capstone · Needs: your MCP server (Lesson 4), Claude Code

🌐 [Polski](../../pl/lessons/05-podlacz-i-przetestuj-narzedzia.md) · [← Prev](04-build-the-mcp-server.md) · [Capstone home](../README.md) · [Next: Author your Skills →](06-author-your-skills.md)

---

## 🧠 Theory (3 min)

Your server exists, but the agent doesn't know about it yet. **Connecting** it tells Claude Code to launch `brain_server.py` and expose its tools. Then we **test each tool** by asking the agent to use it — and approving the calls.

Two ways to register the server:

- **Quick:** the `claude mcp add` command.
- **Committable:** a `.mcp.json` file in your project — so the config ships with your repo (great for Lesson 8).

> Exact MCP commands and config evolve — run `claude mcp --help` for the current options. The idea (point the agent at your server) is stable.

---

## 🛠️ Practice (10 min)

### Step 1 — Register the server (quick way)

From your `second-brain\` folder:

```powershell
claude mcp add second-brain -- python (Resolve-Path .\brain_server.py)
```

Or spell out the full path:

```powershell
claude mcp add second-brain -- python C:\Users\YourName\second-brain\brain_server.py
```

### Step 2 — Or use a committable `.mcp.json`

Prefer config you can commit? Create `.mcp.json` in the project root:

```json
{
  "mcpServers": {
    "second-brain": {
      "command": "python",
      "args": ["C:\\Users\\YourName\\second-brain\\brain_server.py"]
    }
  }
}
```

### Step 3 — Confirm the tools are connected

Start Claude Code in the folder and list MCP servers:

```powershell
claude
```

Then in the session:

```text
/mcp
```

You should see **second-brain** and its four tools. If not, restart Claude Code (config changes need a fresh start).

### Step 4 — Test `save_note`

```text
Save a note titled "Capstone kickoff" with content "Started building my Second
Brain agent today. Excited." and tags work and learning.
```

The agent calls `save_note` and **asks your approval** before writing. Approve it, then check `notes\` — a new `.md` file with frontmatter should be there. 🎉

### Step 5 — Test the other three

```text
List all my notes.
```
```text
Search my notes for "brain".
```
```text
Show me the full "Capstone kickoff" note.
```

Watch the agent pick `list_notes`, `search_notes`, and `get_note` — the right tool each time, because your docstrings told it when to use each.

### Step 6 — Fix a wrong tool choice (if any)

If the agent reaches for the wrong tool, that's a **docstring** problem, not a code problem. Tighten the "use when…" line in `brain_server.py`, restart, and retry — exactly the prompt-engineering-on-code loop from Lesson 4.

---

## 🧩 Connect & verify

| Step | How |
|------|-----|
| Register | `claude mcp add …` or `.mcp.json` |
| Verify | `/mcp` shows `second-brain` + 4 tools |
| Test write | "Save a note titled…" → approve |
| Test read | "List / search / show" notes |
| Fix choice | Tighten the tool's docstring, restart |

> ⚠️ The agent **asks before writing**. Keep that approval step on — it's how you stay in control of your own notes.

---

## ✅ Checkpoint

- [ ] `/mcp` lists **second-brain** with all four tools.
- [ ] `save_note` created a real Markdown file in `notes\` (after your approval).
- [ ] `list_notes`, `search_notes`, and `get_note` all worked.
- [ ] You know a wrong tool choice is fixed by editing the **docstring**.

---

## 🎯 Homework

Capture 5–8 real notes by talking to your agent (ideas, a meeting, a link, a decision). You'll want real content in your Second Brain for the Skills and the weekly review in the next lessons.

---

## 💡 Key takeaways

- Register your server with **`claude mcp add`** or a committable **`.mcp.json`**; verify with **`/mcp`**.
- The agent **calls your tools and asks approval** before writing — you stay in control.
- A wrong tool choice is a **docstring** fix, not a code bug — tighten "use when…" and restart.

🌐 [Polski](../../pl/lessons/05-podlacz-i-przetestuj-narzedzia.md) · [← Prev](04-build-the-mcp-server.md) · [Capstone home](../README.md) · [Next: Author your Skills →](06-author-your-skills.md)
