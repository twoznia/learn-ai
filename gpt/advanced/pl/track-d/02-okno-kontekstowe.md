# D2 — Okno kontekstowe (i kiedy zacząć od nowa)

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Wymagania: konto ChatGPT

🌐 [English](../../en/track-d/02-context-window.md) · [← Poprzedni](01-wykorzystaj-plan.md) · [Spis ścieżki](../README.md) · [Dalej: Oszczędzaj użycie i limity →](03-oszczedzaj-uzycie-i-limity.md)

---

## 🧠 Teoria (5 min)

ChatGPT czyta **całą Twoją rozmowę** za każdym razem, gdy odpowiada — Twoje wiadomości, jego odpowiedzi i wszystkie załączone pliki. Ta narastająca suma to **kontekst**, a mieści się on w oknie kontekstowym o stałym rozmiarze.

Wynikają z tego dwie rzeczy:

1. **Długi czat jest odczytywany od nowa w każdej turze.** Tura 30. przetwarza ponownie wszystko, co było przed nią — wolniej i więcej Twojego użycia niż krótki, skupiony czat.
2. **Gdy okno się zapełni, początek wypada z pola widzenia.** ChatGPT może „zapomnieć", co powiedziałeś/aś na samym początku bardzo długiej rozmowy.

Umiejętność to wiedzieć, **kiedy kontynuować**, a **kiedy zacząć nowy czat** — i jak przenieść tylko to, co ważne.

```
[ Ty ][ GPT ][ Ty ][ GPT ] ... → wszystko odczytywane w każdej turze
                          ↑
                okno kontekstowe (stały rozmiar)
```

> Uwaga: **pamięć** (D4) to co innego — to mały zestaw zapisanych faktów o Tobie, który trwa między czatami. Nie usuwa limitu kontekstu w obrębie czatu.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zobacz, jak czat się „zapełnia"

Wklej długi dokument do czatu i zadaj kilka pytań uzupełniających. Zauważ, że odpowiedzi robią się nieco wolniejsze wraz z rozrostem rozmowy — to całość odczytywana za każdym razem.

### Krok 2 — Zacznij od nowa, gdy zmienia się temat

Nowe, niepowiązane zadanie? **Zacznij nowy czat** zamiast kontynuować. Świeży czat jest szybszy i tańszy — brak starego kontekstu do ponownego odczytu.

> Zasada: **jeden czat = jedno zadanie.** Zmiana tematu → nowy czat.

### Krok 3 — Przenieś podsumowanie, nie całą historię

Aby kontynuować gdzie indziej, podsumuj zamiast wklejać na nowo:

```text
Podsumuj tę rozmowę w krótkie przekazanie do nowego czatu: cel, podjęte
decyzje i obecny stan. Zmieść się w 200 słowach.
```

Wklej to do **nowego** czatu.

### Krok 4 — Używaj Projektów do kontekstu, który powtarzasz

Wyjaśniasz *to samo* tło za każdym razem (Twój produkt, styl, zasady)? Umieść to w **Projekcie**:

1. Pasek boczny → **Projekty** → nowy projekt, dodaj stały kontekst do jego instrukcji/plików.
2. Zaczynaj czaty **wewnątrz** projektu — GPT już zna tło.

Teraz każdy czat w tym projekcie startuje załadowany i nigdy więcej tego nie wklejasz. **Custom GPT** (A1) działa podobnie dla powtarzalnej roli.

### Krok 5 — Wklej istotny fragment, nie wszystko

Nie wklejaj 50-stronicowego raportu, by zapytać o jeden rozdział — **wklej rozdział** (lub załącz plik). Więcej skupienia = ostrzejsze odpowiedzi i mniejsze użycie.

### Krok 6 — Wypatruj „zapominania"

W bardzo długim czacie, jeśli GPT gubi coś z początku, to okno się zapełnia. Powtórz kluczowy fakt, **albo** zacznij od nowa z podsumowaniem, **albo** przenieś stałe fakty do **Projektu**.

---

## 🧩 Kontynuować czy zacząć od nowa?

| Sytuacja | Zrób to |
|-----------|---------|
| To samo zadanie, na dobrej drodze | Kontynuuj |
| Nowe, niepowiązane zadanie | Nowy czat |
| Czat jest ogromny i wolny | Podsumuj → nowy czat |
| To samo tło często powtarzane | Umieść w **Projekcie** / Custom GPT |
| GPT zapomniał wczesnego szczegółu | Powtórz go lub podsumuj → świeży czat |

---

## ✅ Sprawdzian

- [ ] Umiesz wyjaśnić, czemu długie czaty są wolniejsze i zużywają więcej limitu.
- [ ] Zacząłeś/aś świeży czat do nowego zadania zamiast kontynuować.
- [ ] Stworzyłeś/aś podsumowanie-przekazanie i/lub Projekt do ponownego użycia kontekstu.
- [ ] Wiesz, że pamięć (D4) jest oddzielna od okna kontekstowego czatu.

---

## 🎯 Praca domowa

Weź jeden długi, rozgałęziony czat. Skompresuj go do przekazania poniżej 200 słów, zacznij świeży czat i potwierdź, że GPT podejmuje wątek. Następnie stwórz Projekt dla tematu, nad którym pracujesz regularnie.

---

## 💡 Najważniejsze wnioski

- ChatGPT odczytuje **całą rozmowę** w każdej turze; długie czaty są wolniejsze i zużywają więcej limitu.
- **Jeden czat = jedno zadanie** — zaczynaj od nowa przy nowych tematach; przenoś krótkie podsumowanie, nie całą historię.
- Umieść **powtarzane tło** w **Projekcie** (lub Custom GPT), by przestać je wklejać — pamięć (D4) to osobna funkcja.

🌐 [English](../../en/track-d/02-context-window.md) · [← Poprzedni](01-wykorzystaj-plan.md) · [Spis ścieżki](../README.md) · [Dalej: Oszczędzaj użycie i limity →](03-oszczedzaj-uzycie-i-limity.md)
