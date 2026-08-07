# Projekt końcowy 02 — Skonfiguruj agenta

⏱️ **15 minut** · Poziom: Projekt końcowy · Wymagania: Windows, konto Claude Pro/Max, Node.js + Python

🌐 [English](../../en/lessons/02-set-up-your-agent.md) · [← Poprzednia](01-przeglad-i-architektura.md) · [Strona projektu](../README.md) · [Dalej: Zaprojektuj Drugi Mózg →](03-zaprojektuj-drugi-mozg.md)

---

## 🧠 Teoria (3 min)

Hostem naszego agenta jest **Claude Code** — agent Anthropic w wierszu poleceń. Kluczowe dla tego projektu: **logujesz się kontem Claude**, więc działa na Twoim **abonamencie Pro/Max**, **bez klucza API i bez rachunku za tokeny**.

Zainstalujemy Claude Code, zalogujemy się, potwierdzimy gotowość Pythona (do serwera MCP w Lekcji 4) i utworzymy folder projektu, który stanie się Twoim Drugim Mózgiem.

> Wolisz **Claude Desktop**? Też potrafi hostować serwery MCP (przez plik konfiguracyjny, jak w Claude zaawansowany Ścieżka E). Ten projekt używa **Claude Code**, bo to prawdziwy agent i trzyma wszystko — serwer, Skille, notatki — w jednym folderze projektu, który wyślesz na GitHub.

---

## 🛠️ Praktyka (11 min)

### Krok 1 — Sprawdź Node.js i Python

W **PowerShell**:

```powershell
node --version
python --version
```

Jeśli któregoś brakuje, zainstaluj (kurs podstawowy omawia oba; lub `winget install OpenJS.NodeJS.LTS` i `winget install Python.Python.3.12`).

### Krok 2 — Zainstaluj Claude Code

```powershell
npm install -g @anthropic-ai/claude-code
```

### Krok 3 — Utwórz folder projektu

```powershell
mkdir $HOME\second-brain
cd $HOME\second-brain
mkdir notes
git init
```

Folder `notes\` będzie trzymał notatki Markdown; `git` daje siatkę bezpieczeństwa (i później dom na GitHubie).

### Krok 4 — Uruchom Claude Code i zaloguj się

```powershell
claude
```

Przy pierwszym uruchomieniu wybierz **zaloguj się kontem Claude** i dokończ w przeglądarce. To używa Twojego **abonamentu Pro/Max** — odrzuć ścieżkę „użyj klucza API" w tym projekcie.

### Krok 5 — Przywitaj się z agentem

W wierszu poleceń spróbuj:

```text
Jakie pliki są w tym folderze? Krótko.
```

Powinien zobaczyć folder `notes\`. Rozmawiasz ze swoim agentem.

### Krok 6 — Zainstaluj MCP SDK (do Lekcji 4)

W osobnym PowerShell (lub terminalu VS Code) zainstaluj teraz pakiet Python MCP, by był gotowy:

```powershell
pip install "mcp[cli]"
```

---

## 🧩 Co właśnie skonfigurowałeś/aś

| Element | Status |
|-------|--------|
| **Claude Code** (agent) | Zainstalowany, zalogowany na abonamencie |
| **Node.js / Python** | Potwierdzone, działają |
| **Folder projektu** + `notes\` | Utworzony, pod git |
| **MCP SDK** | Zainstalowany, gotowy na serwer |

> ⚠️ Jesteś na **abonamencie** — użycie liczy się wobec limitów planu (zob. Claude zaawansowany Ścieżka D). Jasne, skupione sesje utrzymują efektywność.

---

## ✅ Sprawdzian

- [ ] `node --version` i `python --version` obie działają.
- [ ] Claude Code jest zainstalowany i zalogowany **kontem Claude** (bez klucza API).
- [ ] Utworzyłeś/aś `second-brain\` z folderem `notes\` i `git init`.
- [ ] `pip install "mcp[cli]"` się powiodło.

---

## 🎯 Praca domowa

Przeprowadź krótką rozmowę z Claude Code w folderze projektu — poproś o utworzenie pliku testowego w `notes\`, potem usunięcie. Oswój się z zatwierdzaniem jego akcji. Ten nawyk zatwierdzania to Twoja kontrola bezpieczeństwa na cały projekt.

---

## 💡 Najważniejsze wnioski

- **Claude Code** to Twój agent, zalogowany na **abonamencie Pro/Max** — bez klucza API, bez kosztu za tokeny.
- Wszystko mieszka w jednym **folderze projektu** (`second-brain\`) pod **git**.
- **MCP SDK** jest zainstalowany, gotowy do budowy narzędzi.

🌐 [English](../../en/lessons/02-set-up-your-agent.md) · [← Poprzednia](01-przeglad-i-architektura.md) · [Strona projektu](../README.md) · [Dalej: Zaprojektuj Drugi Mózg →](03-zaprojektuj-drugi-mozg.md)
