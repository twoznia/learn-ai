# E5 — Build Your Own MCP Server (with Tools)

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: Python (from the beginner course), the Gemini CLI

🌐 [Polski](../../pl/track-e/05-zbuduj-wlasny-serwer-mcp.md) · [← Prev](04-azure-mcp.md) · [Track index](../README.md) · [Next: Safety & management →](06-mcp-safety.md)

---

## 🧠 Theory (4 min)

Connecting other people's servers is great — but the real power move is **building your own MCP server**, exposing *your* functions as **tools** Gemini can call. Because MCP is a standard, a server you build works with the Gemini CLI (and any other MCP host).

The easiest path is **FastMCP** (part of the official `mcp` Python package). You:

1. Create a server.
2. Decorate plain Python functions with `@mcp.tool()`.
3. Register the server with the Gemini CLI.

Each decorated function becomes a tool. Its **name**, **parameters** (from the signature), and **docstring** (the description Gemini reads to decide when to use it) all come from your code. Good names and clear docstrings = tools Gemini uses correctly.

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
    mcp.run()   # talks to the host over stdio
```

Two functions → two tools. The docstrings are what Gemini uses to pick them.

### Step 3 — Register it with the Gemini CLI

Find your Python path:

```powershell
(Get-Command python).Source
```

Add the server (replace both paths):

```powershell
gemini mcp add my-tools -- C:\Path\To\python.exe C:\Users\YourName\my_server.py
```

> Prefer config? Add the same under `mcpServers` in `.gemini/settings.json`:
> ```json
> { "mcpServers": { "my-tools": { "command": "C:\\Path\\To\\python.exe", "args": ["C:\\Users\\YourName\\my_server.py"] } } }
> ```
> Restart the CLI.

### Step 4 — Use your tools

Confirm with `/mcp`, then ask Gemini something that needs them:

```text
Using your tools: what is 2379 + 8462, and how many words are in
"model context protocol makes tools easy"?
```

Gemini calls `add` and `word_count`, runs *your* code, and answers. You just extended Gemini with your own abilities. 🎉

### Step 5 — Add a tool that does real work

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

Restart the CLI, then:

```text
Use save_note to store a note titled "ideas" with three bullet points about MCP.
```

Gemini fills the arguments, runs your function, and reports the path. Same shape as the GitHub/Atlassian/Azure servers — just yours.

---

## 🧩 What makes a good tool

| Do | Why |
|----|-----|
| Clear name (`save_note`, not `do_it`) | Gemini matches tasks to names |
| A precise docstring | It's the "when to use me" description |
| Typed parameters (`title: str`) | Gemini fills them correctly |
| Return a useful value | Gemini reports it back |
| Keep each tool doing one thing | Easier to call and reason about |

> **Safety:** your tool runs with *your* permissions. Validate inputs, avoid destructive actions in early versions, and keep file tools pointed at a dedicated folder — not your whole disk.

---

## ✅ Checkpoint

- [ ] `pip install "mcp[cli]"` succeeded.
- [ ] Your server with `add` and `word_count` is registered and shows under `/mcp`.
- [ ] Gemini called your tools and returned correct results.
- [ ] You added a third tool (`save_note`) that does real work.

---

## 🎯 Homework

Add one tool that's genuinely useful to you — convert units, look something up in a local CSV, format text your way. Write a crisp docstring, restart, and confirm Gemini reaches for it at the right moment.

---

## 💡 Key takeaways

- **FastMCP** turns plain Python functions into MCP **tools** with `@mcp.tool()` — name, params, and docstring come from your code.
- Register the server with `gemini mcp add` (or `settings.json`), restart, and Gemini can call it.
- **Docstrings are the interface** Gemini reads; your tools run with your permissions, so validate and scope them.

🌐 [Polski](../../pl/track-e/05-zbuduj-wlasny-serwer-mcp.md) · [← Prev](04-azure-mcp.md) · [Track index](../README.md) · [Next: Safety & management →](06-mcp-safety.md)
