# Lekcja 13 — Praca z długimi dokumentami

⏱️ **11 minut** · Poziom: Zaawansowany · Wymagania: dowolny czat AI (wgrywanie plików pomaga)

🌐 [English](../../en/lessons/13-long-documents.md) · [← Poprzednia](12-autokrytyka-i-iteracja.md) · [Strona kursu](../README.md) · [Dalej: Biblioteka wzorców promptów →](14-biblioteka-wzorcow-promptow.md)

---

## 🧠 Teoria (4 min)

Długie wejścia — raporty, transkrypcje, umowy, bazy kodu — obciążają okno kontekstowe i rozcieńczają skupienie modelu. Dobre promptowanie z nimi to osobna umiejętność.

Kluczowe taktyki:

- **Wskazuj precyzyjnie.** Pytaj o konkretną sekcję, nie o „całość".
- **Podsumowuj warstwowo.** Podsumuj każdą część, potem podsumuj podsumowania — hierarchia mieszcząca duży materiał w małym oknie.
- **Dziel długie wejścia.** Podziel ogromny dokument na kawałki, przetwórz każdy, potem połącz (łańcuch z Lekcji 9).
- **Osadzaj i cytuj.** Przy długich źródłach zawsze każ modelowi cytować, skąd pochodzi odpowiedź (Lekcja 11) — łatwo inaczej zgubić wątek.

Nowoczesne narzędzia z **wgrywaniem plików** lub dużymi oknami pomagają, ale to *technika* — skup się, warstwuj, dziel, cytuj — czyni odpowiedzi niezawodnymi.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Zadaj celowane pytanie

Zamiast „podsumuj ten 40-stronicowy raport":

```text
Z załączonego raportu wyodrębnij tylko rekomendacje z Sekcji 4, jako listę
punktów, cytując zdanie, z którego każda pochodzi.
```

### Krok 2 — Warstwowe podsumowanie

```text
Podsumuj każdą z 5 sekcji w 2 zdaniach. Potem napisz jedno 4-zdaniowe ogólne
podsumowanie zbudowane z nich.
```

### Krok 3 — Podziel ogromne wejście

Jeśli się nie mieści, podziel:

```text
To część 1 z 3 transkrypcji. Podsumuj tylko tę część w 5 punktach. Wyślę części
2 i 3, potem poproszę o scalenie.
```

Potem:

```text
Oto 3 częściowe podsumowania. Scal je w jedno spójne, usuwając duplikaty.
```

### Krok 4 — Wyodrębnij dane strukturalne

```text
Z tej umowy wyodrębnij do tabeli: Klauzula | Zobowiązanie | Strona | Termin.
Zacytuj tekst źródłowy dla każdego wiersza.
```

### Krok 5 — Strzeż się utraconego szczegółu

```text
Jeśli jakaś część jest dwuznaczna lub brakuje potrzebnych informacji, wypisz te
luki zamiast zgadywać.
```

---

## 🧩 Taktyki długiego wejścia

| Sytuacja | Taktyka |
|-----------|--------|
| Potrzebujesz tylko jednej części | Wskaż tę sekcję |
| Za duże na okno | Podziel → podsumuj → scal |
| Potrzebujesz szerokiego obrazu | Warstwowe (hierarchiczne) podsumowanie |
| Potrzebujesz faktów, na których polegasz | Wyodrębnij + cytuj źródła |
| Ryzyko pominięcia info | Poproś, by wypisał luki |

> ⚠️ Przy długich źródłach nieosadzone odpowiedzi są bardziej ryzykowne — zawsze proś o **cytaty/cytowania** i wypatruj utraconego szczegółu.

---

## ✅ Sprawdzian

- [ ] Zadałeś/aś celowane pytanie zamiast „podsumuj wszystko".
- [ ] Wytworzyłeś/aś warstwowe (hierarchiczne) podsumowanie.
- [ ] Podzieliłeś/aś długie wejście i scaliłeś/aś części.
- [ ] Wyodrębniłeś/aś dane strukturalne z cytatami źródeł.

---

## 🎯 Praca domowa

Weź długi dokument, który naprawdę masz. Uzyskaj z niego trzy rzeczy: rekomendacje z jednej sekcji (z cytatami), warstwowe podsumowanie i strukturalną tabelę kluczowych faktów. Zanotuj, gdzie cytowanie źródła złapało szczegół, który byś pominął/ęła.

---

## 💡 Najważniejsze wnioski

- Przy długich wejściach: **wskazuj precyzyjnie, podsumowuj warstwowo, dziel-i-scalaj i cytuj źródła**.
- Duże okna i wgrywanie plików pomagają, ale to **technika** utrzymuje odpowiedzi niezawodnymi.
- Nieosadzone odpowiedzi nad długimi źródłami są ryzykowne — **żądaj cytatów** i wypatruj utraconego szczegółu.

🌐 [English](../../en/lessons/13-long-documents.md) · [← Poprzednia](12-autokrytyka-i-iteracja.md) · [Strona kursu](../README.md) · [Dalej: Biblioteka wzorców promptów →](14-biblioteka-wzorcow-promptow.md)
