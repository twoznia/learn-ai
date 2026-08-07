# F2 — Analiza danych (uruchamiaj kod na swoich danych)

⏱️ **15 minut** · Ścieżka: 🅵 Poza czatem · Potrzebne: aplikacja Gemini, mały CSV lub arkusz

🌐 [English](../../en/track-f/02-data-analysis.md) · [← Wstecz](01-canvas-buduj-i-udostepniaj.md) · [Indeks ścieżki](../README.md) · [Dalej: Połączone aplikacje →](03-polaczone-aplikacje.md)

---

## 🧠 Teoria (4 min)

Gdy prosisz chatbota, by „zsumował tę kolumnę”, często **zgaduje** ze wzorców — i może się mylić. Gemini potrafi lepiej: może **napisać i uruchomić kod**, by policzyć wynik na Twoich prawdziwych danych. Prawdziwa matematyka, nie szacowanie.

Czemu to ważne:

- **Dokładność.** Liczby są liczone, nie zgadywane — sumy, średnie, zliczenia, filtry w kodzie.
- **Prawdziwe pliki.** Wyślij CSV/Excel, a Gemini go przetworzy.
- **Wykresy.** Może zamienić wyniki w wizualizację.
- **Bez kodowania przez Ciebie.** Opisujesz analizę; Gemini pisze i uruchamia kod.

> Uruchamianie kodu / analiza danych może różnić się między aplikacją Gemini a **Google AI Studio** (aistudio.google.com), gdzie możesz wyraźnie włączyć narzędzie uruchamiania kodu. Jeśli aplikacja nie uruchomi kodu na pliku, AI Studio to pewne miejsce, by spróbować.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zdobądź dane

Brak pliku? Poproś Gemini:

```text
Utwórz przykładowy CSV z 20 wierszami fałszywej miesięcznej sprzedaży: kolumny month, region, amount.
Daj mi plik do pobrania.
```

Pobierz go (lub użyj małego prawdziwego arkusza).

### Krok 2 — Wyślij i poproś o prawdziwe liczby

Załącz CSV i poproś:

```text
Policz sumę i średnią sprzedaży na region i powiedz, który region najwyższy i najniższy.
Uruchom obliczenie i pokaż liczby.
```

Gemini liczy i raportuje wyniki — nie zgadywanie.

### Krok 3 — Naciśnij na dokładność

```text
Pokaż mi też dokładne wartości na miesiąc i potwierdź, że sumy się zgadzają.
```

Ponieważ to prawdziwe obliczenia, liczby się bilansują. O to chodzi — wiarygodne odpowiedzi na danych.

### Krok 4 — Zdobądź wykres

```text
Teraz zrób prosty wykres liniowy łącznej sprzedaży wg miesiąca i wskaż trend.
```

### Krok 5 — Wyczyść bałaganiarskie dane

```text
Ten arkusz ma niespójne nazwy regionów (np. „north”, „North ”, „N”).
Ujednolić je, potem przelicz sumy na region.
```

Bolesne ręcznie; szybkie z kodem.

### Krok 6 — Ufaj, ale weryfikuj

Metodę ustawiasz sposobem pytania. Przy czymkolwiek ważnym:
- Poproś o **pokazanie liczb** i **jak pogrupował/przefiltrował**.
- Sam sprawdź jedną liczbę.

```text
Wyjaśnij, jak pogrupowałeś wiersze i które wykluczyłeś, jeśli w ogóle.
```

---

## 🧩 Analiza vs zwykły czat

| Zadanie | Użyj |
|------|-----|
| „Ile to 20% z 4 318?” | Oba — ale policzone jest dokładne |
| „Zsumuj tę kolumnę 500 wierszy” | **Uruchom kod** (nie ufaj zgadywaniu) |
| „Wyczyść i przelicz ten bałaganiarski arkusz” | **Uruchom kod** |
| „Wykres sprzedaży wg miesiąca” | **Uruchom kod** |
| „Wyjaśnij, czym jest mediana” | Zwykły czat |

> ⚠️ **Wciąż Twoje dane.** Nie wysyłaj niczego wrażliwego. Weryfikuj ważne liczby — metodę ustawiasz sposobem pytania.

---

## ✅ Sprawdzenie

- [ ] Wysłałeś CSV i dostałeś **policzone** (nie zgadnięte) sumy.
- [ ] Kazałeś Gemini pokazać wartości pozycji i potwierdzić, że się bilansują.
- [ ] Wygenerowałeś wykres z danych.
- [ ] Wyczyściłeś bałaganiarską kolumnę i przeliczyłeś (w aplikacji lub AI Studio).

---

## 🎯 Zadanie

Weź prawdziwy arkusz (budżet, dziennik, eksport). Policz podsumowanie, ujednolić bałaganiarską kolumnę i zrób jeden wykres. Poproś Gemini o wyjaśnienie grupowania, byś ufał wynikowi.

---

## 💡 Najważniejsze wnioski

- Gemini potrafi **napisać i uruchomić kod** na plikach — dokładne obliczenia, bez kodowania przez Ciebie (użyj **AI Studio**, jeśli aplikacja nie uruchomi).
- Najlepsze do **sum/średnich/filtrów, porządków i wykresów**, gdzie zgadywanie byłoby ryzykowne.
- **Ty sterujesz metodą** — proś o pokazanie liczb i wyjaśnienie grupowania i weryfikuj wszystko ważne.

🌐 [English](../../en/track-f/02-data-analysis.md) · [← Wstecz](01-canvas-buduj-i-udostepniaj.md) · [Indeks ścieżki](../README.md) · [Dalej: Połączone aplikacje →](03-polaczone-aplikacje.md)
