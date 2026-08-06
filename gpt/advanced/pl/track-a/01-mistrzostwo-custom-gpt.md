# A1 — Mistrzostwo Własnych GPT

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: ChatGPT (Własne GPT; zwykle plan płatny do tworzenia)

🌐 [English](../../en/track-a/01-custom-gpts-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym poznałeś **Własne GPT** jako „zapisany ChatGPT z własnymi instrukcjami”. Teraz potraktujemy Własny GPT jak **produkt, który projektujesz** — wyspecjalizowanego asystenta zachowującego się spójnie w jednym zadaniu.

Świetny Własny GPT ma trzy warstwy:

1. **Rola i zasady** (instrukcje) — *kim jest i jak się zachowuje*.
2. **Wiedza** (wysłane pliki) — *co zawsze wie*: fakty, styl, zasady, przykłady.
3. **Przepływy** (zapisane prompty + startery rozmowy) — *powtarzalne zadania*.

Błąd początkujących to jedna gigantyczna instrukcja. Ruch profesjonalisty to **oddzielenie stabilnej wiedzy od zachowania od zadań**.

---

## 🛠️ Praktyka (9 min)

Zbudujemy GPT **„Asystent e-maili do klientów”**.

### Krok 1 — Utwórz GPT + rola/zasady

W ChatGPT przejdź do **Explore GPTs → Create** (kreator GPT). Przełącz na kartę **Configure** i nazwij go **„E-maile klientów”**. W **Instructions** wklej:

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

### Krok 2 — Dodaj pliki wiedzy

W sekcji **Knowledge** wyślij `fakty-studia.txt`:

```text
FAKTY STUDIA (referencja — nie wymyślaj poza tym)
- Nazwa studia: Northlight Design
- Usługi: identyfikacja marki, projektowanie stron, druk
- Typowy start projektu: 2-3 tygodnie po zaliczce
- Nigdy nie podajemy ostatecznych cen e-mailem bez rozmowy zakresowej
```

Teraz odwołuje się do prawdziwych faktów zamiast zgadywać.

### Krok 3 — Dodaj przykład głosu + startery rozmowy

Wyślij e-mail, z którego jesteś dumny, jako `probka-glosu.txt`, i dodaj do Instructions:

```text
- Dopasuj głos z probka-glosu.txt: styl powitania, podpis, długość zdań.
```

Dodaj **Conversation starters** (przyciski, które widzą użytkownicy):
- „Naszkicuj odpowiedź na e-mail klienta”
- „Napisz przeprosiny za opóźnienie”

### Krok 4 — Zapisz przepływy

Zachowaj też w `moje-prompty.txt`:

```text
Naszkicuj odpowiedź na ten e-mail klienta. Użyj faktów studia i mojego głosu.

E-MAIL KLIENTA:
<wklej>

MOJA OGÓLNA INTENCJA:
<kilka słów>
```

### Krok 5 — Sprawdź warstwy razem

Otwórz swój GPT, wklej prawdziwy (lub zmyślony) e-mail i sprawdź: czy użył **faktu** z pliku? Czy dopasował **głos**? Czy przestrzegał **formatu**? Popraw słabą *warstwę* — zwykle plik wiedzy, nie instrukcje.

> Nie planujesz tworzyć GPT? Użyj **instrukcji własnych** (Settings → Personalization) dla globalnego zachowania i zapisz przepływy jako prompty. To samo myślenie trójwarstwowe.

---

## 🧩 Zasada projektowa

| Umieść to… | …w tej warstwie | Dlaczego |
|-----------|----------------|-----|
| Jak się zachowuje | Instrukcje | Rzadko się zmienia; krótkie |
| Fakty, których nie może wymyślać | Pliki wiedzy | Aktualizuj pliki, nie prompty |
| Przykłady głosu/formatu | Pliki wiedzy | Pokazuj, nie opisuj |
| Powtarzalne zadania | Prompty + startery | Używaj ponownie w rozmowach |

---

## ✅ Sprawdzenie

- [ ] Twój Własny GPT ma instrukcje **i** co najmniej jeden plik wiedzy.
- [ ] Odwołał się do faktu z pliku.
- [ ] Dodałeś startery rozmowy i zapisałeś prompt przepływu.

---

## 🎯 Zadanie

Zbuduj **drugi** Własny GPT (lub konfigurację instrukcji własnych) dla innego realnego zadania. Wykorzystaj wzorzec trzech warstw.

---

## 💡 Najważniejsze wnioski

- Mocny Własny GPT = **zachowanie + pliki wiedzy + przepływy**, rozdzielone.
- Umieść fakty w plikach, aby ChatGPT przestał zgadywać.
- Popraw słabą *warstwę*, nie cały prompt.

🌐 [English](../../en/track-a/01-custom-gpts-mastery.md) · [← Indeks ścieżki](../README.md) · [Dalej: Biblioteka promptów →](02-biblioteka-promptow.md)
