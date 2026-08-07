# Lekcja 04 — Dobre promptowanie Copilota

⏱️ **11 minut** · Poziom: Początkujący → Średni · Wymagania: VS Code + Copilot

🌐 [English](../../en/lessons/04-prompting-copilot-well.md) · [← Poprzednia](03-podstawy-copilot-chat.md) · [Strona kursu](../README.md) · [Dalej: Edits i tryb agenta →](05-edits-i-tryb-agenta.md)

---

## 🧠 Teoria (4 min)

Copilot jest tak dobry, jak **kontekst i instrukcje**, które mu dajesz. Najważniejsza umiejętność to **bycie konkretnym** — co chcesz, jakie ograniczenia i jaki kształt odpowiedzi.

Trzy dźwignie kontrolują jakość podpowiedzi:

1. **Kontekst** — które pliki są otwarte, co zaznaczyłeś/aś i do czego się odwołujesz. Copilot czyta Twój otwarty edytor i projekt.
2. **Intencja** — jasny komentarz lub instrukcja czatu („napisz X, które robi Y, obsługując Z").
3. **Ograniczenia** — język, styl, biblioteki do użycia lub unikania, przypadki brzegowe.

Niejasna prośba daje ogólny strzał; precyzyjna prośba daje użyteczny kod.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Porównaj niejasne vs konkretne

W czacie zapytaj wersję niejasną:

```text
Write a function to process a file.
```

Potem wersję konkretną:

```text
Write a Python function read_csv_totals(path) that reads a CSV with columns
"region" and "amount", returns a dict of total amount per region, and raises
FileNotFoundError with a clear message if the file is missing.
```

Zauważ, o ile bardziej użyteczna jest druga odpowiedź.

### Krok 2 — Daj kontekst, otwierając właściwe pliki

Copilot używa Twojego **otwartego edytora**. Zanim zapytasz „dodaj funkcję jak inne", otwórz plik, który je ma — by Copilot dopasował ich styl.

### Krok 3 — Steruj uzupełnieniami komentarzami

W pliku precyzyjny komentarz steruje ghost-textem:

```python
# Convert a temperature in Celsius to Fahrenheit, rounded to 1 decimal place
def c_to_f(celsius):
```

### Krok 4 — Poproś o kształt, jakiego chcesz

Powiedz Copilotowi format:

```text
Refactor this into smaller functions. Show only the changed code, and add a
one-line comment above each new function.
```

### Krok 5 — Iteruj, nie zaczynaj od nowa

Jeśli odpowiedź jest blisko, dopracuj w tym samym czacie:

```text
Good, but use pathlib instead of os.path, and add a type hint on the return value.
```

### Krok 6 — Podawaj przykłady

Do trudnych formatów pokaż przykładowe wejście i oczekiwane wyjście. Copilot dobrze naśladuje wzorce:

```text
Given input "2026-08-07" return "Aug 7, 2026". Write a function that does this.
```

---

## 🧩 Lista kontrolna jakości promptu

| Zawrzyj | Przykład |
|---------|---------|
| **Co** | „funkcja parsująca CSV" |
| **Wejścia/wyjścia** | „bierze ścieżkę, zwraca słownik" |
| **Ograniczenia** | „użyj pathlib; obsłuż brakujący plik" |
| **Styl/kształt** | „małe funkcje, type hinty" |
| **Przykład** | „wejście X → wyjście Y" |

> ⚠️ Zawsze **czytaj** wygenerowany kod przed akceptacją. Copilot potrafi być pewnie w błędzie — to Ty jesteś recenzentem.

---

## ✅ Sprawdzian

- [ ] Zobaczyłeś/aś różnicę między niejasnym a konkretnym promptem.
- [ ] Otworzyłeś/aś istotne pliki, by dać Copilotowi kontekst.
- [ ] Sterowałeś/aś uzupełnieniem precyzyjnym komentarzem.
- [ ] Iterowałeś/aś odpowiedź zamiast zaczynać od nowa.

---

## 🎯 Praca domowa

Weź prawdziwe zadanie (parsowanie, formatowanie, mała funkcja pomocnicza). Napisz je raz z niejasnym promptem i raz z w pełni określonym, zawierającym wejścia, ograniczenia i przykład. Porównaj wyniki i zanotuj, co zrobiło różnicę.

---

## 💡 Najważniejsze wnioski

- Jakość wynika z **kontekstu + jasnej intencji + ograniczeń** — bądź konkretny.
- Copilot czyta Twoje **otwarte pliki i zaznaczenie**; otwórz właściwe przed pytaniem.
- **Iteruj** w tej samej rozmowie, dawaj **przykłady** i zawsze **przeglądaj** wynik.

🌐 [English](../../en/lessons/04-prompting-copilot-well.md) · [← Poprzednia](03-podstawy-copilot-chat.md) · [Strona kursu](../README.md) · [Dalej: Edits i tryb agenta →](05-edits-i-tryb-agenta.md)
