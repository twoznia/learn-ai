# Capstone 04 — Build the MCP Server

⏱️ **18 minutes** · Level: Capstone · Needs: Python + `mcp[cli]` (Lesson 2), your design (Lesson 3)

🌐 [Polski](../../pl/lessons/04-zbuduj-serwer-mcp.md) · [← Prev](03-design-your-second-brain.md) · [Capstone home](../README.md) · [Next: Connect & test the tools →](05-connect-and-test-tools.md)

---

## 🧠 Theory (3 min)

Now we build the **MCP server** — the Python program that gives your agent hands. Using **FastMCP** (the same pattern as Advanced Claude Track E5), each Python function you decorate with `@mcp.tool()` becomes a **tool** the agent can call. Its **name**, **parameters**, and **docstring** all come from your code — and the docstring is what the agent reads to decide *when* to use it.

Our four tools all operate on the local `notes\` folder: `save_note`, `search_notes`, `get_note`, `list_notes`.

> You can absolutely ask Claude Code to help write this file — but read and understand every line. You own what you ship.

---

## 🛠️ Build it (14 min)

### Step 1 — Create the server file

In your `second-brain\` folder, create `brain_server.py`:

```powershell
notepad brain_server.py
```

### Step 2 — Paste the server

```python
from pathlib import Path
from datetime import date
import re
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("second-brain")

# Notes live in a "notes" folder next to this file.
NOTES_DIR = Path(__file__).parent / "notes"
NOTES_DIR.mkdir(exist_ok=True)


def _slug(title: str) -> str:
    """Turn a title into a safe filename slug."""
    s = re.sub(r"[^a-z0-9]+", "-", title.lower()).strip("-")
    return s or "note"


@mcp.tool()
def save_note(title: str, content: str, tags: list[str] = []) -> str:
    """Save a new note as a Markdown file with frontmatter (title, tags, created
    date). Returns the saved file path. Use when the user wants to capture info."""
    path = NOTES_DIR / f"{_slug(title)}.md"
    n = 2
    while path.exists():                      # don't overwrite an existing note
        path = NOTES_DIR / f"{_slug(title)}-{n}.md"
        n += 1
    front = (
        f"---\ntitle: {title}\n"
        f"tags: [{', '.join(tags)}]\n"
        f"created: {date.today().isoformat()}\n---\n\n"
    )
    path.write_text(front + content.strip() + "\n", encoding="utf-8")
    return str(path)


@mcp.tool()
def search_notes(query: str) -> str:
    """Search all notes (title, tags, body; case-insensitive) for a query.
    Returns matching note titles with a short snippet. Use to find relevant notes."""
    q = query.lower()
    hits = []
    for f in sorted(NOTES_DIR.glob("*.md")):
        text = f.read_text(encoding="utf-8")
        i = text.lower().find(q)
        if i != -1:
            snippet = text[max(0, i - 40): i + 60].replace("\n", " ").strip()
            hits.append(f"- {f.stem}: …{snippet}…")
    return "\n".join(hits) if hits else f'No notes matched "{query}".'


@mcp.tool()
def get_note(title: str) -> str:
    """Return the full content of one note, found by its title or filename slug.
    Use to read a specific note in full."""
    path = NOTES_DIR / f"{_slug(title)}.md"
    if not path.exists():
        matches = [f for f in NOTES_DIR.glob("*.md") if _slug(title) in f.stem]
        if not matches:
            return f'No note found for "{title}".'
        path = matches[0]
    return path.read_text(encoding="utf-8")


@mcp.tool()
def list_notes(tag: str = "") -> str:
    """List all note titles, optionally filtered to a given tag.
    Use to browse or get an overview of the Second Brain."""
    out = []
    for f in sorted(NOTES_DIR.glob("*.md")):
        text = f.read_text(encoding="utf-8")
        if tag and tag.lower() not in text.lower():
            continue
        m = re.search(r"^title:\s*(.+)$", text, re.MULTILINE)
        out.append(f"- {(m.group(1).strip() if m else f.stem)}  ({f.name})")
    if out:
        return "\n".join(out)
    return f'No notes tagged "{tag}".' if tag else "No notes yet."


if __name__ == "__main__":
    mcp.run()   # talks to the agent over stdio
```

### Step 3 — Sanity-check it runs

```powershell
python brain_server.py
```

If it starts without errors and waits (no crash), your server is valid. Press **Ctrl+C** to stop — the agent will launch it for you in the next lesson.

### Step 4 — Understand the four tools

Re-read each docstring. Notice they say *what the tool does* **and** *when to use it* — that "when" is the signal the agent uses to choose correctly. This is prompt engineering applied to code.

### Step 5 — Note the safety boundary

Every tool only touches `NOTES_DIR`. The server literally **cannot** read or write outside your `notes\` folder — a built-in guardrail we'll lean on in Lesson 8.

---

## 🧩 Your four tools

| Tool | Reads/Writes | Returns |
|------|--------------|---------|
| `save_note` | Writes a new `.md` | File path |
| `search_notes` | Reads all notes | Matches + snippets |
| `get_note` | Reads one note | Full content |
| `list_notes` | Reads all notes | Titles (by tag) |

> **Docstrings are the interface.** If the agent ever picks the wrong tool, tighten the docstring's "use when…" — that's your steering wheel.

---

## ✅ Checkpoint

- [ ] `brain_server.py` exists in your project with all four tools.
- [ ] `python brain_server.py` starts without errors.
- [ ] Each tool has a precise docstring saying what it does and when to use it.
- [ ] You understand the server only touches the `notes\` folder.

---

## 🎯 Homework

Read the `save_note` function line by line and write a one-sentence comment above each block explaining it (ask Claude Code to check your explanations). Understanding this file deeply pays off when you extend it in Lesson 8.

---

## 💡 Key takeaways

- **FastMCP** turns Python functions into **tools** via `@mcp.tool()` — name, params, and docstring come from your code.
- Your four tools operate **only on the local `notes\` folder** — free, private, and safely scoped.
- **Docstrings are the interface** the agent reads — precise "use when…" lines make it choose the right tool.

🌐 [Polski](../../pl/lessons/04-zbuduj-serwer-mcp.md) · [← Prev](03-design-your-second-brain.md) · [Capstone home](../README.md) · [Next: Connect & test the tools →](05-connect-and-test-tools.md)
