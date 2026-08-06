# Lekcja 12 — VS Code + AI (Codex / Copilot)

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows

🌐 [English](../../en/lessons/12-vscode-ai.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Codex CLI →](13-codex-cli.md)

---

## 🧠 Teoria (2 min)

**VS Code** (Visual Studio Code) to darmowy, ogromnie popularny edytor kodu od Microsoftu. Asystenci AI mieszkają w nim i mogą *widzieć Twoje pliki*, aby pomóc pisać i edytować kod.

Dla modeli OpenAI dwie świetne opcje:

- **Codex (OpenAI)** — asystent kodowania OpenAI, dostępny jako rozszerzenie VS Code łączone z Twoim kontem ChatGPT.
- **GitHub Copilot** — programista-partner AI od Microsoftu (napędzany m.in. modelami OpenAI), z darmowym poziomem. Bardzo popularny i przyjazny początkującym.

Każdy działa. Zainstalujemy VS Code, a potem dodamy jeden.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj VS Code

**Najprościej (winget):** w PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Albo pobierz:** wejdź na **https://code.visualstudio.com**, kliknij **Download for Windows**, uruchom instalator. Zaznacz **„Add to PATH”** i **„Open with Code”**.

### Krok 2 — Otwórz folder kursu

1. Uruchom **VS Code** (Start → wpisz *Code* → Enter).
2. **File → Open Folder…** → wybierz `C:\Users\TwojaNazwa\learn-ai-gpt`.
3. W lewym panelu zobaczysz pliki z wcześniejszych lekcji. 🎉

### Krok 3 — Zainstaluj rozszerzenie Python

1. Kliknij **Extensions** (cztery kwadraty lub **Ctrl+Shift+X**).
2. Wyszukaj **Python** i zainstaluj oficjalne od **Microsoftu**.

### Krok 4 — Dodaj asystenta AI

Wybierz jeden:

**Opcja A — Codex (OpenAI):**
1. W Extensions (**Ctrl+Shift+X**) wyszukaj **Codex** (od **OpenAI**).
2. Zainstaluj i **zaloguj się kontem ChatGPT** (lub kluczem API), gdy poprosi.

**Opcja B — GitHub Copilot:**
1. W Extensions wyszukaj **GitHub Copilot**.
2. Zainstaluj i **zaloguj się kontem GitHub**. Włącz darmowy poziom, jeśli zaoferuje.

### Krok 5 — Wypróbuj

1. Otwórz `first_gpt.py` z wcześniejszej lekcji.
2. W czacie/panelu AI zapytaj: *„Wyjaśnij, co robi ten plik, linia po linii, dla początkującego.”*
3. Zacznij pisać nową funkcję i patrz, jak pojawiają się podpowiedzi (naciśnij **Tab**, aby przyjąć).

Masz teraz pomoc AI wewnątrz edytora.

---

## 🗺️ Podstawy VS Code (dodaj do zakładek)

| Akcja | Skrót |
|--------|----------|
| Paleta poleceń (zrób cokolwiek) | Ctrl+Shift+P |
| Rozszerzenia | Ctrl+Shift+X |
| Przełącz terminal | Ctrl+` (backtick) |
| Zapisz | Ctrl+S |
| Uruchom plik Python | przycisk ▶ (prawy górny róg) |
| Przyjmij podpowiedź AI | Tab |

> **Wskazówka:** naciśnij **Ctrl+`**, aby otworzyć terminal *wewnątrz* VS Code — to PowerShell, więc wszystkie wcześniejsze komendy działają.

---

## ✅ Sprawdzenie

- [ ] VS Code jest zainstalowany i otworzył folder kursu.
- [ ] Rozszerzenie Python zainstalowane.
- [ ] Codex lub Copilot zainstalowany i zalogowany.
- [ ] AI wyjaśnił plik lub zasugerował kod.

---

## 🎯 Zadanie

Zapytaj asystenta AI: *„Zaproponuj jedno małe ulepszenie first_gpt.py i pokaż zmieniony kod.”* Przeczytaj propozycję i zdecyduj, czy ją zastosować.

---

## 💡 Najważniejsze wnioski

- VS Code = darmowy, standardowy edytor; instaluj przez winget lub code.visualstudio.com.
- Dodaj rozszerzenie **Python**, potem **Codex** (OpenAI) lub **GitHub Copilot**.
- AI wyjaśnia i sugeruje kod bezpośrednio w edytorze.
- **Ctrl+`** otwiera terminal wewnątrz edytora.

🌐 [English](../../en/lessons/12-vscode-ai.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Codex CLI →](13-codex-cli.md)
