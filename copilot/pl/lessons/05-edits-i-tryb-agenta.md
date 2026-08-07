# Lekcja 05 — Copilot Edits i tryb agenta

⏱️ **12 minut** · Poziom: Średni · Wymagania: VS Code + Copilot, folder z kilkoma plikami

🌐 [English](../../en/lessons/05-edits-and-agent-mode.md) · [← Poprzednia](04-dobre-promptowanie-copilota.md) · [Strona kursu](../README.md) · [Dalej: Testy, dokumentacja i refactoring →](06-testy-dokumentacja-refactoring.md)

---

## 🧠 Teoria (4 min)

Czat w linii edytuje **jedno** miejsce. Copilot potrafi też wprowadzać **skoordynowane zmiany w wielu plikach** — do tego służą **Edits** i **tryb agenta**.

- **Tryb Edit** — wybierasz zestaw plików i opisujesz zmianę; Copilot proponuje edycje **we wszystkich** jako zestaw diffów do przeglądu. Akceptujesz lub odrzucasz, plik po pliku.
- **Tryb agenta** — dajesz **cel**, a Copilot decyduje, które pliki zmienić, robi edycje, może uruchamiać zadania (jak testy) i iterować — sprawdzając własną pracę. Ty wciąż zatwierdzasz akcje.

Różnica: tryb Edit jest *kierowany przez Ciebie* w wybranych plikach; tryb agenta jest *kierowany celem* i sam ustala kroki. Oba zostawiają Cię recenzentem.

> Nazwy trybów i dostępność ewoluują. Szukaj **selektora trybu** w panelu Copilot Chat (np. Ask / Edit / Agent). Jeśli Twój się różni, przepływ — opisz zmianę, przejrzyj diffy, zatwierdź — jest ten sam.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Utwórz malutki projekt wieloplikowy

Poproś Copilot Chat:

```text
Create a small project: app.py with a main() that greets the user, and
greetings.py with a function get_greeting(name). Wire them together.
```

Masz teraz dwa powiązane pliki.

### Krok 2 — Przełącz na tryb Edit

W panelu Copilot Chat wybierz tryb **Edit**. **Dodaj** oba pliki do zestawu roboczego (przeciągnij je lub użyj kontrolki dodawania plików).

### Krok 3 — Opisz zmianę między plikami

```text
Add a language parameter (default "en") throughout: get_greeting(name, language)
should support "en" and "pl", and main() should ask the user which language.
```

Copilot proponuje edycje w **obu** plikach. Przejrzyj każdy **diff**, potem **Accept**.

### Krok 4 — Wypróbuj tryb agenta

Przełącz na tryb **Agent** i podaj cel:

```text
Add a simple unit test file for get_greeting covering both languages, then run
the tests and fix anything that fails.
```

Obserwuj, jak tworzy test, uruchamia go i iteruje. **Zatwierdzaj** akcje, o które pyta.

### Krok 5 — Przejrzyj wszystko przed zachowaniem

Otwórz widok **Source Control** (**Ctrl+Shift+G**), by zobaczyć wszystkie zmiany naraz. Nigdy nie akceptuj partii, której nie przejrzałeś/aś.

### Krok 6 — Cofnij w razie potrzeby

Nie podoba się? Użyj **Ctrl+Z** na plik lub (lepiej) polegaj na Git — który ustawiamy w Lekcji 9, by każda zmiana była odwracalna.

---

## 🧩 Ask vs Edit vs Agent

| Tryb | Ty dajesz | Copilot robi | Najlepszy do |
|------|----------|--------------|----------|
| **Ask** | Pytanie | Odpowiada, podpowiada | Zrozumienie, fragmenty |
| **Edit** | Pliki + zmianę | Diffy w tych plikach | Celowane edycje wieloplikowe |
| **Agent** | Cel | Planuje, edytuje, uruchamia, iteruje | Większe zadania, od początku do końca |

> ⚠️ Tryb agenta może uruchamiać polecenia i zmieniać wiele plików. Pracuj w **folderze pod kontrolą Git** i przeglądaj diffy przed commitem.

---

## ✅ Sprawdzian

- [ ] Zrobiłeś/aś dwuplikowy projekt.
- [ ] Użyłeś/aś **trybu Edit**, by zmienić oba pliki z jednej instrukcji.
- [ ] Użyłeś/aś **trybu agenta**, by dodać i uruchomić testy.
- [ ] Przejrzałeś/aś wszystkie zmiany w Source Control przed zachowaniem.

---

## 🎯 Praca domowa

Weź mały projekt i użyj trybu Edit, by zmienić nazwę pojęcia w plikach (np. „user" → „customer"). Potem użyj trybu agenta, by „dodać README opisujące, jak go uruchomić". Przejrzyj każdy diff przed akceptacją.

---

## 💡 Najważniejsze wnioski

- **Tryb Edit** stosuje zmianę w **wybranych plikach** jako diffy do przeglądu.
- **Tryb agenta** bierze **cel**, planuje kroki, edytuje, uruchamia zadania i iteruje — za Twoim zatwierdzeniem.
- Zawsze **przeglądaj diffy** (widok Source Control) i pracuj w folderze **pod kontrolą Git**, by zmiany były odwracalne.

🌐 [English](../../en/lessons/05-edits-and-agent-mode.md) · [← Poprzednia](04-dobre-promptowanie-copilota.md) · [Strona kursu](../README.md) · [Dalej: Testy, dokumentacja i refactoring →](06-testy-dokumentacja-refactoring.md)
