# Projekt końcowy 07 — Uruchom agenta od początku do końca

⏱️ **15 minut** · Poziom: Projekt końcowy · Wymagania: działające narzędzia + Skille (Lekcja 6), trochę prawdziwych notatek

🌐 [English](../../en/lessons/07-run-the-agent.md) · [← Poprzednia](06-napisz-swoje-skille.md) · [Strona projektu](../README.md) · [Dalej: Testuj, utwardź i wydaj →](08-testuj-utwardz-i-wydaj.md)

---

## 🧠 Teoria (3 min)

Wszystko podłączone: agent, narzędzia, Skille i notatki. Teraz **używasz tego jak prawdziwego produktu**. Trzy główne przepływy pokazują całość działającą razem:

1. **Przechwytywanie** — mówisz, a ono zapisuje dobrze uformowane notatki (narzędzia + Skill note-style).
2. **Przypominanie** — pytasz i dostajesz odpowiedzi **osadzone w Twoich notatkach**, z zacytowaną notatką źródłową (nawyk anty-halucynacyjny z kursu Inżynierii promptów).
3. **Przegląd** — uruchamiasz przegląd tygodniowy i dostajesz motywy, otwarte pętle i priorytety.

Ta lekcja to nagroda: Twój Drugi Mózg, działający od początku do końca.

---

## 🛠️ Praktyka (11 min)

### Krok 1 — Przechwytuj naturalnie

Po prostu mów do niego:

```text
Zapisz to: pomysł na aplikację — „tryb skupienia", który ukrywa wszystkie
notatki poza dzisiejszymi. Może dobrze współgrać z przeglądem tygodniowym.
```

Agent nadaje tytuł, taguje (`idea`) i zapisuje. Przechwytuj, ile chcesz — teraz jest bez tarcia.

### Krok 2 — Przypominaj, osadzone

Zadaj prawdziwe pytanie:

```text
Jakie pomysły zapisałem o aplikacji? Odpowiedz tylko z moich notatek i nazwij
notatkę, z której pochodzi każdy punkt. Jeśli tego nie ma w notatkach, powiedz.
```

To „**tylko z moich notatek, nazwij notatkę**" to osadzanie — trzyma agenta uczciwym i zamienia Twoje notatki w godną zaufania bazę wiedzy.

### Krok 3 — Połącz kropki

Agent potrafi syntezować między notatkami:

```text
Przeszukaj notatki i powiedz mi: jakie mam otwarte TODO, pogrupowane wg tagu?
```

Używa `search_notes`/`list_notes` i wyciąga linie `TODO:`, które zostawiałeś/aś — wartość, jakiej same płaskie pliki by nie dały.

### Krok 4 — Uruchom przegląd tygodniowy

```text
Zrób mój przegląd tygodniowy.
```

**Skill weekly-review** ładuje się i uruchamia Twój przepływ: zbierz notatki → motywy → otwarte pętle → 3 priorytety → zaproponuj zapisanie podsumowania. Zatwierdź zapis, a stanie się też notatką.

### Krok 5 — Trzymaj osadzenie

Jeśli odpowiedź kiedyś wydaje się wymyślona, dodaj barierę:

```text
Odpowiedz ponownie, używając tylko tego, co faktycznie jest w moich notatkach.
Zacytuj dokładne linie, których użyłeś.
```

Jeśli nie potrafi zacytować notatki, twierdzenie naprawdę nie było Twoje — dokładnie to, co chcesz złapać.

### Krok 6 — Uczyń to pętlą nawyku

Masz teraz dzienną pętlę: **przechwytuj w ciągu dnia → przypominaj, gdy potrzebujesz → przeglądaj co tydzień.** Ta pętla zamienia stos plików w prawdziwy Drugi Mózg.

---

## 🧩 Trzy przepływy

| Przepływ | Mówisz | Używa |
|----------|---------|------|
| **Przechwytywanie** | „Zapisz to…" | `save_note` + Skill note-style |
| **Przypominanie** | „Co zanotowałem o X? (tylko z notatek)" | `search_notes` / `get_note` |
| **Przegląd** | „Zrób mój przegląd tygodniowy" | Skill weekly-review + narzędzia |

> ⚠️ Przy przypominaniu zawsze trzymaj ramę **„tylko z moich notatek"**. To różnica między godnym zaufania Drugim Mózgiem a pewnym siebie zgadywaczem.

---

## ✅ Sprawdzian

- [ ] Przechwyciłeś/aś notatki, po prostu mówiąc; wyszły dobrze uformowane.
- [ ] Dostałeś/aś **osadzoną** odpowiedź, która nazwała swoje notatki źródłowe.
- [ ] Agent wyciągnął Twoje otwarte TODO z wielu notatek.
- [ ] Przegląd tygodniowy uruchomił pełny przepływ i zaproponował zapisanie podsumowania.

---

## 🎯 Praca domowa

Użyj Drugiego Mózgu przez jeden prawdziwy dzień: przechwytuj wszystko przez agenta, potem zadaj mu dwa osadzone pytania i uruchom przegląd tygodniowy na koniec. Zauważ, co wydobył, o czym zapomniałeś/aś — o to właśnie chodzi.

---

## 💡 Najważniejsze wnioski

- Twój agent robi trzy prawdziwe przepływy: **przechwytywanie**, **osadzone przypominanie** i **przegląd tygodniowy** — narzędzia i Skille razem.
- **Osadzanie** („tylko z moich notatek, nazwij źródło") to, co czyni przypominanie godnym zaufania.
- Dzienna pętla **przechwytuj → przypominaj → przeglądaj** to, co czyni z tego prawdziwy Drugi Mózg.

🌐 [English](../../en/lessons/07-run-the-agent.md) · [← Poprzednia](06-napisz-swoje-skille.md) · [Strona projektu](../README.md) · [Dalej: Testuj, utwardź i wydaj →](08-testuj-utwardz-i-wydaj.md)
