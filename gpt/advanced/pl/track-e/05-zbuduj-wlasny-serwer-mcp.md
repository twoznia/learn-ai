# E5 — Zbuduj własny serwer MCP (z narzędziami)

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: Python (z kursu dla początkujących), Codex CLI

🌐 [English](../../en/track-e/05-build-your-own-mcp-server.md) · [← Poprzedni](04-azure-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Bezpieczeństwo i zarządzanie →](06-mcp-bezpieczenstwo.md)

---

## 🧠 Teoria (4 min)

Podłączanie cudzych serwerów jest świetne — ale prawdziwy majstersztyk to **zbudowanie własnego serwera MCP**, udostępniającego *Twoje* funkcje jako **narzędzia**, które GPT może wywołać. Ponieważ MCP to standard, serwer, który zbudujesz, działa z Codex CLI (i każdym innym hostem MCP).

Najłatwiejsza droga to **FastMCP** (część oficjalnego pakietu Pythona `mcp`). Ty:

1. Tworzysz serwer.
2. Dekorujesz zwykłe funkcje Pythona przez `@mcp.tool()`.
3. Rejestrujesz serwer w Codex CLI.

Każda udekorowana funkcja staje się narzędziem. Jej **nazwa**, **parametry** (z sygnatury) i **docstring** (opis, który GPT czyta, by zdecydować, kiedy jej użyć) — wszystko pochodzi z Twojego kodu. Dobre nazwy i jasne docstringi = narzędzia, których GPT używa poprawnie.

---

## 🛠️ Zbuduj to (10 min)

### Krok 1 — Zainstaluj MCP SDK

```powershell
pip install "mcp[cli]"
```

### Krok 2 — Napisz serwer z dwoma narzędziami

Utwórz `my_server.py`:

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
    mcp.run()   # rozmawia z hostem przez stdio
```

Dwie funkcje → dwa narzędzia. Docstringi to, czym GPT je dobiera.

### Krok 3 — Zarejestruj go w Codex CLI

Znajdź ścieżkę do Pythona:

```powershell
(Get-Command python).Source
```

Dodaj serwer (podmień obie ścieżki):

```powershell
codex mcp add my-tools -- C:\Sciezka\Do\python.exe C:\Users\TwojaNazwa\my_server.py
```

> Wolisz config? Dodaj to samo pod `~/.codex/config.toml`:
> ```toml
> [mcp_servers.my-tools]
> command = "C:\\Sciezka\\Do\\python.exe"
> args = ["C:\\Users\\TwojaNazwa\\my_server.py"]
> ```
> Zrestartuj Codeksa.

### Krok 4 — Użyj swoich narzędzi

Potwierdź przez `/mcp`, potem poproś GPT o coś, co ich wymaga:

```text
Używając swoich narzędzi: ile to 2379 + 8462 i ile słów jest w
„model context protocol makes tools easy"?
```

GPT wywołuje `add` i `word_count`, uruchamia *Twój* kod i odpowiada. Właśnie rozszerzyłeś/aś GPT o własne umiejętności. 🎉

### Krok 5 — Dodaj narzędzie, które robi prawdziwą pracę

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

Zrestartuj Codeksa, potem:

```text
Użyj save_note, by zapisać notatkę zatytułowaną „ideas" z trzema punktami o MCP.
```

GPT wypełnia argumenty, uruchamia Twoją funkcję i raportuje ścieżkę. Ten sam kształt co serwery GitHub/Atlassian/Azure — tylko Twój.

---

## 🧩 Co czyni dobre narzędzie

| Rób | Dlaczego |
|----|-----|
| Jasna nazwa (`save_note`, nie `do_it`) | GPT dopasowuje zadania do nazw |
| Precyzyjny docstring | To opis „kiedy mnie użyć" |
| Typowane parametry (`title: str`) | GPT wypełnia je poprawnie |
| Zwracaj użyteczną wartość | GPT ją raportuje |
| Niech każde narzędzie robi jedną rzecz | Łatwiej wywołać i rozumować |

> **Bezpieczeństwo:** Twoje narzędzie działa z *Twoimi* uprawnieniami. Waliduj dane wejściowe, unikaj destrukcyjnych akcji we wczesnych wersjach i trzymaj narzędzia plikowe wycelowane w dedykowany folder — nie cały dysk.

---

## ✅ Sprawdzian

- [ ] `pip install "mcp[cli]"` się powiodło.
- [ ] Twój serwer z `add` i `word_count` jest zarejestrowany i widoczny pod `/mcp`.
- [ ] GPT wywołał Twoje narzędzia i zwrócił poprawne wyniki.
- [ ] Dodałeś/aś trzecie narzędzie (`save_note`), które robi prawdziwą pracę.

---

## 🎯 Praca domowa

Dodaj jedno narzędzie naprawdę Ci przydatne — przelicz jednostki, wyszukaj coś w lokalnym CSV, sformatuj tekst po swojemu. Napisz zwięzły docstring, zrestartuj i potwierdź, że GPT sięga po nie we właściwym momencie.

---

## 💡 Najważniejsze wnioski

- **FastMCP** zamienia zwykłe funkcje Pythona w **narzędzia** MCP przez `@mcp.tool()` — nazwa, parametry i docstring pochodzą z Twojego kodu.
- Zarejestruj serwer przez `codex mcp add` (lub `config.toml`), zrestartuj, a GPT może go wywołać.
- **Docstringi to interfejs**, który GPT czyta; Twoje narzędzia działają z Twoimi uprawnieniami, więc waliduj i ograniczaj je.

🌐 [English](../../en/track-e/05-build-your-own-mcp-server.md) · [← Poprzedni](04-azure-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Bezpieczeństwo i zarządzanie →](06-mcp-bezpieczenstwo.md)
