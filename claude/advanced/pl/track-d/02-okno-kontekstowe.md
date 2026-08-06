# D2 — Okno kontekstowe (i kiedy zacząć od nowa)

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Claude.ai

🌐 [English](../../en/track-d/02-context-window.md) · [← Wstecz](01-wykorzystaj-abonament.md) · [Indeks ścieżki](../README.md) · [Dalej: Oszczędzaj tokeny i limity →](03-oszczedzaj-tokeny-i-limity.md)

---

## 🧠 Teoria (5 min)

Claude czyta **całą rozmowę** za każdym razem, gdy odpowiada — Twoje wiadomości, jego odpowiedzi i wszystkie załączone pliki. Ta suma bieżąca to **kontekst**, a mieści się w **oknie kontekstowym** o stałym rozmiarze.

Wynikają z tego dwie rzeczy:

1. **Długi czat jest ponownie czytany w każdej turze.** Tura 30 przetwarza znów wszystko z tur 1–29. To wolniej i zużywa więcej Twojego limitu niż krótki, skupiony czat.
2. **Gdy okno się zapełni, początek wypada z pola widzenia.** Claude może „zapomnieć”, co powiedziałeś na samym początku bardzo długiej rozmowy.

Umiejętność to wiedzieć, **kiedy kontynuować**, a **kiedy zacząć nowy czat** — i jak przenieść tylko to, co ważne.

```
[ Twoja wiad. ][ Claude ][ Twoja wiad. ][ Claude ] ... → wszystko czytane co turę
                                          ↑
                                okno kontekstowe (stały rozmiar)
```

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zobacz, jak czat się „zapełnia”

Otwórz zwykły czat, wklej długi dokument i zadaj kilka pytań uzupełniających. Zauważ, że odpowiedzi lekko zwalniają, gdy rozmowa rośnie — to ponowne czytanie całości.

### Krok 2 — Zaczynaj od nowa, gdy zmienia się temat

Nowe zadanie? **Zacznij nowy czat**, zamiast kontynuować niezwiązany. Świeży czat jest szybszy i tańszy, bo nie ma starego kontekstu do ponownego czytania.

> Zasada kciuka: **jeden czat = jedno zadanie.** Gdy przechodzisz do czegoś niezwiązanego, otwórz nowy czat.

### Krok 3 — Przenieś tylko to, co ważne

Gdy *chcesz* kontynuować gdzie indziej, nie wklejaj całego starego czatu. Poproś Claude o streszczenie kluczowych rzeczy:

```text
Streść tę rozmowę w krótkie przekazanie, które wkleję do nowego czatu:
cel, decyzje, które podjęliśmy, i obecny stan. Zmieść się w 200 słowach.
```

Skopiuj to streszczenie do **nowego** czatu. Zachowujesz przydatny kontekst i pozbywasz się balastu.

### Krok 4 — Użyj Projektów do kontekstu wielokrotnego użytku

Jeśli wciąż tłumaczysz *to samo* tło (Twój produkt, styl, zasady), nie wklejaj go za każdym razem — umieść w **Projekcie**.

1. Lewy pasek → **Projects** → **New Project**.
2. Dodaj stały kontekst do **Project knowledge** (lub instrukcji projektu).
3. Zaczynaj czaty **wewnątrz** projektu — Claude już zna tło.

Teraz każdy czat w tym projekcie startuje z załadowanym kontekstem, a Ty nigdy go nie wklejasz ponownie.

### Krok 5 — Wypatruj „zapominania”

W bardzo długim czacie, jeśli Claude gubi coś z początku, to zapełniające się okno. Naprawy:
- Krótko powtórz kluczowy fakt, **albo**
- Zacznij świeży czat z krótkim streszczeniem (Krok 3), **albo**
- Przenieś stałe fakty do **Projektu** (Krok 4).

---

## 🧩 Kontynuować czy zacząć od nowa?

| Sytuacja | Zrób to |
|-----------|---------|
| To samo zadanie, wciąż na torze | Kontynuuj czat |
| Nowe, niezwiązane zadanie | Nowy czat |
| Czat jest ogromny i wolny | Streść → nowy czat |
| To samo tło używane często | Umieść w **Projekcie** |
| Claude zapomniał wczesny szczegół | Powtórz go lub streść → świeży czat |

---

## ✅ Sprawdzenie

- [ ] Umiesz wyjaśnić, czemu długie czaty zwalniają i zużywają więcej limitu.
- [ ] Zacząłeś świeży czat do nowego zadania, zamiast ciągnąć stary.
- [ ] Utworzyłeś streszczenie przekazania i/lub Projekt do wielokrotnego użycia kontekstu.

---

## 🎯 Zadanie

Weź jeden długi, rozlazły czat. Streść go do przekazania poniżej 200 słów, zacznij świeży czat z nim i potwierdź, że Claude podejmuje wątek tam, gdzie skończyłeś. Potem utwórz Projekt dla tematu, nad którym pracujesz wielokrotnie.

---

## 💡 Najważniejsze wnioski

- Claude ponownie czyta **całą rozmowę** co turę; długie czaty są wolniejsze i zużywają więcej limitu.
- **Jeden czat = jedno zadanie** — zaczynaj od nowa dla nowych tematów; przenoś krótkie streszczenie, nie całą historię.
- Umieść **powtarzalne tło** w **Projekcie**, by przestać je wklejać.

🌐 [English](../../en/track-d/02-context-window.md) · [← Wstecz](01-wykorzystaj-abonament.md) · [Indeks ścieżki](../README.md) · [Dalej: Oszczędzaj tokeny i limity →](03-oszczedzaj-tokeny-i-limity.md)
