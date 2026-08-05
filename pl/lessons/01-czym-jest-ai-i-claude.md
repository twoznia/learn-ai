# Lekcja 01 — Czym jest AI i czym jest Claude?

⏱️ **10 minut** · Poziom: Początkujący · Bez instalacji

🌐 [English](../../en/lessons/01-what-is-ai-and-claude.md) · [← Strona kursu](../README.md) · [Dalej: Pierwsza rozmowa →](02-pierwsza-rozmowa.md)

---

## 🧠 Teoria (4 min)

### Co oznacza tu „AI”

Gdy dziś ludzie mówią **AI**, zwykle mają na myśli **duży model językowy (LLM)** — program komputerowy wytrenowany na ogromnych ilościach tekstu, aby **przewidywać kolejne słowa** w zdaniu. Ta prosta idea, zrealizowana na wielką skalę, tworzy coś, co potrafi pisać, streszczać, wyjaśniać, tłumaczyć i kodować.

Wyobraź sobie niezwykle oczytanego asystenta, który:

- przeczytał ogromną część publicznego internetu i wiele książek,
- świetnie radzi sobie z językiem, rozumowaniem i redagowaniem,
- ale **naprawdę nie „zna” faktów** — przewiduje prawdopodobny tekst, więc czasem może pewnie się mylić (to nazywa się **halucynacją**).

> 🔑 **Złota zasada z pierwszej lekcji:** AI to genialny asystent, a nie wyrocznia. Używaj go do szkicowania, wyjaśniania i przyspieszania — a potem weryfikuj wszystko, co ważne.

### Czym jest Claude

**Claude** to rodzina modeli AI tworzonych przez firmę **Anthropic**. Możesz korzystać z Claude na kilka sposobów, a ten kurs obejmuje je wszystkie:

| Sposób użycia Claude | Co to jest | Lekcja |
|-------------------|-----------|--------|
| **Claude.ai (sieć)** | Rozmowa w przeglądarce | 02 |
| **Claude Desktop** | Aplikacja dla Windows | 05 |
| **API** | Claude w Twoim własnym kodzie | 09–11 |
| **Claude Code** | AI edytujące kod w terminalu | 13 |

### Rodzina modeli Claude

Claude występuje w różnych rozmiarach. Wybierasz zależnie od zadania:

| Typ modelu | Najlepszy do | Charakter |
|------------|----------|------|
| **Haiku** | Szybkie, tanie, proste zadania | Szybki i lekki |
| **Sonnet** | Codzienna praca, świetny balans | Niezawodny domyślny |
| **Opus** | Najtrudniejsze rozumowanie i kodowanie | Najbardziej zdolny |

Nie musisz zapamiętywać numerów wersji. Zapamiętaj: **Haiku = szybki**, **Sonnet = zrównoważony**, **Opus = najmądrzejszy**. W aplikacjach czatu Claude zwykle wybiera sensowny domyślny model za Ciebie.

### Tokeny (jednostka, którą liczy AI)

AI czyta i pisze w **tokenach** — kawałkach tekstu. Token to mniej więcej **¾ słowa**. „Hamburger” to może 3 tokeny; „the” to 1.

Dlaczego to ważne? Z dwóch powodów:

1. **Limity** — model widzi naraz tylko określoną liczbę tokenów (jego **okno kontekstu**).
2. **Koszt** — korzystając z API, płacisz za tokeny (drobne ułamki grosza). Więcej w Lekcji 17.

---

## 🛠️ Praktyka (4 min)

Nie potrzebujesz jeszcze konta. Zbudujmy intuicję.

1. Otwórz notatnik lub weź kartkę.
2. Zapisz **trzy zadania** ze swojego życia lub pracy, które dotyczą *słów*: pisanie, wyjaśnianie, streszczanie, planowanie lub wyszukiwanie. Przykłady:
   - „Napisz uprzejmą odpowiedź na e-mail od klienta.”
   - „Streść długi raport PDF.”
   - „Wyjaśnij prostymi słowami przepis podatkowy.”
3. Obok każdego napisz, czy zaufałbyś odpowiedzi AI **taką, jaka jest**, czy **ją zweryfikujesz** (podpowiedź: wszystko z liczbami, prawem, medycyną lub pieniędzmi → weryfikuj).

Zachowaj tę listę. Do Lekcji 6 będziesz robić wszystkie trzy z Claude.

---

## ✅ Sprawdzenie

Potrafisz odpowiedzieć w głowie:

- [ ] Czym jest LLM w jednym zdaniu? *(Program przewidujący tekst na podstawie wzorców, których się nauczył.)*
- [ ] Czym jest halucynacja? *(Gdy AI pewnie podaje coś fałszywego.)*
- [ ] Wymień trzy „rozmiary” Claude. *(Haiku, Sonnet, Opus.)*

---

## 🎯 Zadanie

W jednym zdaniu opisz **najbardziej irytujące powtarzalne zadanie tekstowe** w Twoim tygodniu. To zadanie jest Twoim celem — zautomatyzujesz je później w tym kursie.

---

## 💡 Najważniejsze wnioski

- AI = model językowy przewidujący tekst; genialny, ale nieomylny nie jest.
- Claude to rodzina modeli (Haiku/Sonnet/Opus), z której korzystasz przez sieć, aplikację lub kod.
- Zawsze weryfikuj to, co ważne.

🌐 [English](../../en/lessons/01-what-is-ai-and-claude.md) · [← Strona kursu](../README.md) · [Dalej: Pierwsza rozmowa →](02-pierwsza-rozmowa.md)
