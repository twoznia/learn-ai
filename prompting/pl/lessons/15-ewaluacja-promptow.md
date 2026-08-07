# Lekcja 15 — Ewaluacja i testowanie promptów

⏱️ **11 minut** · Poziom: Zaawansowany · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/15-evaluating-prompts.md) · [← Poprzednia](14-biblioteka-wzorcow-promptow.md) · [Strona kursu](../README.md) · [Dalej: Bezpieczeństwo i podsumowanie →](16-bezpieczenstwo-i-podsumowanie.md)

---

## 🧠 Teoria (4 min)

„Wydaje się dobre" to nie miara. Jeśli polegasz na promptcie — zwłaszcza wielokrotnego użytku — powinieneś umieć powiedzieć **dlaczego** jest dobry i **czy** zmiana go ulepszyła. To **ewaluacja** promptu.

Podstawy, zapożyczone od tego, jak inżynierowie testują cokolwiek:

- **Najpierw zdefiniuj sukces.** Co zawiera dobra odpowiedź? Napisz kryteria *przed* oceną.
- **Testuj na kilku wejściach.** Prompt działający na jednym przykładzie może zawieść na innych. Wypróbuj łatwe, trudne i brzegowe.
- **Porównuj uczciwie (A/B).** Zmień **jedną rzecz** między dwiema wersjami i uruchom obie na tych samych wejściach.
- **Obserwuj spójność.** Uruchom ten sam prompt kilka razy — utrzymuje się, czy to szczęśliwy jednorazowy strzał?

Nie potrzebujesz wymyślnych narzędzi — rubryka i garść przypadków testowych bije przeczucie.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Napisz rubrykę sukcesu

Przed oceną wyników zdefiniuj „dobre":

```text
Dobre podsumowanie: (1) ≤5 punktów, (2) pokrywa wszystkie kluczowe punkty,
(3) bez wymyślonych faktów, (4) czytelne dla nie-eksperta.
```

### Krok 2 — Zrób mały zestaw testowy

Wybierz 3–5 reprezentatywnych wejść — w tym trudne i brzegowe. Zapisz je z promptem.

### Krok 3 — Uruchom test A/B

Wersja A vs Wersja B (jedna zmiana — powiedzmy dodanie przykładu). Uruchom obie na każdym wejściu testowym i oceń wobec rubryki. Zachowaj zwycięzcę.

### Krok 4 — Sprawdź spójność

```text
Uruchom ten sam prompt na tym samym wejściu 3 razy.
```

Jeśli wyniki mocno się wahają, dociśnij prompt (więcej struktury, przykładów, ograniczeń).

### Krok 5 — Niech model pomoże oceniać

Dla subiektywnego wyniku użyj sprawdzenia opartego na rubryce („LLM jako sędzia"):

```text
Oceń tę odpowiedź 1–5 na każdym kryterium rubryki i uzasadnij każdą ocenę.
```

Używaj jako *sygnału*, nie ostatniego słowa — sprawdzaj sam/a wyrywkowo.

### Krok 6 — Zapisuj, co wygrywa

W `my-prompts.md` zanotuj, która wersja wygrała i dlaczego. Twoja biblioteka mierzalnie się poprawia z czasem.

---

## 🧩 Lekka pętla ewaluacji

| Krok | Zrób |
|------|-----|
| 1. Kryteria | Zdefiniuj „dobre" przed oceną |
| 2. Zestaw testowy | 3–5 wejść w tym trudne/brzegowe |
| 3. A/B | Zmień jedną rzecz, uruchom obie |
| 4. Spójność | Powtórz; wypatruj wahań |
| 5. Sędzia | Ocena wg rubryki (Ty + model) |
| 6. Zapisz | Zanotuj zwycięzcę i dlaczego |

---

## ✅ Sprawdzian

- [ ] Napisałeś/aś kryteria sukcesu przed oceną wyników.
- [ ] Zbudowałeś/aś mały zestaw testowy z przypadkiem trudnym/brzegowym.
- [ ] Przetestowałeś/aś A/B dwie wersje na tych samych wejściach.
- [ ] Sprawdziłeś/aś spójność w powtarzanych uruchomieniach.

---

## 🎯 Praca domowa

Weź najczęściej używany wzorzec. Napisz rubrykę, wybierz 4 wejścia testowe i przetestuj A/B dwa warianty (zmień jedną rzecz). Oceń oba, zachowaj zwycięzcę i zapisz wynik w bibliotece. Właśnie uczyniłeś/aś prompt dowodliwie lepszym.

---

## 💡 Najważniejsze wnioski

- Ewaluuj prompty z **kryteriami zdefiniowanymi najpierw**, **małym zestawem testowym** i porównaniami **A/B z jedną zmianą**.
- Sprawdzaj **spójność** w powtarzanych uruchomieniach; dociskaj prompty, które się wahają.
- Używaj **oceny wg rubryki** (Ty + model jako sygnał) i **zapisuj zwycięzców**.

🌐 [English](../../en/lessons/15-evaluating-prompts.md) · [← Poprzednia](14-biblioteka-wzorcow-promptow.md) · [Strona kursu](../README.md) · [Dalej: Bezpieczeństwo i podsumowanie →](16-bezpieczenstwo-i-podsumowanie.md)
