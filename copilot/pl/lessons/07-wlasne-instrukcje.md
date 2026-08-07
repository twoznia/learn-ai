# Lekcja 07 — Własne instrukcje i styl projektu

⏱️ **11 minut** · Poziom: Średni · Wymagania: VS Code + Copilot, folder projektu

🌐 [English](../../en/lessons/07-custom-instructions.md) · [← Poprzednia](06-testy-dokumentacja-refactoring.md) · [Strona kursu](../README.md) · [Dalej: Kontekst, uczestnicy i referencje →](08-kontekst-uczestnicy-referencje.md)

---

## 🧠 Teoria (4 min)

Przepisywanie „użyj pathlib, dodaj type hinty, pisz zwięzłe komentarze" za każdym razem to marnotrawstwo. **Własne instrukcje** pozwalają ustawić stałe reguły raz, a Copilot stosuje je automatycznie.

Głównym mechanizmem jest plik w repo:

```
.github/copilot-instructions.md
```

Copilot **czyta go automatycznie** i przestrzega przy czacie i edycjach w tym projekcie. Umieść tam fakty i konwencje projektu — język, styl, biblioteki, co robić i czego nie — i przestań się powtarzać.

Możesz też ustawić **osobiste** instrukcje w ustawieniach VS Code, które podążają za *Tobą* między projektami. Instrukcje projektu opisują *projekt*; osobiste opisują *Twoje preferencje*.

> Dokładne nazwy plików i ustawienia własnych instrukcji ewoluują (są też warianty na zadanie i pliki „prompt"). Sprawdź bieżącą dokumentację Copilota; idea — **stałe reguły, które Copilot auto-stosuje** — jest stabilna.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Utwórz plik instrukcji

W projekcie utwórz `.github/copilot-instructions.md`:

```powershell
mkdir .github -Force
notepad .github\copilot-instructions.md
```

### Krok 2 — Napisz prawdziwe, użyteczne reguły

```markdown
# Copilot instructions for this project

## About
A small Python utility project. Beginner-friendly, Windows-first.

## Conventions
- Python 3, use type hints and `pathlib` (not `os.path`).
- Keep functions small; write concise docstrings with one example.
- Prefer standard library; ask before adding a dependency.

## Testing
- Use `pytest`. Every new function gets at least one test.

## Don't
- Don't reformat unrelated code.
- Don't include secrets or API keys in code.
```

Zapisz.

### Krok 3 — Zobacz, jak działa

Zacznij świeży czat i poproś Copilota o dodanie funkcji. Powinien teraz używać type hintów i `pathlib` **bez Twojej prośby** — bo przeczytał instrukcje.

### Krok 4 — Dodaj osobiste instrukcje (opcjonalnie)

W ustawieniach VS Code (wyszukaj „Copilot instructions") dodaj preferencje podążające za Tobą wszędzie, np. *„Wyjaśniaj ryzykowne zmiany przed ich wykonaniem; jestem na Windowsie, dawaj komendy PowerShell."*

### Krok 5 — Trzymaj instrukcje zwięzłe i aktualne

- Umieść fakty, których Copilot nie zgadnie (jak uruchomić, konwencje, strefy zakazane).
- Usuwaj cokolwiek nieaktualnego — błędna instrukcja wprowadza w błąd każdą sesję.
- Jest commitowany do repo, więc **bez sekretów**.

### Krok 6 — Pozwól mu pomóc je napisać

```text
Look at this project and draft a copilot-instructions.md capturing its language,
conventions, and how to run and test it. I'll review before saving.
```

---

## 🧩 Które instrukcje gdzie

| Reguła | Umieść w |
|------|-----------|
| Język, styl, biblioteki projektu | `.github/copilot-instructions.md` |
| Jak uruchomić/testować ten projekt | `.github/copilot-instructions.md` |
| „Jestem na Windowsie, bądź zwięzły" | Osobiste (ustawienia VS Code) |
| Reguły jednorazowego zadania | W samym promptcie czatu |

---

## ✅ Sprawdzian

- [ ] Utworzyłeś/aś `.github/copilot-instructions.md` z prawdziwymi konwencjami.
- [ ] Świeża odpowiedź Copilota przestrzegała Twoich reguł bez polecenia.
- [ ] Znasz różnicę: instrukcje projektu vs osobiste.
- [ ] Twoje instrukcje nie zawierają sekretów.

---

## 🎯 Praca domowa

Napisz prawdziwy `copilot-instructions.md` dla projektu, na którym Ci zależy: czym jest, jak go uruchomić/testować, jego konwencje i strefy zakazane. Potem poproś Copilota o zmianę i potwierdź, że honoruje reguły.

---

## 💡 Najważniejsze wnioski

- **`.github/copilot-instructions.md`** ustawia stałe reguły, które Copilot **auto-stosuje** w tym repo.
- Instrukcje **projektu** opisują projekt; **osobiste** opisują Twoje preferencje.
- Trzymaj je **zwięzłe, aktualne, bez sekretów** — i pozwól Copilotowi naszkicować pierwszą wersję do przeglądu.

🌐 [English](../../en/lessons/07-custom-instructions.md) · [← Poprzednia](06-testy-dokumentacja-refactoring.md) · [Strona kursu](../README.md) · [Dalej: Kontekst, uczestnicy i referencje →](08-kontekst-uczestnicy-referencje.md)
