# Projekt końcowy 04 — Zbuduj serwer MCP

⏱️ **18 minut** · Poziom: Projekt końcowy · Wymagania: Python + `mcp[cli]` (Lekcja 2), Twój projekt (Lekcja 3)

🌐 [English](../../en/lessons/04-build-the-mcp-server.md) · [← Poprzednia](03-zaprojektuj-drugi-mozg.md) · [Strona projektu](../README.md) · [Dalej: Podłącz i przetestuj narzędzia →](05-podlacz-i-przetestuj-narzedzia.md)

---

## 🧠 Teoria (3 min)

Teraz budujemy **serwer MCP** — program Python, który daje agentowi ręce. Używając **FastMCP** (ten sam wzorzec co Claude zaawansowany E5), każda funkcja Pythona udekorowana `@mcp.tool()` staje się **narzędziem**, które agent może wywołać. Jej **nazwa**, **parametry** i **docstring** pochodzą z Twojego kodu — a docstring to, co agent czyta, by zdecydować, *kiedy* go użyć.

Nasze cztery narzędzia działają na lokalnym folderze `notes\`: `save_note`, `search_notes`, `get_note`, `list_notes`.

> Możesz oczywiście poprosić Claude Code o pomoc w napisaniu tego pliku — ale przeczytaj i zrozum każdą linię. Jesteś właścicielem tego, co wysyłasz.

---

## 🛠️ Zbuduj to (14 min)

### Krok 1 — Utwórz plik serwera

W folderze `second-brain\` utwórz `brain_server.py`:

```powershell
notepad brain_server.py
```

### Krok 2 — Wklej serwer

```python
from pathlib import Path
from datetime import date
import re
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("second-brain")

# Notatki mieszkają w folderze "notes" obok tego pliku.
NOTES_DIR = Path(__file__).parent / "notes"
NOTES_DIR.mkdir(exist_ok=True)


def _slug(title: str) -> str:
    """Zamień tytuł na bezpieczny slug pliku."""
    s = re.sub(r"[^a-z0-9]+", "-", title.lower()).strip("-")
    return s or "note"


@mcp.tool()
def save_note(title: str, content: str, tags: list[str] = []) -> str:
    """Save a new note as a Markdown file with frontmatter (title, tags, created
    date). Returns the saved file path. Use when the user wants to capture info."""
    path = NOTES_DIR / f"{_slug(title)}.md"
    n = 2
    while path.exists():                      # nie nadpisuj istniejącej notatki
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
    mcp.run()   # rozmawia z agentem przez stdio
```

> Docstringi zostawiamy po angielsku — to interfejs, który czyta model; działa tak samo dobrze. Możesz je przetłumaczyć, jeśli wolisz.

### Krok 3 — Sprawdź, że się uruchamia

```powershell
python brain_server.py
```

Jeśli startuje bez błędów i czeka (bez awarii), Twój serwer jest poprawny. Naciśnij **Ctrl+C**, by zatrzymać — agent uruchomi go za Ciebie w następnej lekcji.

### Krok 4 — Zrozum cztery narzędzia

Przeczytaj ponownie każdy docstring. Zauważ, że mówią *co narzędzie robi* **oraz** *kiedy go użyć* — to „kiedy" jest sygnałem, którego agent używa, by wybrać poprawnie. To inżynieria promptów zastosowana do kodu.

### Krok 5 — Zauważ granicę bezpieczeństwa

Każde narzędzie dotyka tylko `NOTES_DIR`. Serwer dosłownie **nie może** czytać ani zapisywać poza folderem `notes\` — wbudowana bariera, na której oprzemy się w Lekcji 8.

---

## 🧩 Twoje cztery narzędzia

| Narzędzie | Czyta/Zapisuje | Zwraca |
|------|--------------|---------|
| `save_note` | Zapisuje nowy `.md` | Ścieżkę pliku |
| `search_notes` | Czyta wszystkie notatki | Dopasowania + fragmenty |
| `get_note` | Czyta jedną notatkę | Pełną treść |
| `list_notes` | Czyta wszystkie notatki | Tytuły (wg tagu) |

> **Docstringi to interfejs.** Jeśli agent kiedyś wybierze złe narzędzie, dociśnij linię „use when…" docstringa — to Twoja kierownica.

---

## ✅ Sprawdzian

- [ ] `brain_server.py` istnieje w projekcie ze wszystkimi czterema narzędziami.
- [ ] `python brain_server.py` startuje bez błędów.
- [ ] Każde narzędzie ma precyzyjny docstring mówiący, co robi i kiedy go użyć.
- [ ] Rozumiesz, że serwer dotyka tylko folderu `notes\`.

---

## 🎯 Praca domowa

Przeczytaj funkcję `save_note` linia po linii i napisz jednozdaniowy komentarz nad każdym blokiem, wyjaśniając go (poproś Claude Code o sprawdzenie Twoich wyjaśnień). Głębokie zrozumienie tego pliku opłaci się, gdy rozwiniesz go w Lekcji 8.

---

## 💡 Najważniejsze wnioski

- **FastMCP** zamienia funkcje Pythona w **narzędzia** przez `@mcp.tool()` — nazwa, parametry i docstring pochodzą z Twojego kodu.
- Twoje cztery narzędzia działają **tylko na lokalnym folderze `notes\`** — darmowo, prywatnie i bezpiecznie ograniczone.
- **Docstringi to interfejs**, który agent czyta — precyzyjne linie „use when…" sprawiają, że wybiera właściwe narzędzie.

🌐 [English](../../en/lessons/04-build-the-mcp-server.md) · [← Poprzednia](03-zaprojektuj-drugi-mozg.md) · [Strona projektu](../README.md) · [Dalej: Podłącz i przetestuj narzędzia →](05-podlacz-i-przetestuj-narzedzia.md)
