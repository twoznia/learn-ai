# A3 — Canvas i Zaawansowana analiza danych

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: ChatGPT (funkcje zależą od planu)

🌐 [English](../../en/track-a/03-canvas-and-data-analysis.md) · [← Wstecz](02-biblioteka-promptow.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Poza czatem ChatGPT ma dwie funkcje mocy, które znacznie zwiększają produktywność — bez kodu:

- **Canvas** — interaktywna przestrzeń, gdzie ChatGPT szkicuje **dokument lub kod**, który edytujesz obok siebie i doprecyzowujesz, zamiast przewijać czat.
- **Zaawansowana analiza danych** — wysyłasz arkusz/CSV, a ChatGPT **pisze i uruchamia Pythona** w tle, by wyczyścić, przeanalizować i zwizualizować dane — potem wyjaśnia wyniki prostym językiem.

Obie mogą zależeć od planu/wdrożenia. Jeśli którejś nie ma, *umiejętności* i tak się przenoszą.

---

## 🛠️ Praktyka (9 min)

### Część 1 — Canvas

1. Zacznij zadanie tworzące **dokument lub kod** i otwórz je w **Canvas** (poszukaj opcji Canvas przy długim szkicu):

```text
Naszkicuj jednostronicową propozycję projektu ogrodu społecznego. Otwórz to w Canvas, abym mógł edytować.
```

2. W Canvas edytuj bezpośrednio i proś o celowane zmiany:

```text
Zrób z sekcji budżetu tabelę. Skróć wstęp do 3 zdań. Dodaj oś czasu.
```

3. Zauważ, że **iterujesz na żywym dokumencie**, a nie przewijasz czat. Znacznie lepsze dla wszystkiego, co wypuścisz.

### Część 2 — Zaawansowana analiza danych

1. Znajdź lub zrób mały CSV. Brak danych? Poproś ChatGPT: *„Zrób mi przykładowy CSV z 20 wierszami fałszywej miesięcznej sprzedaży i daj plik.”*
2. Wyślij CSV (📎) i poproś o analizę:

```text
Przeanalizuj te dane sprzedaży. Pokaż sumę i średnią wg miesiąca, zaznacz najlepszy i
najgorszy miesiąc, i zrób prosty wykres liniowy. Wyjaśnij, co się wyróżnia, prostym językiem.
```

3. ChatGPT pisze i uruchamia Pythona, potem pokazuje **wykres** i podsumowanie. Możesz pobrać wykres lub oczyszczone dane.
4. Iteruj:

```text
Teraz dodaj linię 3-miesięcznej średniej kroczącej i wyeksportuj wynik jako nowy CSV do pobrania.
```

### Część 3 — Połącz je

Przepływ mocy: **przeanalizuj dane → opisz w Canvas**.

```text
Weź powyższą analizę i zamień ją w jednostronicowy raport w Canvas, z wykresem,
polem „kluczowe wnioski” i 3 rekomendacjami.
```

Analiza danych znajduje historię; Canvas kształtuje ją w produkt.

---

## 🧭 Kiedy czego używać

| Funkcja | Do czego |
|---------|---------|
| **Canvas** | Dokumenty/kod, które będziesz edytować i zachowasz |
| **Zaawansowana analiza danych** | Arkusze, wykresy, „co mówią te dane” |
| **Obie** | Analiza → dopracowany raport |
| Zwykły czat | Szybkie pytania, szkice, burza mózgów |

> ⚠️ Zaawansowana analiza danych też może się mylić — sprawdzaj liczby i proś o pokazanie kroków przy wszystkim, co ważne.

---

## ✅ Sprawdzenie

- [ ] Naszkicowałeś i iterowałeś coś w Canvas.
- [ ] Wysłałeś dane i dostałeś analizę + wykres z Zaawansowanej analizy danych.
- [ ] Połączyłeś analizę w raport w Canvas.

---

## 🎯 Zadanie

Weź prawdziwy arkusz ze swojego życia (budżet, dziennik, wyeksportowane dane). Przeanalizuj go z ChatGPT, potem zamień wynik w jednostronicowy raport w Canvas, którym faktycznie byś się podzielił.

---

## 💡 Najważniejsze wnioski

- **Canvas** pozwala iterować na żywym dokumencie/kodzie zamiast przewijać czat.
- **Zaawansowana analiza danych** pisze+uruchamia Pythona na Twoich danych i wyjaśnia wyniki.
- Najmocniejszy przepływ to **Analiza → Canvas** dla dopracowanego raportu.

🌐 [English](../../en/track-a/03-canvas-and-data-analysis.md) · [← Wstecz](02-biblioteka-promptow.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
