# F2 — Narzędzie analizy (uruchamiaj kod w czacie)

⏱️ **15 minut** · Ścieżka: 🅵 Poza czatem · Potrzebne: konto Claude.ai, mały CSV lub arkusz

🌐 [English](../../en/track-f/02-analysis-tool.md) · [← Wstecz](01-artefakty.md) · [Indeks ścieżki](../README.md) · [Dalej: Badania i web →](03-badania-i-web.md)

---

## 🧠 Teoria (4 min)

Gdy prosisz chatbota, by „zsumował tę kolumnę”, zwykle **zgaduje** wynik ze wzorców — i może się mylić. **Narzędzie analizy** to naprawia: Claude **pisze i uruchamia prawdziwy kod** (w czacie), by policzyć wynik. Prawdziwa matematyka, na Twoich prawdziwych danych.

Czemu to ważne:

- **Dokładność.** Liczby są liczone, nie szacowane. Sumy, średnie, zliczenia, filtry — w kodzie.
- **Prawdziwe pliki.** Wyślij CSV/Excel, a Claude przetworzy go programowo.
- **Wykresy.** Może zamienić wyniki w wizualizację.
- **Bez kodowania przez Ciebie.** Opisujesz analizę zwykłym językiem; Claude pisze kod i go uruchamia.

To coś innego niż ścieżka API/Claude Code — jest wbudowane w **czat**, bez konfiguracji.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zdobądź dane

Brak pliku? Poproś Claude o utworzenie:

```text
Utwórz przykładowy CSV z 20 wierszami fałszywej miesięcznej sprzedaży: kolumny month, region, amount.
Daj mi plik do pobrania.
```

Pobierz go (lub użyj własnego małego arkusza).

### Krok 2 — Wyślij i poproś o prawdziwe liczby

Załącz CSV (📎) i poproś:

```text
Używając narzędzia analizy, policz sumę i średnią sprzedaży na region i powiedz,
który region jest najwyższy i najniższy. Pokaż liczby.
```

Claude **uruchamia kod** na pliku i raportuje policzone wyniki — nie zgadywanie.

### Krok 3 — Naciśnij na dokładność

Poproś o udowodnienie pracy:

```text
Pokaż mi też dokładne wartości na miesiąc i potwierdź, że sumy się zgadzają.
```

Ponieważ to prawdziwe obliczenia, liczby się bilansują. O to właśnie chodzi — wiarygodne odpowiedzi na danych.

### Krok 4 — Zdobądź wykres

```text
Teraz zrób prosty wykres liniowy łącznej sprzedaży wg miesiąca i wskaż trend.
```

Claude liczy serię i tworzy wizualizację czytelną na pierwszy rzut oka.

### Krok 5 — Wyczyść bałaganiarskie dane

Narzędzie analizy błyszczy przy porządkach:

```text
Ten arkusz ma niespójne nazwy regionów (np. „north”, „North ”, „N”).
Ujednolić je, potem przelicz sumy na region ponownie.
```

Normalizuje dane w kodzie i przelicza — zadanie bolesne ręcznie.

### Krok 6 — Wiedz, kiedy ufać, a kiedy weryfikować

Narzędzie analizy liczy poprawnie, ale **Ty wybierasz metodę** przez to, jak pytasz. Przy czymkolwiek ważnym:
- Poproś o **pokazanie liczb** i **jak pogrupował/przefiltrował**.
- Sam sprawdź jedną liczbę.

```text
Wyjaśnij, jak pogrupowałeś wiersze i które wykluczyłeś, jeśli w ogóle.
```

---

## 🧩 Narzędzie analizy vs zwykły czat

| Zadanie | Użyj |
|------|-----|
| „Ile to 20% z 4 318?” | Oba — ale analiza jest dokładna |
| „Zsumuj tę kolumnę 500 wierszy” | **Narzędzie analizy** (nie ufaj zgadywaniu) |
| „Wyczyść i przelicz ten bałaganiarski arkusz” | **Narzędzie analizy** |
| „Wykres sprzedaży wg miesiąca” | **Narzędzie analizy** |
| „Wyjaśnij, czym jest mediana” | Zwykły czat |

> ⚠️ **Wciąż Twoje dane.** Nie wysyłaj niczego wrażliwego, czego nie chciałbyś przetwarzać. I weryfikuj ważne liczby — metodę ustawiasz sposobem pytania.

---

## ✅ Sprawdzenie

- [ ] Wysłałeś CSV i dostałeś **policzone** (nie zgadnięte) sumy.
- [ ] Kazałeś Claude pokazać wartości pozycji i potwierdzić, że się bilansują.
- [ ] Wygenerowałeś wykres z danych.
- [ ] Wyczyściłeś bałaganiarską kolumnę i przeliczyłeś.

---

## 🎯 Zadanie

Weź prawdziwy arkusz ze swojego życia (budżet, dziennik, eksport). Użyj narzędzia analizy, by policzyć podsumowanie, ujednolicić bałaganiarską kolumnę i zrobić jeden wykres. Poproś o wyjaśnienie grupowania, byś ufał wynikowi.

---

## 💡 Najważniejsze wnioski

- **Narzędzie analizy** każe Claude **pisać i uruchamiać kod** w czacie — prawdziwe, dokładne obliczenia na plikach, bez kodowania przez Ciebie.
- Najlepsze do **sum/średnich/filtrów, porządków i wykresów**, gdzie zgadnięta odpowiedź byłaby ryzykowna.
- **Ty sterujesz metodą** — proś o pokazanie liczb i wyjaśnienie grupowania i weryfikuj wszystko ważne.

🌐 [English](../../en/track-f/02-analysis-tool.md) · [← Wstecz](01-artefakty.md) · [Indeks ścieżki](../README.md) · [Dalej: Badania i web →](03-badania-i-web.md)
