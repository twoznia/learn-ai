# Lekcja 16 — Prompt engineering, który działa

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: dowolny ChatGPT (sieć/aplikacja/kod)

🌐 [English](../../en/lessons/16-prompt-engineering.md) · [← Wstecz](15-wyszukiwanie-web.md) · [Strona kursu](../README.md) · [Dalej: Koszty i bezpieczeństwo →](17-koszty-bezpieczenstwo.md)

---

## 🧠 Teoria (4 min)

Podstawy (R-K-Z-F) poznałeś w Lekcji 3. Oto **wzorce używane przez profesjonalistów**, które dają stale świetne wyniki. Żaden nie wymaga kodu — działają wszędzie, gdzie rozmawiasz z ChatGPT.

### 1. Podaj przykłady (few-shot)

Pokaż wzorzec, którego chcesz, potem poproś o więcej.

```text
Zamień nazwy produktów na chwytliwe hasła. Przykłady:

"Ładowarka solarna" → "Moc z nieba, gdziekolwiek jesteś."
"Słuchawki z redukcją szumów" → "Twoja cisza, na żądanie."

Teraz zrób te:
"Butelka wielokrotnego użytku"
"Biurko stojące"
```

### 2. Poproś ChatGPT, aby pomyślał przed odpowiedzią

Przy trudnym rozumowaniu dodaj:

```text
Przemyśl to krok po kroku, zanim podasz ostateczną odpowiedź.
```

To widocznie poprawia matematykę, logikę i planowanie.

### 3. Przypisz jasną rolę + odbiorcę

```text
Jesteś pielęgniarką pediatryczną wyjaśniającą zmartwionemu rodzicowi. Wyjaśnij, co
oznacza gorączka 38,5°C i kiedy iść do lekarza. Ciepły ton, proste słowa.
```

### 4. Ogranicz format wyjścia

```text
Odpowiedz TYLKO jako poprawny JSON z kluczami: "podsumowanie", "poziom_ryzyka" (niski/średni/wysoki)
i "następny_krok". Bez dodatkowego tekstu.
```

### 5. Pozwól mu najpierw zadać pytania

```text
Chcę zaplanować przyjęcie urodzinowe. Zanim doradzisz, zadaj mi do 4
pytań, których potrzebujesz, aby dać świetny plan.
```

### 6. Iteruj — odpowiedź to szkic

```text
Skróć.
Teraz zabawniej.
Teraz przeredaguj na LinkedIn.
```

---

## 🛠️ Praktyka (5 min)

Wypróbuj każdą na własnych treściach w ChatGPT:

### Ćwiczenie 1 — Few-shot
Daj ChatGPT 2 przykłady tonu, którego używasz w e-mailach służbowych, potem poproś o nowy w tym samym tonie.

### Ćwiczenie 2 — Rozumowanie krok po kroku
```text
Sklep oferuje "kup 2, trzeci gratis" na skarpetki po 6 zł za parę. Chcę 9 par.
Przemyśl krok po kroku, potem podaj łączny koszt.
```

### Ćwiczenie 3 — Ścisły format
```text
Wyciągnij szczegóły z tego tekstu jako JSON z kluczami "imię", "data", "miejsce".
Tekst: "Lunch z Priyą 3 marca w Cafe Rio."
Zwróć tylko JSON.
```

### Ćwiczenie 4 — Pytania doprecyzowujące
```text
Pomóż mi napisać podsumowanie do CV. Zapytaj najpierw, co musisz wiedzieć.
```

---

## 🧰 Szablon „mocnego promptu” do skopiowania

Trzymaj to w `moje-prompty.txt` i uzupełniaj luki:

```text
Rola: Jesteś <kim>.
Odbiorca: <dla kogo to jest>.
Zadanie: <czego chcesz>.
Kontekst: <tło, ograniczenia, przykłady>.
Format: <jak ma wyglądać odpowiedź>.
Zasady:
- Jeśli nie jesteś pewny faktu, powiedz to.
- Zadaj pytanie doprecyzowujące, jeśli coś jest niejednoznaczne.
- Zmieść się w <długość/ton>.

Oto dane wejściowe:
<wklej swoją treść>
```

---

## ⚠️ Częste błędy do uniknięcia

| Błąd | Poprawka |
|---------|-----|
| Niejasna prośba | Dodaj Rolę + Format |
| Ślepe zaufanie faktom | Poproś o oznaczanie niepewności; weryfikuj (lub użyj wyszukiwania, Lekcja 15) |
| Jeden ogromny prompt na wiele zadań | Podziel na kroki; iteruj |
| Akceptacja pierwszego szkicu | Doprecyzowuj szybkimi uzupełnieniami |
| Brak przykładów | Pokaż 1–2 przykłady, jak wygląda „dobre” |

---

## ✅ Sprawdzenie

- [ ] Użyłeś przykładów few-shot.
- [ ] Użyłeś „przemyśl krok po kroku” i zobaczyłeś lepsze rozumowanie.
- [ ] Uzyskałeś od ChatGPT ścisły JSON.
- [ ] Pozwoliłeś ChatGPT zadać *Tobie* pytania doprecyzowujące.

---

## 🎯 Zadanie

Przeredaguj prompt „irytującego zadania” z Lekcji 1 używając **szablonu mocnego promptu**. Zapisz wersję ostateczną — to narzędzie, którego będziesz używać miesiącami.

---

## 💡 Najważniejsze wnioski

- Pokazuj przykłady, przypisuj rolę i przypinaj format wyjścia.
- „Przemyśl krok po kroku” wzmacnia zadania rozumowania.
- Pozwól ChatGPT pytać; traktuj pierwsze odpowiedzi jak szkice i iteruj.
- Dla faktów łącz dobre prompty z **wyszukiwaniem w sieci** (Lekcja 15).

🌐 [English](../../en/lessons/16-prompt-engineering.md) · [← Wstecz](15-wyszukiwanie-web.md) · [Strona kursu](../README.md) · [Dalej: Koszty i bezpieczeństwo →](17-koszty-bezpieczenstwo.md)
