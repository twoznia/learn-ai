# E5 — Zbuduj własny serwer MCP (z narzędziami)

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: Python (z kursu podstawowego), Gemini CLI

🌐 [English](../../en/track-e/05-build-your-own-mcp-server.md) · [← Wstecz](04-azure-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Bezpieczeństwo i zarządzanie →](06-mcp-bezpieczenstwo.md)

---

## 🧠 Teoria (4 min)

Podłączanie cudzych serwerów jest świetne — ale prawdziwy mistrzowski ruch to **zbudowanie własnego serwera MCP**, udostępnienie *Twoich* funkcji jako **narzędzi**, które Gemini może wołać. Ponieważ MCP to standard, serwer, który zbudujesz, działa z Gemini CLI (i każdym innym hostem MCP).

Najłatwiejsza droga to **FastMCP** (część oficjalnego pakietu `mcp`). Robisz:

1. Tworzysz serwer.
2. Dekorujesz zwykłe funkcje Pythona przez `@mcp.tool()`.
3. Rejestrujesz serwer w Gemini CLI.

Każda udekorowana funkcja staje się narzędziem. Jej **nazwa**, **parametry** (z sygnatury) i **docstring** (opis, który Gemini czyta) biorą się z Twojego kodu. Dobre nazwy i jasne docstringi = narzędzia używane poprawnie.

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
    """Dodaj dwie liczby i zwróć sumę."""
    return a + b

@mcp.tool()
def word_count(text: str) -> int:
    """Policz liczbę słów w kawałku tekstu."""
    return len(text.split())

if __name__ == "__main__":
    mcp.run()   # rozmawia z hostem przez stdio
```

Dwie funkcje → dwa narzędzia. Docstringi to to, czym Gemini je wybiera.

### Krok 3 — Zarejestruj go w Gemini CLI

Znajdź ścieżkę do Pythona:

```powershell
(Get-Command python).Source
```

Dodaj serwer (zamień obie ścieżki):

```powershell
gemini mcp add my-tools -- C:\Sciezka\Do\python.exe C:\Users\TwojaNazwa\my_server.py
```

> Wolisz konfigurację? Dodaj ten sam pod `mcpServers` w `.gemini/settings.json`:
> ```json
> { "mcpServers": { "my-tools": { "command": "C:\\Sciezka\\Do\\python.exe", "args": ["C:\\Users\\TwojaNazwa\\my_server.py"] } } }
> ```
> Zrestartuj CLI.

### Krok 4 — Użyj swoich narzędzi

Potwierdź przez `/mcp`, potem poproś Gemini o coś, co ich wymaga:

```text
Używając swoich narzędzi: ile to 2379 + 8462 i ile słów jest w
„model context protocol makes tools easy”?
```

Gemini woła `add` i `word_count`, uruchamia *Twój* kod i odpowiada. Właśnie rozszerzyłeś Gemini o własne umiejętności. 🎉

### Krok 5 — Dodaj narzędzie robiące coś prawdziwego

```python
from pathlib import Path

@mcp.tool()
def save_note(title: str, body: str) -> str:
    """Zapisz notatkę jako plik .txt w folderze Documents/notes użytkownika.
    Zwraca pełną ścieżkę zapisanego pliku."""
    folder = Path.home() / "Documents" / "notes"
    folder.mkdir(parents=True, exist_ok=True)
    path = folder / f"{title}.txt"
    path.write_text(body, encoding="utf-8")
    return str(path)
```

Zrestartuj CLI, potem:

```text
Użyj save_note, by zapisać notatkę o tytule „ideas” z trzema punktami o MCP.
```

Gemini wypełnia argumenty, uruchamia Twoją funkcję i raportuje ścieżkę. Ten sam kształt co serwery GitHub/Atlassian/Azure — tylko Twój.

---

## 🧩 Co czyni dobre narzędzie

| Rób | Dlaczego |
|----|-----|
| Jasna nazwa (`save_note`, nie `do_it`) | Gemini dopasowuje zadania do nazw |
| Precyzyjny docstring | To opis „kiedy mnie użyć” |
| Typowane parametry (`title: str`) | Gemini wypełnia je poprawnie |
| Zwracaj użyteczną wartość | Gemini raportuje ją z powrotem |
| Niech każde narzędzie robi jedną rzecz | Łatwiej wołać i rozumować |

> **Bezpieczeństwo:** Twoje narzędzie działa z *Twoimi* uprawnieniami. Waliduj wejścia, unikaj destrukcyjnych akcji we wczesnych wersjach i kieruj narzędzia plikowe na dedykowany folder — nie na cały dysk.

---

## ✅ Sprawdzenie

- [ ] `pip install "mcp[cli]"` się powiódł.
- [ ] Twój serwer z `add` i `word_count` jest zarejestrowany i pokazuje się pod `/mcp`.
- [ ] Gemini wywołał Twoje narzędzia i zwrócił poprawne wyniki.
- [ ] Dodałeś trzecie narzędzie (`save_note`) robiące realną pracę.

---

## 🎯 Zadanie

Dodaj jedno narzędzie naprawdę Ci przydatne — przelicz jednostki, wyszukaj coś w lokalnym CSV, sformatuj tekst po swojemu. Napisz zwięzły docstring, zrestartuj i potwierdź, że Gemini sięga po nie w odpowiednim momencie.

---

## 💡 Najważniejsze wnioski

- **FastMCP** zamienia zwykłe funkcje Pythona w **narzędzia** MCP przez `@mcp.tool()` — nazwa, parametry i docstring z Twojego kodu.
- Zarejestruj serwer przez `gemini mcp add` (lub `settings.json`), zrestartuj i Gemini może go wołać.
- **Docstringi to interfejs**, który Gemini czyta; Twoje narzędzia działają z Twoimi uprawnieniami, więc waliduj je i ograniczaj.

🌐 [English](../../en/track-e/05-build-your-own-mcp-server.md) · [← Wstecz](04-azure-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Bezpieczeństwo i zarządzanie →](06-mcp-bezpieczenstwo.md)
