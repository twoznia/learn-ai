# Lekcja 08 — Rozumowanie krok po kroku

⏱️ **11 minut** · Poziom: Średni · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/08-step-by-step-reasoning.md) · [← Poprzednia](07-role-i-prompty-systemowe.md) · [Strona kursu](../README.md) · [Dalej: Dekompozycja i łańcuchy →](09-dekompozycja-i-lancuchy.md)

---

## 🧠 Teoria (4 min)

W problemach wymagających **rozumowania** — matematyka, logika, wieloetapowe decyzje, staranna analiza — poproszenie modelu, by **przeszedł przez to krok po kroku**, dramatycznie poprawia trafność. Nazywa się to często **chain-of-thought** (łańcuch myśli).

Dlaczego: gdy model próbuje skoczyć wprost do odpowiedzi, może zaangażować się w błędny strzał. Danie mu miejsca na rozumowanie najpierw pozwala „pokazać pracę", złapać własne potknięcia i dojść do lepszej odpowiedzi finalnej.

Jak to wyzwolić:

- „Pomyśl krok po kroku przed odpowiedzią."
- „Przejdź przez to starannie, potem daj finalną odpowiedź."
- „Pokaż rozumowanie, potem jasny wniosek."

Dwie uwagi:
- Nowoczesne modele „rozumujące" mogą robić to wewnętrznie — ale jawne poproszenie wciąż pomaga przy trudnych problemach i pozwala *Tobie* zbadać logikę.
- Przy prostych pytaniach faktycznych krok po kroku to zbędny narzut. Używaj tam, gdzie rozumowanie ma znaczenie.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Zobacz różnicę

Zapytaj wprost:

```text
Koszula kosztuje 40 zł po 20% rabacie. Ile wynosiła cena wyjściowa?
```

Potem poproś o rozumowanie:

```text
Koszula kosztuje 40 zł po 20% rabacie. Pomyśl krok po kroku, potem podaj cenę
wyjściową.
```

Druga jest bardziej prawdopodobnie poprawna przy trudniejszych wersjach — i możesz sprawdzić kroki.

### Krok 2 — Oddziel rozumowanie od odpowiedzi

```text
Najpierw przemyśl kompromisy. Potem, w nowej linii zaczynającej się od
„ODPOWIEDŹ:", podaj jednozdaniową rekomendację.
```

To daje i myślenie, i czysty wniosek.

### Krok 3 — Poproś, by rozważył opcje

Przy decyzjach:

```text
Wypisz 3 najbardziej prawdopodobne opcje, zważ każdą krótko, potem wybierz jedną
i wyjaśnij, czemu bije pozostałe.
```

### Krok 4 — Niech sprawdzi własną pracę

```text
Rozwiąż to, potem zweryfikuj odpowiedź, wstawiając ją z powrotem. Jeśli się nie
zgadza, zrób od nowa.
```

### Krok 5 — Wiedz, kiedy pominąć

Przy „Jaka jest stolica Japonii?" nie potrzebujesz rozumowania. Rezerwuj chain-of-thought na problemy, gdzie szybka błędna odpowiedź jest prawdopodobna.

---

## 🧩 Kiedy prosić o rozumowanie

| Zadanie | Krok po kroku? |
|------|---------------|
| Zagadka matematyczna / logiczna | ✅ Tak |
| Wieloczynnikowa decyzja | ✅ Tak |
| Staranna analiza / diagnoza | ✅ Tak |
| Proste sprawdzenie faktu | ❌ Pomiń |
| Szybkie przepisanie | ❌ Pomiń |

> Chcesz schludny wynik? Poproś, by rozumował **najpierw**, potem dał jasno oznaczoną finalną odpowiedź, którą wyjmiesz.

---

## ✅ Sprawdzian

- [ ] Porównałeś/aś bezpośrednią odpowiedź z krokiem po kroku.
- [ ] Oddzieliłeś/aś rozumowanie od oznaczonej finalnej odpowiedzi.
- [ ] Poprosiłeś/aś model o weryfikację własnego wyniku.
- [ ] Umiesz nazwać zadania, gdzie krok po kroku *nie* jest tego wart.

---

## 🎯 Praca domowa

Weź problem, który normalnie oceniasz na oko (obliczenie, plan, kompromis). Zpromptuj go dwoma sposobami — wprost i „pomyśl krok po kroku, potem odpowiedz". Porównaj trafność i zanotuj, gdzie rozumowanie złapało błąd.

---

## 💡 Najważniejsze wnioski

- Przy zadaniach rozumowania **„pomyśl krok po kroku"** poprawia trafność i pozwala zbadać logikę.
- Proś o rozumowanie **najpierw**, potem **oznaczoną finalną odpowiedź**, którą czysto wyjmiesz.
- Pomiń chain-of-thought przy **prostych faktach** — używaj tam, gdzie szybka błędna odpowiedź jest prawdopodobna.

🌐 [English](../../en/lessons/08-step-by-step-reasoning.md) · [← Poprzednia](07-role-i-prompty-systemowe.md) · [Strona kursu](../README.md) · [Dalej: Dekompozycja i łańcuchy →](09-dekompozycja-i-lancuchy.md)
