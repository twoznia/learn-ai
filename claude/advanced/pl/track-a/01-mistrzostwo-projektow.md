# A1 — Mistrzostwo Projektów

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: Claude (Projekty; pełne funkcje w planie płatnym)

🌐 [English](../../en/track-a/01-projects-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym poznałeś **Projekty** jako „stałe instrukcje + pliki”. Teraz potraktujemy Projekt jak **produkt, który projektujesz** — wyspecjalizowanego asystenta zachowującego się spójnie w jednym zadaniu.

Świetny Projekt ma trzy warstwy:

1. **Rola i zasady** (instrukcje) — *kim jest i jak się zachowuje*.
2. **Wiedza** (pliki) — *co zawsze wie*: przewodnik stylu, lista produktów, zasady, przykłady.
3. **Przepływy pracy** (zapisane prompty) — *powtarzalne zadania, które wykonuje*.

Błąd początkujących to upychanie wszystkiego w jedną gigantyczną instrukcję. Ruch profesjonalisty to **oddzielenie stabilnej wiedzy (pliki) od zachowania (instrukcje) od zadań (prompty)** — każda część zostaje czysta i wielokrotnego użytku.

---

## 🛠️ Praktyka (9 min)

Zbudujemy Projekt **„Asystent e-maili do klientów”** od początku do końca.

### Krok 1 — Utwórz Projekt + rola/zasady

Utwórz nowy Projekt o nazwie **„E-maile klientów”**. W instrukcjach wklej:

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
- Zakończ „Na co uważać:” z rzeczami, które powinienem sprawdzić.
```

Zauważ, że to wyłącznie **zachowanie** — żadnych faktów ani przykładów jeszcze.

### Krok 2 — Dodaj pliki wiedzy

Daj mu to, co powinien zawsze wiedzieć. Utwórz mały plik tekstowy `fakty-studia.txt` i wyślij go do Projektu:

```text
FAKTY STUDIA (referencja — nie wymyślaj poza tym)
- Nazwa studia: Northlight Design
- Usługi: identyfikacja marki, projektowanie stron, druk
- Typowy start projektu: 2-3 tygodnie po zaliczce
- Godziny odpowiedzi: pon-pt, 9-17
- Nigdy nie podajemy ostatecznych cen e-mailem bez rozmowy zakresowej
```

Teraz asystent odwołuje się do prawdziwych faktów zamiast zgadywać — a Twoje instrukcje zostają krótkie.

### Krok 3 — Dodaj przykład stylu (few-shot jako plik)

Utwórz `probka-glosu.txt` z jednym e-mailem, z którego jesteś dumny, i wyślij go. Dodaj jedną linię do instrukcji:

```text
- Dopasuj głos z probka-glosu.txt (styl powitania, podpis, długość zdań).
```

### Krok 4 — Zapisz przepływy jako prompty wielokrotnego użytku

Wewnątrz Projektu uruchom te raz i zachowaj w `moje-prompty.txt`:

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

### Krok 5 — Sprawdź, że warstwy współpracują

Wklej prawdziwy (lub zmyślony) e-mail klienta i sprawdź:
- Czy użył **faktu** z `fakty-studia.txt`?
- Czy dopasował próbkę **głosu**?
- Czy przestrzegał **formatu** (podsumowanie → e-maile → Na co uważać)?

Jeśli jedna warstwa jest słaba, popraw *tę warstwę* — zwykle plik, nie instrukcje.

---

## 🧩 Zasada projektowa

| Umieść to… | …w tej warstwie | Dlaczego |
|-----------|----------------|-----|
| Jak ma się zachowywać | Instrukcje | Rzadko się zmienia; krótkie |
| Fakty, których nie może wymyślać | Pliki wiedzy | Aktualizuj pliki, nie prompty |
| Przykłady głosu/formatu | Pliki wiedzy | Pokazuj, nie opisuj |
| Powtarzalne zadania | Zapisane prompty | Używaj ponownie w rozmowach |

---

## ✅ Sprawdzenie

- [ ] Twój Projekt ma instrukcje **i** co najmniej jeden plik wiedzy.
- [ ] Asystent odwołał się do faktu z pliku.
- [ ] Zapisałeś co najmniej dwa prompty przepływów.

---

## 🎯 Zadanie

Zbuduj **drugi** Projekt dla innego realnego zadania w Twoim życiu (nauka, dodatkowy biznes, hobby). Wykorzystaj wzorzec trzech warstw: rola/zasady → pliki wiedzy → zapisane przepływy.

---

## 💡 Najważniejsze wnioski

- Mocny Projekt = **zachowanie (instrukcje) + wiedza (pliki) + przepływy (prompty)**, rozdzielone.
- Umieść fakty w plikach, aby Claude przestał zgadywać, a instrukcje zostały krótkie.
- Popraw słabą *warstwę*, nie cały prompt.

🌐 [English](../../en/track-a/01-projects-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)
