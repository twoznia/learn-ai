# D3 — Oszczędzaj tokeny i zarządzaj limitami

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Claude.ai

🌐 [English](../../en/track-d/03-save-tokens-and-manage-limits.md) · [← Wstecz](02-okno-kontekstowe.md) · [Indeks ścieżki](../README.md) · [Dalej: Skille i konektory →](04-skille-i-konektory.md)

---

## 🧠 Teoria (5 min)

Plan Pro/Max daje **hojną, ale nie nieograniczoną** ilość użycia. Odnawia się w **oknie kroczącym** (nowa pula otwiera się po kilku godzinach), a plany Max dodają wyższy pułap tygodniowy. Nie płacisz za wiadomość — ale jeśli wyczerpiesz okno, czekasz na reset.

Wszystko, co wysyłasz, **i** wszystko, co Claude generuje, liczy się do tego użycia. Więc dwie dźwignie to:

1. **Wysyłaj mniej zbędnych rzeczy** (krótszy kontekst, właściwy model).
2. **Proś o mniej zbędnego wyjścia** (bądź konkretny co do długości i formatu).

Efektywność to nie upychanie — to **niemarnowanie okna na rzeczy, których nie potrzebowałeś.**

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Znajdź swoje użycie

**Settings → Usage** (lub strona planu) pokazuje, ile zużyłeś i kiedy się resetuje. Sprawdź raz, byś wiedział, gdzie stoisz — i sprawdzaj, jeśli odpowiedzi nagle mówią, że jesteś blisko limitu.

### Krok 2 — Dobierz rozmiar modelu

Cięższe modele zużywają limit szybciej. Dopasuj model do zadania (z D1):

- **Haiku / Sonnet** do szybkiej lub rutynowej pracy.
- **Opus** tylko gdy zadanie naprawdę wymaga najgłębszego rozumowania.

Przełączenie prostego wyszukania z Opusa na Sonnet to darmowa wygrana.

### Krok 3 — Trzymaj kontekst chudy

Z D2: długi czat czyta wszystko co turę, co zużywa limit. Konkretnie:
- **Jeden czat = jedno zadanie**; zaczynaj od nowa dla nowych tematów.
- Nie wklejaj całego 50-stronicowego PDF, by zapytać o jeden akapit — **wklej akapit**.
- Załączaj pliki zamiast wklejać ogromne bloki, gdy możesz.

### Krok 4 — Proś o wyjście, którego naprawdę chcesz

Nieograniczone odpowiedzi marnują tokeny. Steruj długością i kształtem:

```text
Odpowiedz w 3 punktach, każdy w jednej linii. Bez wstępu.
```
```text
Daj mi tylko finalne zapytanie SQL — bez wyjaśnień.
```
```text
Streść w mniej niż 100 słowach.
```

Dostajesz to, czego potrzebujesz, i przestajesz płacić za akapity, które pominiesz.

### Krok 5 — Używaj ponownie zamiast generować od nowa

- Zapisuj dobre prompty (patrz biblioteka promptów ze Ścieżki A), by ich nie odtwarzać.
- Umieść stały kontekst w **Projekcie**, byś nigdy go nie wklejał ponownie.
- Jeśli masz już dobrą odpowiedź, **edytuj** ją sam, zamiast generować całość na nowo.

### Krok 6 — Grupuj drobiazgi

Zamiast dziesięciu malutkich wymian, poproś o kilka powiązanych rzeczy w **jednej** dobrze ustrukturyzowanej wiadomości. Mniej tur = mniej ponownego czytania rosnącego kontekstu.

---

## 🧩 Ściąga oszczędzania tokenów

| Nawyk | Dlaczego oszczędza |
|-------|-------------|
| Dobierz rozmiar modelu | Lżejsze modele zużywają mniej limitu |
| Jeden czat = jedno zadanie | Brak starego kontekstu czytanego co turę |
| Wklej istotny fragment, nie cały dokument | Mniej wejścia do przetworzenia |
| Określ długość/format | Brak zmarnowanego wyjścia |
| Projekty na stały kontekst | Koniec wklejania tła |
| Grupuj powiązane prośby | Mniej tur, mniej czytania |
| Edytuj zamiast generować | Nie płać dwa razy za tę samą odpowiedź |

---

## ✅ Sprawdzenie

- [ ] Znalazłeś stronę użycia/limitów i wiesz, kiedy się resetuje.
- [ ] Zastosowałeś co najmniej trzy nawyki oszczędzania tokenów w prawdziwym czacie.
- [ ] Umiesz wyjaśnić, czemu **i wejście, i wyjście** liczą się do użycia.

---

## 🎯 Zadanie

Weź zadanie, które normalnie zrobiłbyś w długim, bałaganiarskim czacie. Zrób je efektywnie: właściwy model, chudy kontekst, instrukcja długości i jedna zgrupowana wiadomość. Zauważ, o ile krótsze i szybsze jest — to limit, który właśnie zaoszczędziłeś.

---

## 💡 Najważniejsze wnioski

- Użycie liczy **i** to, co wysyłasz, **i** to, co Claude generuje; oszczędzaj po obu stronach.
- Dobierz **model**, trzymaj **kontekst chudy** i **określ** wyjście, którego chcesz.
- **Projekty** + zapisane prompty + edytowanie (zamiast generowania) zatrzymują powtarzalne marnotrawstwo.

🌐 [English](../../en/track-d/03-save-tokens-and-manage-limits.md) · [← Wstecz](02-okno-kontekstowe.md) · [Indeks ścieżki](../README.md) · [Dalej: Skille i konektory →](04-skille-i-konektory.md)
