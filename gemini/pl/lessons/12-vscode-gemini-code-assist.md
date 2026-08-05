# Lekcja 12 — VS Code + Gemini Code Assist

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows, konto Google

🌐 [English](../../en/lessons/12-vscode-gemini-code-assist.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Gemini CLI →](13-gemini-cli.md)

---

## 🧠 Teoria (2 min)

**VS Code** (Visual Studio Code) to darmowy, ogromnie popularny edytor kodu od Microsoftu. **Gemini Code Assist** to rozszerzenie AI od Google do niego: wyjaśnia kod, sugeruje uzupełnienia i odpowiada na pytania w panelu czatu — z **darmowym poziomem** dla osób prywatnych.

Zainstalujemy VS Code, a potem dodamy Gemini Code Assist, aby mieć pomoc AI tam, gdzie piszesz kod.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj VS Code

**Najprościej (winget):** w PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Albo pobierz:** wejdź na **https://code.visualstudio.com**, kliknij **Download for Windows**, uruchom instalator. Zaznacz **„Add to PATH”** i **„Open with Code”** na ekranie zadań.

### Krok 2 — Otwórz folder kursu

1. Uruchom **VS Code** (Start → wpisz *Code* → Enter).
2. **File → Open Folder…** → wybierz `C:\Users\TwojaNazwa\learn-ai-gemini`.
3. W lewym panelu zobaczysz pliki z wcześniejszych lekcji. 🎉

### Krok 3 — Zainstaluj rozszerzenie Python

1. Kliknij **Extensions** (cztery kwadraty lub **Ctrl+Shift+X**).
2. Wyszukaj **Python** i zainstaluj oficjalne od **Microsoftu** (ładne kolory + przycisk Run).

### Krok 4 — Zainstaluj Gemini Code Assist

1. Nadal w Extensions (**Ctrl+Shift+X**) wyszukaj **Gemini Code Assist**.
2. Zainstaluj to opublikowane przez **Google**.
3. Kliknij **ikonę Gemini** w lewym pasku i **zaloguj się kontem Google**, gdy zostaniesz poproszony. Wybierz darmową opcję dla osób prywatnych, jeśli zapyta.

### Krok 5 — Wypróbuj

1. Otwórz `first_gemini.py` z wcześniejszej lekcji.
2. W czacie Gemini Code Assist zapytaj: *„Wyjaśnij, co robi ten plik, linia po linii, dla początkującego.”*
3. Ustaw kursor w pliku i poproś o *„dodanie komentarza nad każdą linią wyjaśniającego ją.”*

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

> **Wskazówka:** naciśnij **Ctrl+`**, aby otworzyć terminal *wewnątrz* VS Code — to PowerShell, więc wszystkie wcześniejsze komendy działają.

---

## ✅ Sprawdzenie

- [ ] VS Code jest zainstalowany i otworzył folder kursu.
- [ ] Rozszerzenie Python zainstalowane.
- [ ] Gemini Code Assist zainstalowane i zalogowane.
- [ ] Gemini wyjaśnił jeden z Twoich plików.

---

## 🎯 Zadanie

Zapytaj Gemini Code Assist: *„Zaproponuj jedno małe ulepszenie first_gemini.py i pokaż zmieniony kod.”* Przeczytaj propozycję i zdecyduj, czy ją zastosować.

---

## 💡 Najważniejsze wnioski

- VS Code = darmowy, standardowy edytor; instaluj przez winget lub code.visualstudio.com.
- Dodaj rozszerzenie **Python** i **Gemini Code Assist** (darmowy poziom dla osób prywatnych).
- AI wyjaśnia i sugeruje kod bezpośrednio w edytorze.
- **Ctrl+`** otwiera terminal wewnątrz edytora.

🌐 [English](../../en/lessons/12-vscode-gemini-code-assist.md) · [← Wstecz](11-powershell.md) · [Strona kursu](../README.md) · [Dalej: Gemini CLI →](13-gemini-cli.md)
