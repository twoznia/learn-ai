# Lekcja 12 — Instalacja VS Code + rozszerzenie Claude

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows

🌐 [English](../../en/lessons/12-vscode-setup.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Claude Code CLI →](13-claude-code-cli.md)

---

## 🧠 Teoria (2 min)

**VS Code** (Visual Studio Code) to darmowy, ogromnie popularny edytor kodu od Microsoftu. To tu większość programistów pisze kod — i tu asystenci kodowania AI błyszczą, bo AI może *widzieć Twoje pliki* i pomagać je edytować.

Zainstalujemy VS Code, a potem dodamy **Claude Code**, oficjalne rozszerzenie Anthropic. Umieszcza asystenta kodowania AI bezpośrednio w edytorze, który potrafi czytać, pisać i zmieniać pliki w Twoim projekcie (za Twoją zgodą).

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj VS Code

**Najprościej (winget):** w PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Albo pobierz:** wejdź na **https://code.visualstudio.com**, kliknij **Download for Windows**, uruchom instalator. Na ekranie „Select Additional Tasks” zaznacz opcje **„Add to PATH”** i **„Open with Code”** — ułatwiają życie.

### Krok 2 — Otwórz folder kursu w VS Code

1. Uruchom **VS Code** (Start → wpisz *Code* → Enter).
2. **File → Open Folder…** → wybierz `C:\Users\TwojaNazwa\learn-ai-claude`.
3. W lewym panelu zobaczysz pliki utworzone we wcześniejszych lekcjach. 🎉

### Krok 3 — Poznaj panel rozszerzeń

1. Kliknij ikonę **Extensions** w lewym pasku (cztery kwadraty lub naciśnij **Ctrl+Shift+X**).
2. W polu wyszukiwania wpisz **Python** i zainstaluj oficjalne rozszerzenie **Python** od Microsoftu. Daje ładne kolorowanie kodu i przycisk „Run”.

### Krok 4 — Zainstaluj rozszerzenie Claude Code

1. Nadal w Extensions (**Ctrl+Shift+X**) wyszukaj **Claude Code**.
2. Zainstaluj to opublikowane przez **Anthropic**.
3. Po instalacji poszukaj ikony Claude w pasku bocznym (lub otwórz paletę poleceń przez **Ctrl+Shift+P** i wpisz „Claude”).
4. Zaloguj się, gdy zostaniesz poproszony — możesz użyć konta Claude lub klucza API.

> Rozszerzenie to przyjazna nakładka na **Claude Code**, którego uruchomisz też z terminala w następnej lekcji. Oba używają tego samego silnika.

### Krok 5 — Wypróbuj

1. Otwórz `first_claude.py` z wcześniejszej lekcji.
2. Otwórz panel Claude i zapytaj: *„Wyjaśnij, co robi ten plik, linia po linii, dla początkującego.”*
3. Potem zapytaj: *„Dodaj komentarz nad każdą linią wyjaśniający ją.”* i zatwierdź zmianę.

Patrz, jak edytuje Twój prawdziwy plik. To kodowanie wspomagane AI.

---

## 🗺️ Podstawy VS Code (dodaj do zakładek)

| Akcja | Skrót |
|--------|----------|
| Otwórz folder | Ctrl+K, Ctrl+O |
| Paleta poleceń (zrób cokolwiek) | Ctrl+Shift+P |
| Rozszerzenia | Ctrl+Shift+X |
| Przełącz terminal | Ctrl+` (backtick) |
| Zapisz | Ctrl+S |
| Uruchom plik Python | przycisk ▶ (prawy górny róg) |

> **Wskazówka:** naciśnij **Ctrl+`**, aby otworzyć terminal *wewnątrz* VS Code — to PowerShell, więc wszystkie wcześniejsze komendy działają od razu.

---

## ✅ Sprawdzenie

- [ ] VS Code jest zainstalowany i otworzył folder kursu.
- [ ] Rozszerzenie Python zainstalowane.
- [ ] Rozszerzenie Claude Code zainstalowane i zalogowane.
- [ ] Claude wyjaśnił (lub zedytował) jeden z Twoich plików.

---

## 🎯 Zadanie

Zapytaj Claude w VS Code: *„Utwórz nowy plik hello.py, który wypisze przyjazne powitanie i dzisiejszy motywacyjny cytat.”* Zatwierdź, potem uruchom przyciskiem ▶.

---

## 💡 Najważniejsze wnioski

- VS Code = darmowy, standardowy edytor; instaluj przez winget lub code.visualstudio.com.
- Dodaj rozszerzenie **Python** i rozszerzenie **Claude Code**.
- AI może czytać i edytować pliki projektu, za Twoją zgodą.
- **Ctrl+`** otwiera terminal wewnątrz edytora.

🌐 [English](../../en/lessons/12-vscode-setup.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Claude Code CLI →](13-claude-code-cli.md)
