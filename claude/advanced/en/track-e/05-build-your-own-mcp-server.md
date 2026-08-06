# E5 — Build Your Own MCP Server (with Tools)

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: Python (from the beginner course), Claude Desktop

🌐 [Polski](../../pl/track-e/05-zbuduj-wlasny-serwer-mcp.md) · [← Prev](04-azure-mcp.md) · [Track index](../README.md) · [Next: MCP at scale →](06-mcp-at-scale-security.md)

---

## 🧠 Theory (4 min)

Connectors are great, but the real power move is **building your own MCP server** — exposing *your* functions as **tools** Claude can call. If you can write a Python function, you can give Claude a new ability.

The easiest path is **FastMCP** (part of the official `mcp` package). You:

1. Create a server.
2. Decorate plain Python functions with `@mcp.tool()`.
3. Register the server in Claude Desktop's config.

Each decorated function becomes a tool. Its **name**, **parameters** (from the signature), and **docstring** (the description Claude reads to decide when to use it) all come straight from your code. Good names and clear docstrings = tools Claude uses correctly.

---

## 🛠️ Build it (10 min)

### Step 1 — Install the MCP SDK

```powershell
pip install "mcp[cli]"
```

### Step 2 — Write a server with two tools

Create `my_server.py`:

```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("my-tools")

@mcp.tool()
def add(a: float, b: float) -> float:
    """Add two numbers and return the sum."""
    return a + b

@mcp.tool()
def word_count(text: str) -> int:
    """Count the number of words in a piece of text."""
    return len(text.split())

if __name__ == "__main__":
    mcp.run()   # talks to the client over stdio
```

Two functions → two tools. The docstrings are what Claude uses to pick them.

### Step 3 — Register it in Claude Desktop

Find your Python path:

```powershell
(Get-Command python).Source
```

Open the config and add your server (replace both paths):

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

```json
{
  "mcpServers": {
    "my-tools": {
      "command": "C:\\Path\\To\\python.exe",
      "args": ["C:\\Users\\YourName\\my_server.py"]
    }
  }
}
```

Save, then **fully quit and reopen** Claude Desktop.

### Step 4 — Use your tools

Ask Claude something that needs them:

```text
Using your tools: what is 2379 + 8462, and how many words are in
"model context protocol makes tools easy"?
```

Claude calls `add` and `word_count`, runs *your* code, and answers. You just extended Claude with your own abilities. 🎉

### Step 5 — Add a tool that does something real

Give Claude a tool that touches a file (still simple, still safe):

```python
from pathlib import Path

@mcp.tool()
def save_note(title: str, body: str) -> str:
    """Save a note as a .txt file in the user's Documents/notes folder.
    Returns the full path of the saved file."""
    folder = Path.home() / "Documents" / "notes"
    folder.mkdir(parents=True, exist_ok=True)
    path = folder / f"{title}.txt"
    path.write_text(body, encoding="utf-8")
    return str(path)
```

Restart Claude Desktop, then:

```text
Use save_note to store a note titled "ideas" with three bullet points about MCP.
```

Claude fills the arguments, runs your function, and reports the path. That's the same shape GitHub/Atlassian/Azure servers use — just yours.

---

## 🧩 What makes a good tool

| Do | Why |
|----|-----|
| Clear name (`save_note`, not `do_it`) | Claude matches tasks to names |
| A precise docstring | It's the "when to use me" description |
| Typed parameters (`title: str`) | Claude fills them correctly |
| Return a useful value | Claude reports it back to you |
| Keep each tool doing one thing | Easier to call and reason about |

> **Safety:** your tool runs with *your* permissions. Validate inputs, avoid destructive actions in early versions, and keep file tools pointed at a dedicated folder — not your whole disk.

---

## ✅ Checkpoint

- [ ] `pip install "mcp[cli]"` succeeded.
- [ ] Your server with `add` and `word_count` is registered and loads after a restart.
- [ ] Claude called your tools and returned correct results.
- [ ] You added a third tool (`save_note`) that does real work.

---

## 🎯 Homework

Add one tool that's genuinely useful to you — convert units, look something up in a local CSV, format text your way. Write a crisp docstring, restart, and confirm Claude reaches for it at the right moment.

---

## 💡 Key takeaways

- **FastMCP** turns plain Python functions into MCP **tools** with `@mcp.tool()` — name, params, and docstring come from your code.
- Register the server in Claude Desktop's config (`command` = python, `args` = your script), restart, and Claude can call it.
- **Docstrings are the interface** Claude reads; your tools run with your permissions, so validate and scope them.

🌐 [Polski](../../pl/track-e/05-zbuduj-wlasny-serwer-mcp.md) · [← Prev](04-azure-mcp.md) · [Track index](../README.md) · [Next: MCP at scale →](06-mcp-at-scale-security.md)
