# D2 — Okno kontekstowe (i kiedy zacząć od nowa)

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Google

🌐 [English](../../en/track-d/02-context-window.md) · [← Wstecz](01-wykorzystaj-plan.md) · [Indeks ścieżki](../README.md) · [Dalej: Oszczędzaj użycie i limity →](03-oszczedzaj-uzycie-i-limity.md)

---

## 🧠 Teoria (5 min)

Gemini czyta **całą rozmowę** za każdym razem, gdy odpowiada — Twoje wiadomości, jego odpowiedzi i wszystkie załączone pliki. Ta suma bieżąca to **kontekst**, a mieści się w **oknie kontekstowym**.

Okno Gemini jest **bardzo duże** (przyjmie długie dokumenty, a nawet kilka plików naraz), co to prawdziwa siła — ale dwie rzeczy nadal obowiązują:

1. **Długi czat jest ponownie czytany w każdej turze.** Tura 30 przetwarza wszystko przed nią — wolniej i więcej użycia niż krótki, skupiony czat.
2. **Większe nie zawsze lepsze.** Wrzucenie ogromnej, nieistotnej sterty czyni odpowiedzi mglistszymi, nie ostrzejszymi. Podawaj **istotny** kontekst, nie wszystko.

Umiejętność: wiedzieć, **kiedy kontynuować**, a **kiedy zacząć od nowa**, i jak przenieść tylko to, co ważne.

```
[ Ty ][ Gemini ][ Ty ][ Gemini ] ... → wszystko czytane co turę
                              ↑
                   okno kontekstowe (bardzo duże, ale nie darmowe)
```

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Użyj dużego okna celowo

Duży kontekst Gemini jest świetny do **długich wejść**. Wypróbuj:

```text
Oto 20-stronicowy dokument. Streść go, potem wypisz 5 decyzji, które implikuje.
```

Jedno długie wejście, jedna skupiona prośba — dokładnie do tego jest duże okno.

### Krok 2 — Ale zaczynaj od nowa, gdy temat się zmienia

Nowe, niezwiązane zadanie? **Zacznij nowy czat** zamiast kontynuować. Świeży czat jest szybszy i tańszy — brak starego kontekstu do ponownego czytania.

> Zasada kciuka: **jeden czat = jedno zadanie.** Zmiana tematu → nowy czat.

### Krok 3 — Podawaj istotny kontekst, nie wszystko

Nie wklejaj całego 50-stronicowego raportu, by zapytać o jedną sekcję — **wklej sekcję** (lub wyślij plik i wskaż go). Więcej skupienia = ostrzejsze odpowiedzi i mniej użycia.

### Krok 4 — Przenoś przekazanie, nie całą historię

By kontynuować gdzie indziej, streszczaj zamiast wklejać ponownie:

```text
Streść tę rozmowę w krótkie przekazanie do nowego czatu: cel, podjęte decyzje
i obecny stan. Zmieść się w 200 słowach.
```

Wklej to do **nowego** czatu.

### Krok 5 — Użyj Gemów do kontekstu wielokrotnego użytku

Tłumaczysz *to samo* tło co raz (produkt, styl, zasady)? Umieść je w **Gemie** (Ścieżka A1):

1. Utwórz Gema ze stałym kontekstem w instrukcjach.
2. Rozmawiaj **z Gemem** — już zna tło.

Teraz każdy czat z tym Gemem startuje załadowany, a Ty nigdy go nie wklejasz.

### Krok 6 — Wypatruj dryfu w bardzo długich czatach

Jeśli bardzo długi czat zaczyna gubić wątek, powtórz kluczowy punkt, **albo** zacznij świeży ze streszczeniem, **albo** przenieś stałe fakty do **Gema**.

---

## 🧩 Kontynuować czy zacząć od nowa?

| Sytuacja | Zrób to |
|-----------|---------|
| To samo zadanie, na torze | Kontynuuj |
| Nowe, niezwiązane zadanie | Nowy czat |
| Ogromny czat, wolny/mglisty | Streść → nowy czat |
| To samo tło używane często | Umieść w **Gemie** |
| Jeden długi dokument do analizy | Użyj dużego okna — podaj raz |

---

## ✅ Sprawdzenie

- [ ] Użyłeś dużego kontekstu do naprawdę długiego wejścia.
- [ ] Zacząłeś świeży czat do nowego zadania zamiast kontynuować.
- [ ] Zrobiłeś streszczenie przekazania i/lub Gema do wielokrotnego użycia.
- [ ] Umiesz wyjaśnić, czemu „wszystko” to nie to samo co „istotne”.

---

## 🎯 Zadanie

Weź długi dokument i użyj dużego okna, by go streścić + wydobyć decyzje. Potem weź rozlazły stary czat, sprowadź do przekazania poniżej 200 słów i kontynuuj w świeżym czacie. Na koniec umieść jedno powtarzalne tło w Gemie.

---

## 💡 Najważniejsze wnioski

- Okno Gemini jest **duże** — świetne do długich wejść — ale czat wciąż jest **czytany co turę**, więc długie czaty kosztują więcej.
- **Jeden czat = jedno zadanie**; podawaj **istotny** kontekst, nie wszystko; przenoś streszczenie, nie całą historię.
- Umieść **powtarzalne tło** w **Gemie**, by przestać je wklejać.

🌐 [English](../../en/track-d/02-context-window.md) · [← Wstecz](01-wykorzystaj-plan.md) · [Indeks ścieżki](../README.md) · [Dalej: Oszczędzaj użycie i limity →](03-oszczedzaj-uzycie-i-limity.md)
