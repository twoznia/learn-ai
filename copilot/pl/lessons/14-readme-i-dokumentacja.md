# Lekcja 14 — README i dokumentacja z Copilotem

⏱️ **11 minut** · Poziom: Średni · Wymagania: repo GitHub + Copilot

🌐 [English](../../en/lessons/14-readmes-and-docs.md) · [← Poprzednia](13-automatyczny-przeglad-kodu.md) · [Strona kursu](../README.md) · [Dalej: Copilot na github.com →](15-copilot-na-github-com.md)

---

## 🧠 Teoria (3 min)

**README** to drzwi wejściowe projektu — pierwsza rzecz, którą czytają ludzie (i przyszły Ty). Dobre wyjaśnia **czym** projekt jest, **jak go zainstalować i uruchomić** oraz **jak go używać**. Copilot może naszkicować całość z kodu, potem utrzymywać aktualnym.

Dobra dokumentacja do wygenerowania:

- **README.md** — przegląd, instalacja, użycie, przykłady.
- **Docstringi/komentarze** — w kodzie (Lekcja 6).
- **CONTRIBUTING / przewodniki użycia** — dla większych projektów.

Zysk: Copilot czyta Twój rzeczywisty projekt, więc dokumentacja pasuje do kodu — o ile **przejrzysz** ją pod kątem trafności.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Wygeneruj README

W VS Code z otwartym projektem:

```text
@workspace Write a README.md for this project: a one-line description, features,
installation (Windows/PowerShell), usage with a runnable example, and a project
structure section. Keep it friendly and concise.
```

Zapisz jako `README.md` w korzeniu projektu.

### Krok 2 — Podejrzyj je

Otwórz `README.md` i naciśnij **Ctrl+Shift+V** dla podglądu Markdown. Sprawdź, czy nagłówki, bloki kodu i linki renderują się dobrze.

### Krok 3 — Uczyń przykłady prawdziwymi

Dokumentacja gnije, gdy przykłady są fałszywe. Zapytaj:

```text
Make the usage examples match the actual commands and output of this project.
Verify against the code.
```

Potem **uruchom polecenia sam/a**, by potwierdzić, że działają.

### Krok 4 — Dodaj odznaki i spis treści (opcjonalnie)

```text
Add a short table of contents and a "Requirements" section. Suggest any badges
that make sense (e.g. language, license).
```

### Krok 5 — Trzymaj w synchronizacji

Po zmianie funkcji zaktualizuj dokumentację w tym samym PR:

```text
@workspace I added the --language flag. Update README.md's usage section and
examples to include it. Show the diff.
```

Dokumentacja aktualizowana w **tym samym PR** co kod nigdy się nie rozjeżdża.

### Krok 6 — Dokumentuj na bieżąco

Dla każdej nieoczywistej funkcji wygeneruj docstring (Lekcja 6). Dobrze udokumentowany kod też poprawia generowanie README.

---

## 🧩 Solidne README

| Sekcja | Zawartość |
|---------|----------|
| **Tytuł + jedna linia** | Czym jest, w zdaniu |
| **Funkcje** | Co potrafi |
| **Instalacja** | Dokładne kroki (Windows/PowerShell) |
| **Użycie** | Uruchamialne przykłady + oczekiwany wynik |
| **Struktura** | Kluczowe pliki/foldery |
| **Licencja** | Jak inni mogą go używać |

> ⚠️ Copilot potrafi wymyślić polecenia lub funkcje. **Uruchom przykłady** i zweryfikuj twierdzenia przed commitem dokumentacji.

---

## ✅ Sprawdzian

- [ ] Wygenerowałeś/aś README z Copilotem i podejrzałeś/aś je.
- [ ] Uczyniłeś/aś przykłady zgodnymi z projektem i uruchomiłeś/aś je.
- [ ] Zaktualizowałeś/aś dokumentację po zmianie, w tym samym PR.
- [ ] Twoje README obejmuje instalację, użycie i strukturę.

---

## 🎯 Praca domowa

Napisz (lub wygeneruj ponownie) prawdziwe README dla projektu z Copilotem. Zweryfikuj każde polecenie, uruchamiając je, napraw cokolwiek niedokładnego i zacommituj. Potem zrób małą zmianę funkcji i zaktualizuj README w **tym samym** PR.

---

## 💡 Najważniejsze wnioski

- Copilot szkicuje **README i dokumentację** z Twojego rzeczywistego kodu — ogromny start.
- Dobre README obejmuje **co, instalację, użycie (z prawdziwymi przykładami) i strukturę**.
- **Weryfikuj przykłady, uruchamiając je**, i aktualizuj dokumentację **w tym samym PR** co kod, by się nie rozjechała.

🌐 [English](../../en/lessons/14-readmes-and-docs.md) · [← Poprzednia](13-automatyczny-przeglad-kodu.md) · [Strona kursu](../README.md) · [Dalej: Copilot na github.com →](15-copilot-na-github-com.md)
