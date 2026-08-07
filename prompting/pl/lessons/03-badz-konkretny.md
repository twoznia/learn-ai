# Lekcja 03 — Bądź konkretny: klarowność i precyzja

⏱️ **11 minut** · Poziom: Początkujący · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/03-be-specific.md) · [← Poprzednia](02-anatomia-promptu.md) · [Strona kursu](../README.md) · [Dalej: Kontekst i okno kontekstowe →](04-kontekst-i-okno-kontekstowe.md)

---

## 🧠 Teoria (4 min)

Najczęstszy błąd promptowania to **niejasność**. AI nie czyta w myślach, więc dwuznaczność wypełnia się *przeciętnym strzałem* modelu — rzadko tym, co miałeś/aś na myśli.

Trzy nawyki naprawiają większość niejasności:

1. **Powiedz dokładnie, czego chcesz** — wynik, nie wskazówkę ku niemu. „Daj mi 5 tematów maila" bije „pomóż z mailem".
2. **Usuń dwuznaczne słowa** — „dobry", „krótki", „kilka", „lepszy" nic precyzyjnie nie znaczą. Zastąp liczbami i kryteriami: „poniżej 60 znaków", „3 opcje", „bardziej formalny niż szkic".
3. **Nazwij niewypowiedziane założenia** — odbiorca, cel, język, czego unikać. Jeśli to dla Ciebie ważne, powiedz.

Konkretność to nie dłuższe prompty — to **usuwanie miejsca na błędne zgadywanie**.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Zabij niejasne słowa

Niejasne:

```text
Popraw ten e-mail i skróć go.
```

Precyzyjne:

```text
Przepisz ten e-mail poniżej 90 słów, uprzejmiej i z jednym jasnym wezwaniem do
działania w ostatniej linii. Nie zmieniaj daty spotkania.
```

### Krok 2 — Zastąp przymiotniki kryteriami

Zamiast „uczyń to angażującym", powiedz, co angażujące znaczy *tutaj*:

```text
Zacznij zaskakującą statystyką, używaj „Ty" i trzymaj zdania poniżej 20 słów.
```

### Krok 3 — Nazwij odbiorcę i cel

```text
To dla nietechnicznych dyrektorów decydujących o finansowaniu projektu.
Skup się na wpływie i koszcie, nie na wdrożeniu.
```

### Krok 4 — Dodaj ograniczenia negatywne

Powiedz, czego **nie** robić:

```text
Nie używaj sloganów, nie wymyślaj liczb i nie przekraczaj jednego akapitu.
```

### Krok 5 — Przetestuj prompt na obcym

Przeczytaj prompt, jakbyś nic nie wiedział/a. Czy mógłbyś/mogłabyś wytworzyć złą-ale-technicznie-poprawną odpowiedź? Jeśli tak, dociśnij.

---

## 🧩 Zamiany niejasne → precyzyjne

| Niejasne | Precyzyjne |
|-------|---------|
| „krótki" | „poniżej 100 słów" |
| „kilka przykładów" | „dokładnie 3 przykłady" |
| „popraw to" | „napraw gramatykę i wytnij stronę bierną" |
| „profesjonalny ton" | „formalny, bez skrótów, trzecia osoba" |
| „wkrótce" | „w ostatniej linii, jako wezwanie do działania" |

---

## ✅ Sprawdzian

- [ ] Zastąpiłeś/aś niejasne słowa liczbami i kryteriami.
- [ ] Nazwałeś/aś odbiorcę i cel wprost.
- [ ] Dodałeś/aś co najmniej jedno ograniczenie negatywne (czego nie robić).
- [ ] „Przeczytałeś/aś jak obcy" i docisnąłeś/ęłaś wszelką dwuznaczność.

---

## 🎯 Praca domowa

Znajdź prompt napisany wcześniej, który nie dowiózł. Przepisz go, usuwając każde niejasne słowo — zastąp każde liczbą, kryterium lub nazwanym odbiorcą. Uruchom ponownie i porównaj.

---

## 💡 Najważniejsze wnioski

- Niejasność wypełnia się **przeciętnym strzałem** modelu — konkretność usuwa miejsce na błędne zgadywanie.
- Zastępuj przymiotniki („krótki", „dobry") **liczbami i kryteriami**.
- Nazywaj **odbiorcę, cel i czego unikać** — i czytaj prompt, jak zrobiłby to obcy.

🌐 [English](../../en/lessons/03-be-specific.md) · [← Poprzednia](02-anatomia-promptu.md) · [Strona kursu](../README.md) · [Dalej: Kontekst i okno kontekstowe →](04-kontekst-i-okno-kontekstowe.md)
