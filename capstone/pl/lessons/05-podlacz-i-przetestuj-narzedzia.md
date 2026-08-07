# Projekt końcowy 05 — Podłącz i przetestuj narzędzia

⏱️ **14 minut** · Poziom: Projekt końcowy · Wymagania: Twój serwer MCP (Lekcja 4), Claude Code

🌐 [English](../../en/lessons/05-connect-and-test-tools.md) · [← Poprzednia](04-zbuduj-serwer-mcp.md) · [Strona projektu](../README.md) · [Dalej: Napisz swoje Skille →](06-napisz-swoje-skille.md)

---

## 🧠 Teoria (3 min)

Twój serwer istnieje, ale agent jeszcze o nim nie wie. **Podłączenie** mówi Claude Code, by uruchomił `brain_server.py` i udostępnił jego narzędzia. Potem **testujemy każde narzędzie**, prosząc agenta o użycie — i zatwierdzając wywołania.

Dwa sposoby rejestracji serwera:

- **Szybki:** polecenie `claude mcp add`.
- **Do commitowania:** plik `.mcp.json` w projekcie — by konfiguracja płynęła z repo (świetne do Lekcji 8).

> Dokładne polecenia i konfiguracja MCP ewoluują — uruchom `claude mcp --help` po bieżące opcje. Idea (wskaż agentowi serwer) jest stabilna.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zarejestruj serwer (szybko)

Z folderu `second-brain\`:

```powershell
claude mcp add second-brain -- python (Resolve-Path .\brain_server.py)
```

Lub podaj pełną ścieżkę:

```powershell
claude mcp add second-brain -- python C:\Users\TwojaNazwa\second-brain\brain_server.py
```

### Krok 2 — Albo użyj `.mcp.json` do commitowania

Wolisz konfigurację, którą zacommitujesz? Utwórz `.mcp.json` w korzeniu projektu:

```json
{
  "mcpServers": {
    "second-brain": {
      "command": "python",
      "args": ["C:\\Users\\TwojaNazwa\\second-brain\\brain_server.py"]
    }
  }
}
```

### Krok 3 — Potwierdź, że narzędzia są podłączone

Uruchom Claude Code w folderze i wylistuj serwery MCP:

```powershell
claude
```

Potem w sesji:

```text
/mcp
```

Powinieneś/aś zobaczyć **second-brain** i jego cztery narzędzia. Jeśli nie, zrestartuj Claude Code (zmiany konfiguracji wymagają świeżego startu).

### Krok 4 — Przetestuj `save_note`

```text
Zapisz notatkę zatytułowaną „Start projektu końcowego" z treścią „Zacząłem
budować agenta Drugiego Mózgu. Ekscytujące." i tagami work i learning.
```

Agent wywołuje `save_note` i **prosi o zatwierdzenie** przed zapisem. Zatwierdź, potem sprawdź `notes\` — powinien być nowy plik `.md` z frontmatter. 🎉

### Krok 5 — Przetestuj pozostałe trzy

```text
Wylistuj wszystkie moje notatki.
```
```text
Przeszukaj notatki pod kątem „mózg".
```
```text
Pokaż mi pełną notatkę „Start projektu końcowego".
```

Obserwuj, jak agent wybiera `list_notes`, `search_notes` i `get_note` — właściwe narzędzie za każdym razem, bo Twoje docstringi powiedziały mu, kiedy którego użyć.

### Krok 6 — Napraw zły wybór narzędzia (jeśli jest)

Jeśli agent sięga po złe narzędzie, to problem **docstringa**, nie kodu. Dociśnij linię „use when…" w `brain_server.py`, zrestartuj i spróbuj ponownie — dokładnie pętla inżynierii-promptów-na-kodzie z Lekcji 4.

---

## 🧩 Podłącz i zweryfikuj

| Krok | Jak |
|------|-----|
| Zarejestruj | `claude mcp add …` lub `.mcp.json` |
| Zweryfikuj | `/mcp` pokazuje `second-brain` + 4 narzędzia |
| Test zapisu | „Zapisz notatkę zatytułowaną…" → zatwierdź |
| Test odczytu | „Wylistuj / przeszukaj / pokaż" notatki |
| Napraw wybór | Dociśnij docstring narzędzia, zrestartuj |

> ⚠️ Agent **pyta przed zapisem**. Trzymaj ten krok zatwierdzania włączony — tak zostajesz w kontroli własnych notatek.

---

## ✅ Sprawdzian

- [ ] `/mcp` listuje **second-brain** ze wszystkimi czterema narzędziami.
- [ ] `save_note` utworzył prawdziwy plik Markdown w `notes\` (po Twoim zatwierdzeniu).
- [ ] `list_notes`, `search_notes` i `get_note` wszystkie zadziałały.
- [ ] Wiesz, że zły wybór narzędzia naprawia się, edytując **docstring**.

---

## 🎯 Praca domowa

Przechwyć 5–8 prawdziwych notatek, rozmawiając z agentem (pomysły, spotkanie, link, decyzja). Będziesz chciał/a prawdziwej treści w Drugim Mózgu do Skilli i przeglądu tygodniowego w kolejnych lekcjach.

---

## 💡 Najważniejsze wnioski

- Zarejestruj serwer przez **`claude mcp add`** lub commitowalny **`.mcp.json`**; zweryfikuj przez **`/mcp`**.
- Agent **wywołuje Twoje narzędzia i pyta o zatwierdzenie** przed zapisem — zostajesz w kontroli.
- Zły wybór narzędzia to poprawka **docstringa**, nie błąd kodu — dociśnij „use when…" i zrestartuj.

🌐 [English](../../en/lessons/05-connect-and-test-tools.md) · [← Poprzednia](04-zbuduj-serwer-mcp.md) · [Strona projektu](../README.md) · [Dalej: Napisz swoje Skille →](06-napisz-swoje-skille.md)
