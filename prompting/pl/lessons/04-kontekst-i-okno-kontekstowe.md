# Lekcja 04 — Kontekst i okno kontekstowe

⏱️ **11 minut** · Poziom: Początkujący → Średni · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/04-context-and-context-window.md) · [← Poprzednia](03-badz-konkretny.md) · [Strona kursu](../README.md) · [Dalej: Struktura i formatowanie →](05-struktura-i-formatowanie.md)

---

## 🧠 Teoria (4 min)

LLM wie tylko to, co ma **przed sobą** — bieżącą rozmowę. To **kontekst**, a mieści się w oknie kontekstowym o stałym rozmiarze. Dwie konsekwencje kształtują dobre promptowanie:

- **Brak kontekstu = zgadywanie.** Jeśli AI potrzebuje faktu, by dobrze odpowiedzieć (Twój produkt, odbiorca, dokument), musisz go **dostarczyć**. Nie pobierze tego, czego nie dałeś/aś.
- **Za dużo kontekstu = szum (i koszt).** Wrzucenie 50 stron, by zapytać o jeden akapit, grzebie sygnał, a całość jest odczytywana co turę — wolniej i, na płatnych planach, drożej.

Umiejętność to **kuracja**: zawrzyj dokładnie ten kontekst, który zmienia odpowiedź, i nic więcej. Istotne w, nieistotne poza.

> Każdy model ma limit kontekstu. Bardzo długie czaty mogą wypchnąć wczesne szczegóły z pola widzenia — model może „zapomnieć" początek. Powtórz kluczowe fakty lub zacznij od nowa, gdy to nastąpi.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Dostarcz brakujący fakt

Słabo (AI musi zgadnąć Twój stack):

```text
Napisz funkcję zapisującą ustawienia użytkownika.
```

Mocno (kontekst dostarczony):

```text
W projekcie Python 3 używającym SQLite napisz funkcję save_settings(user_id, settings_dict),
która robi upsert wiersza w tabeli „settings". Dopasuj ten istniejący styl: [wklej 5 linii].
```

### Krok 2 — Wklej istotną część, nie wszystko

Nie wklejaj całego raportu, by zapytać o jedną sekcję — **wklej sekcję**. Lub podsumuj resztę:

```text
Oto istotny akapit: „…". Tylko na jego podstawie odpowiedz: …
```

### Krok 3 — Wysuń na przód, co ważne

Umieść kluczową instrukcję i najważniejszy kontekst **blisko góry** długiego promptu, by nie zostały pogrzebane.

### Krok 4 — Przenieś podsumowanie między czatami

Zaczynasz świeży czat, by kontynuować? Przynieś zwięzłe przekazanie, nie całą historię:

```text
Podsumuj nasze decyzje i obecny stan w mniej niż 150 słowach, bym mógł/mogła
wkleić to do nowego czatu.
```

### Krok 5 — Zauważaj „zapominanie"

W bardzo długiej rozmowie, jeśli AI gubi wczesny szczegół, to okno się zapełnia. Powtórz fakt lub zacznij świeży czat z podsumowaniem.

---

## 🧩 Kontekst: zawrzeć vs wyciąć

| Zawrzyj | Wytnij |
|---------|-----|
| Fakty, których AI nie zna (Twoje dane, odbiorca) | Tło, które już zna |
| Konkretny tekst, o który pytasz | Niepowiązane strony „dla kompletu" |
| Przykłady stylu, który chcesz dopasować | Długą historię po podsumowaniu |
| Ograniczenia i cele | Powtórzenia i wypełniacze |

---

## ✅ Sprawdzian

- [ ] Dostarczyłeś/aś brakujący fakt zamiast pozwolić AI zgadywać.
- [ ] Wkleiłeś/aś istotną część zamiast wszystkiego.
- [ ] Wysunąłeś/ęłaś na przód kluczową instrukcję/kontekst.
- [ ] Umiesz wyjaśnić, co się dzieje, gdy czat robi się bardzo długi.

---

## 🎯 Praca domowa

Weź zadanie zależne od Twoich własnych informacji. Napisz prompt z akurat wystarczającym kontekstem — potem spróbuj usunąć jeden element i zobacz, czy odpowiedź się pogarsza. To mówi, co było naprawdę nośne.

---

## 💡 Najważniejsze wnioski

- AI wie tylko **bieżący kontekst** — dostarcz, czego potrzebuje, wytnij, czego nie.
- **Kuruj**: istotne fakty i konkretny tekst w; nieistotny nadmiar poza (dodaje szum i koszt).
- Długie czaty mogą wypchnąć wczesne szczegóły z **okna** — powtórz kluczowe fakty lub zacznij od nowa z podsumowaniem.

🌐 [English](../../en/lessons/04-context-and-context-window.md) · [← Poprzednia](03-badz-konkretny.md) · [Strona kursu](../README.md) · [Dalej: Struktura i formatowanie →](05-struktura-i-formatowanie.md)
