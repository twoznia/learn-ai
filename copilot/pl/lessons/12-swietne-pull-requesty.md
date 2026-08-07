# Lekcja 12 — Świetne pull requesty z Copilotem

⏱️ **12 minut** · Poziom: Średni · Wymagania: repo GitHub + Copilot

🌐 [English](../../en/lessons/12-great-pull-requests.md) · [← Poprzednia](11-zgloszenia-etykiety-projekty.md) · [Strona kursu](../README.md) · [Dalej: Automatyczny przegląd kodu →](13-automatyczny-przeglad-kodu.md)

---

## 🧠 Teoria (4 min)

Świetny PR jest **łatwy do przeglądu**: jasny tytuł, opis wyjaśniający *co* i *dlaczego*, rozsądny rozmiar i dobre komunikaty commitów. Copilot pomaga w każdej części — zamienia „oto diff, powodzenia" w PR, który recenzent szybko zatwierdzi.

Co czyni PR łatwym do przeglądu:

- **Mały i skupiony** — jedna logiczna zmiana, nie dziesięć.
- **Tytuł podsumowujący zmianę** (nie „aktualizacje" czy „poprawki").
- **Opis**: co się zmieniło, dlaczego, jak testować i wszelkie ryzyka.
- **Czyste commity** z sensownymi komunikatami.

Copilot może napisać komunikaty commitów, wygenerować **podsumowanie/opis** PR, a nawet zaproponować dobry tytuł.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Pozwól Copilotowi napisać komunikat commita

W panelu **Source Control** VS Code umieść zmiany w staging. Poszukaj ikony **gwiazdki / Copilota** przy polu komunikatu — kliknij, by **wygenerować komunikat commita** z diffa. Edytuj w razie potrzeby, potem zacommituj.

### Krok 2 — Trzymaj PR skupionym

Przed otwarciem PR zapytaj:

```text
@workspace Look at my changes on this branch. Are they one focused change, or
should this be split into separate PRs? Be specific.
```

### Krok 3 — Wygeneruj opis PR

Otwórz PR (github.com lub rozszerzenie **GitHub Pull Requests** w VS Code). Na github.com pole opisu często ma opcję **Copilot „Summary"**, która szkicuje opis z diffa. Lub zapytaj Copilot Chat:

```text
Write a pull request description for these changes: a "What" section, a "Why"
section, a "How to test" checklist, and any risks. Keep it concise.
```

### Krok 4 — Napisz mocny tytuł

```text
Suggest 3 clear, specific PR titles for this change, under 70 characters each.
```

Wybierz ten, który najlepiej podsumowuje zmianę.

### Krok 5 — Dodaj sekcję „jak testować"

Recenzenci to uwielbiają. Zawrzyj dokładne polecenia:

```text
Add a "How to test" section with the exact PowerShell commands to run and what
the expected output is.
```

### Krok 6 — Połącz zgłoszenie

W opisie napisz **„Closes #1"**, by zgłoszenie zamknęło się automatycznie po scaleniu — łącząc pracę z planem z Lekcji 11.

---

## 🧩 Anatomia PR-a do przeglądu

| Część | Dobra wersja |
|------|--------------|
| **Tytuł** | „Add --language flag to CLI (en/pl)" |
| **Co** | Jednoakapitowe podsumowanie zmiany |
| **Dlaczego** | Problem, który rozwiązuje / link do zgłoszenia |
| **Jak testować** | Dokładne polecenia + oczekiwany wynik |
| **Ryzyka** | Cokolwiek, co recenzenci powinni zbadać |
| **Commity** | Małe, z sensownymi komunikatami |

> ⚠️ Copilot szkicuje opis z diffa — **przeczytaj i popraw go**. Opisuje *co się zmieniło*, ale tylko *Ty* znasz pełne *dlaczego*.

---

## ✅ Sprawdzian

- [ ] Wygenerowałeś/aś komunikat commita z Copilotem.
- [ ] Sprawdziłeś/aś, czy PR należy podzielić.
- [ ] Wygenerowałeś/aś opis PR (Co / Dlaczego / Jak testować / Ryzyka).
- [ ] Połączyłeś/aś zgłoszenie przez „Closes #N".

---

## 🎯 Praca domowa

Otwórz prawdziwy PR dla zmiany na repo. Użyj Copilota do wygenerowania komunikatu commita i pełnego opisu, napisz mocny tytuł i dodaj sekcję „jak testować". Zapytaj kolegę (lub przeczytaj to jutro ponownie) — czy mógłby przejrzeć bez pytań?

---

## 💡 Najważniejsze wnioski

- Świetne PR-y są **małe, jasno zatytułowane i dobrze opisane** (co / dlaczego / jak testować / ryzyka).
- Copilot generuje **komunikaty commitów, opisy PR i tytuły** z Twojego diffa.
- Zawsze **przeglądaj szkic Copilota** — zna *co*, Ty dostarczasz *dlaczego* — i łącz zgłoszenia przez **„Closes #N"**.

🌐 [English](../../en/lessons/12-great-pull-requests.md) · [← Poprzednia](11-zgloszenia-etykiety-projekty.md) · [Strona kursu](../README.md) · [Dalej: Automatyczny przegląd kodu →](13-automatyczny-przeglad-kodu.md)
