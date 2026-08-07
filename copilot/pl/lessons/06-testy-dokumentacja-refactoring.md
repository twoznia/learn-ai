# Lekcja 06 — Testy, dokumentacja i refactoring z Copilotem

⏱️ **11 minut** · Poziom: Średni · Wymagania: VS Code + Copilot

🌐 [English](../../en/lessons/06-tests-docs-refactoring.md) · [← Poprzednia](05-edits-i-tryb-agenta.md) · [Strona kursu](../README.md) · [Dalej: Własne instrukcje →](07-wlasne-instrukcje.md)

---

## 🧠 Teoria (3 min)

Trzy codzienne zadania, gdzie Copilot oszczędza najwięcej czasu — i gdzie **musisz przeglądać starannie**:

- **Testy** — Copilot szybko pisze testy jednostkowe, w tym przypadki brzegowe, o których byś zapomniał/a. Testy to też świetna siatka bezpieczeństwa dla kodu generowanego przez AI.
- **Dokumentacja** — docstringi, komentarze i README z samego kodu.
- **Refactoring** — restrukturyzacja kodu bez zmiany zachowania (mniejsze funkcje, lepsze nazwy, mniej powtórzeń).

Motyw: Copilot szkicuje, **Ty weryfikujesz** — zwłaszcza że testy faktycznie testują właściwą rzecz, a refactory nie zmieniają zachowania.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Wygeneruj testy

Otwórz plik z funkcją (użyj ponownie `greetings.py` lub `demo.py`). Zaznacz funkcję i:

```text
/tests
```

Lub zapytaj konkretnie:

```text
Write pytest tests for get_greeting covering: normal name, empty string,
and an unsupported language. Use clear test names.
```

### Krok 2 — Uruchom je

W terminalu VS Code (**Ctrl+`**):

```powershell
pip install pytest
pytest
```

Napraw niepowodzenia przez `/fix` — ale najpierw **sprawdź, czy test jest poprawny**, nie tylko kod.

### Krok 3 — Dodaj dokumentację

Zaznacz funkcję i:

```text
/doc
```

Lub: „Dodaj docstring wyjaśniający parametry, wartość zwracaną i jeden przykład użycia."

### Krok 4 — Refactoruj bezpiecznie

```text
Refactor this file into smaller functions with clear names. Do NOT change
behavior. List what you changed and why.
```

Potem **uruchom testy ponownie** — zielone testy to dowód, że zachowanie się nie zmieniło.

### Krok 5 — Popraw nazwy i usuń powtórzenia

```text
Find duplicated logic in these files and extract it into a shared helper.
Show the diff.
```

### Krok 6 — Wyjaśnij stary kod

Odziedziczyłeś/aś zabałaganiony plik? Otwórz go i zapytaj:

```text
Explain what this file does, note anything risky, and suggest 3 small,
safe improvements — don't apply them yet.
```

---

## 🧩 Copilot do pracy nad jakością

| Zadanie | Początek promptu |
|------|----------------|
| Testy | „/tests" lub „napisz testy pytest pokrywające…" |
| Dokumentacja | „/doc" lub „dodaj docstring z przykładem" |
| Refactor | „refactoruj w mniejsze funkcje, bez zmiany zachowania" |
| Nazwy | „zaproponuj jaśniejsze nazwy tych zmiennych" |
| Zrozumienie | „wyjaśnij ten plik i jego ryzyka" |

> ⚠️ Testy pisane przez AI mogą przechodzić, testując niewłaściwą rzecz. Czytaj **asercje** każdego testu — czy pasują do tego, co kod *powinien* robić?

---

## ✅ Sprawdzian

- [ ] Wygenerowałeś/aś i uruchomiłeś/aś testy, i przechodzą.
- [ ] Dodałeś/aś docstring przez `/doc` lub prompt.
- [ ] Zrefaktoryzowałeś/aś plik i potwierdziłeś/aś, że testy wciąż przechodzą.
- [ ] Kazałeś/aś Copilotowi wyjaśnić plik i jego ryzyka.

---

## 🎯 Praca domowa

Wybierz funkcję napisaną wcześniej. Wygeneruj testy (celuj w 3+ przypadki, w tym brzegowy), uruchom je, potem zrefaktoryzuj funkcję w mniejsze części i potwierdź, że testy wciąż przechodzą. Ta pętla testuj-potem-refactoruj to nawyk profesjonalisty.

---

## 💡 Najważniejsze wnioski

- Copilot szybko szkicuje **testy, dokumentację i refactory** — ogromna oszczędność czasu.
- **Testy to Twoja siatka bezpieczeństwa** dla kodu AI — ale zweryfikuj, że ich asercje są poprawne.
- Refactoruj z „**bez zmiany zachowania**", potem **uruchom testy ponownie**, by to udowodnić.

🌐 [English](../../en/lessons/06-tests-docs-refactoring.md) · [← Poprzednia](05-edits-i-tryb-agenta.md) · [Strona kursu](../README.md) · [Dalej: Własne instrukcje →](07-wlasne-instrukcje.md)
