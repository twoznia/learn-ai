# Lekcja 12 — Autokrytyka i iteracja

⏱️ **11 minut** · Poziom: Średni → Zaawansowany · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/12-self-critique-and-iteration.md) · [← Poprzednia](11-ograniczanie-halucynacji.md) · [Strona kursu](../README.md) · [Dalej: Praca z długimi dokumentami →](13-dlugie-dokumenty.md)

---

## 🧠 Teoria (4 min)

Pierwsza odpowiedź to **szkic**, nie ostatnie słowo. Dwa z najpotężniejszych (i niedocenianych) ruchów promptowania to poproszenie modelu, by **skrytykował własną pracę**, a potem ją **ulepszył** — i traktowanie całej interakcji jak pętli.

Dlaczego autokrytyka działa: przeglądanie to inne zadanie niż generowanie. Poproszony o *ocenę* wobec kryteriów, model często dostrzega słabości, które wytworzył chwilę wcześniej.

Dlaczego iteracja działa: rzadko dostajesz idealny prompt za pierwszym razem. Zamiast przepisywać od zera, **dopracowuj w miejscu** — „dobrze, ale krócej i mniej formalnie" — sterując model ku temu, czego chcesz.

Zmiana nastawienia: nie zadajesz pytania, tylko **prowadzisz krótki proces redakcyjny** z modelem.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Poproś o autokrytykę

Po odpowiedzi:

```text
Skrytykuj swoją poprzednią odpowiedź wobec tych kryteriów: dokładność, klarowność
i czy odpowiedziała na faktyczne pytanie. Wypisz słabości, potem mocniejszą wersję.
```

### Krok 2 — Podaj rubrykę z góry

```text
Naszkicuj e-mail, potem oceń go 1–5 na klarowność, ciepło i zwięzłość i popraw
cokolwiek poniżej 4.
```

### Krok 3 — Iteruj, nie zaczynaj od nowa

Dopracowuj małymi szturchnięciami zamiast nowym promptem:

```text
Zwięźlej. Utnij wstęp. Niech ostatnia linia będzie pytaniem.
```

### Krok 4 — Poproś o alternatywy, potem połącz

```text
Daj mi 3 różne otwarcia z różnymi kątami. Wybiorę, potem dopracujesz.
```

### Krok 5 — Niech znajdzie własne błędy

```text
Zanim to użyję, wypisz cokolwiek, co może być błędne, niejasne lub brakujące.
```

### Krok 6 — Wiedz, kiedy przestać

Iteracja ma malejące zyski. Gdy odpowiedź spełnia kryteria, przestań — nie poleruj w nieskończoność.

---

## 🧩 Ruchy iteracji

| Ruch | Prompt |
|------|--------|
| Autokrytyka | „Skrytykuj to wobec [kryteriów], potem ulepsz" |
| Samoocena | „Oceń 1–5 na X, Y, Z i napraw poniżej 4" |
| Dopracuj w miejscu | „Krócej, cieplej, usuń wstęp" |
| Rozejdź się, potem zbiegnij | „3 opcje" → „dopracuj #2" |
| Pre-mortem | „Co jest błędne lub brakujące, zanim użyję?" |

---

## ✅ Sprawdzian

- [ ] Poprosiłeś/aś model o krytykę własnej odpowiedzi wobec kryteriów.
- [ ] Kazałeś/aś mu samoocenić i poprawić słabe części.
- [ ] Iterowałeś/aś małymi szturchnięciami zamiast przepisywać prompt.
- [ ] Przestałeś/aś, gdy odpowiedź spełniła kryteria.

---

## 🎯 Praca domowa

Weź dowolną pierwszą odpowiedź z dziś. Uruchom jeden przebieg autokrytyki („oceń wobec dokładności, klarowności, zwięzłości; potem ulepsz") i dwa małe szturchnięcia dopracowujące. Porównaj finalną z oryginałem — ta różnica to wartość iterowania.

---

## 💡 Najważniejsze wnioski

- Pierwsza odpowiedź to **szkic** — poproś model, by **skrytykował wobec kryteriów** i ulepszył.
- **Iteruj małymi szturchnięciami** („krócej, cieplej") zamiast zaczynać prompt od nowa.
- Używaj **rozejdź-się-potem-zbiegnij** (opcje → dopracuj) i **pre-mortem** — i przestań, gdy kryteria spełnione.

🌐 [English](../../en/lessons/12-self-critique-and-iteration.md) · [← Poprzednia](11-ograniczanie-halucynacji.md) · [Strona kursu](../README.md) · [Dalej: Praca z długimi dokumentami →](13-dlugie-dokumenty.md)
