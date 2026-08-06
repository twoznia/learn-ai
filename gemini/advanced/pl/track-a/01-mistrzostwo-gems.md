# A1 — Mistrzostwo Gemów

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: aplikacja Gemini (Gemy)

🌐 [English](../../en/track-a/01-gems-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym poznałeś **Gemy** jako „własnych asystentów ze stałymi instrukcjami”. Teraz potraktujemy Gem jak **produkt, który projektujesz** — wyspecjalizowanego asystenta zachowującego się spójnie w jednym zadaniu.

Świetny Gem ma trzy warstwy:

1. **Rola i zasady** (instrukcje) — *kim jest i jak się zachowuje*.
2. **Wiedza** (pliki/kontekst) — *co zawsze wie*: fakty, styl, zasady, przykłady.
3. **Przepływy pracy** (zapisane prompty) — *powtarzalne zadania*.

Błąd początkujących to jedna gigantyczna instrukcja. Ruch profesjonalisty to **oddzielenie stabilnej wiedzy od zachowania od zadań** — każda część zostaje czysta i wielokrotnego użytku.

---

## 🛠️ Praktyka (9 min)

Zbudujemy Gem **„Asystent e-maili do klientów”** od początku do końca.

### Krok 1 — Utwórz Gem + rola/zasady

W aplikacji Gemini utwórz **New Gem** o nazwie **„E-maile klientów”**. W instrukcjach wklej:

```text
Jesteś moim asystentem komunikacji z klientami dla małego studia projektowego.

ZACHOWANIE
- Ton: ciepły, profesjonalny, zwięzły.
- Nigdy nie obiecuj terminów, cen ani zakresu, których nie potwierdziłem.
- Jeśli prośba wymaga informacji, których nie masz, zadaj najpierw JEDNO pytanie doprecyzowujące.
- Domyślnie 2 wersje każdego e-maila: „zwięzła” i „cieplejsza”.

FORMAT WYJŚCIA
- Zacznij od jednej linii podsumowania, co robi e-mail.
- Potem e-mail(e), każdy pod jasnym nagłówkiem.
- Zakończ „Na co uważać:” z rzeczami do sprawdzenia.
```

To wyłącznie **zachowanie** — żadnych faktów jeszcze.

### Krok 2 — Dodaj wiedzę (fakty, których nie może wymyślać)

Gemy przyjmują pliki referencyjne lub blok „wiedzy”. Dodaj to jako wysłany `fakty-studia.txt` lub wklej do instrukcji pod nagłówkiem `FAKTY`:

```text
FAKTY STUDIA (referencja — nie wymyślaj poza tym)
- Nazwa studia: Northlight Design
- Usługi: identyfikacja marki, projektowanie stron, druk
- Typowy start projektu: 2-3 tygodnie po zaliczce
- Nigdy nie podajemy ostatecznych cen e-mailem bez rozmowy zakresowej
```

Teraz odwołuje się do prawdziwych faktów zamiast zgadywać.

### Krok 3 — Dodaj przykład głosu

Daj mu jeden e-mail, z którego jesteś dumny (jako plik lub wklejony przykład), i dodaj:

```text
- Dopasuj głos z przykładu: styl powitania, podpis, długość zdań.
```

### Krok 4 — Zapisz przepływy jako prompty wielokrotnego użytku

Zachowaj w `moje-prompty.txt`:

```text
Naszkicuj odpowiedź na ten e-mail klienta. Użyj faktów studia i mojego głosu.

E-MAIL KLIENTA:
<wklej>

MOJA OGÓLNA INTENCJA:
<kilka słów>
```

```text
Klient jest niezadowolony z opóźnienia. Napisz przeprosiny pozostające profesjonalne,
biorące odpowiedzialność bez nadmiernych obietnic i oferujące jeden konkretny następny krok.

KONTEKST:
<wklej>
```

### Krok 5 — Sprawdź warstwy razem

Wklej prawdziwy (lub zmyślony) e-mail i sprawdź: czy użył **faktu**? Czy dopasował **głos**? Czy przestrzegał **formatu**? Popraw słabą *warstwę* — zwykle wiedzę, nie instrukcje.

---

## 🧩 Zasada projektowa

| Umieść to… | …w tej warstwie | Dlaczego |
|-----------|----------------|-----|
| Jak się zachowuje | Instrukcje | Rzadko się zmienia; krótkie |
| Fakty, których nie może wymyślać | Wiedza/pliki | Aktualizuj fakty, nie prompty |
| Przykłady głosu/formatu | Wiedza/pliki | Pokazuj, nie opisuj |
| Powtarzalne zadania | Zapisane prompty | Używaj ponownie w rozmowach |

---

## ✅ Sprawdzenie

- [ ] Twój Gem ma instrukcje **i** warstwę wiedzy/faktów.
- [ ] Odwołał się do faktu, który podałeś.
- [ ] Zapisałeś co najmniej dwa prompty przepływów.

---

## 🎯 Zadanie

Zbuduj **drugi** Gem dla innego realnego zadania (nauka, dodatkowy biznes, hobby). Wykorzystaj wzorzec trzech warstw.

---

## 💡 Najważniejsze wnioski

- Mocny Gem = **zachowanie + wiedza + przepływy**, rozdzielone.
- Umieść fakty w warstwie wiedzy, aby Gemini przestał zgadywać.
- Popraw słabą *warstwę*, nie cały prompt.

🌐 [English](../../en/track-a/01-gems-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)
