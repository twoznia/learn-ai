# Lekcja 01 — Czym jest inżynieria promptów?

⏱️ **10 minut** · Poziom: Początkujący · Wymagania: dowolny czat AI (Claude, Gemini lub ChatGPT)

🌐 [English](../../en/lessons/01-what-is-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Anatomia promptu →](02-anatomia-promptu.md)

---

## 🧠 Teoria (4 min)

**Inżynieria promptów** to umiejętność pisania instrukcji, które sprawiają, że AI robi to, czego naprawdę chcesz — niezawodnie. Ten sam model może dać niejasną, przeciętną odpowiedź albo ostrą i użyteczną; różnicą jest zwykle **prompt**.

By dobrze promptować, trzymaj prosty model tego, jak te modele działają:

- Czat AI to **duży model językowy (LLM)**, który przewiduje tekst. Mając Twoje słowa, kontynuuje je najbardziej prawdopodobnymi następnymi słowami.
- Nie ma **pamięci** między osobnymi czatami ani **ukrytej wiedzy o Twojej intencji** — ma tylko to, co jest w bieżącej rozmowie (**kontekst**).
- To **dopasowywacz wzorców, nie baza danych**. Potrafi być płynny i *błędny*. Twój prompt kształtuje wzorzec, który podąża.

Ponieważ dotyczy to *wszystkich* nowoczesnych LLM-ów, umiejętności z tego kursu **przenoszą się między dostawcami** — Claude, Gemini, ChatGPT i inne. Sformułowania i funkcje się różnią; zasady nie.

> Główna idea: nie „wyszukujesz", tylko **reżyserujesz**. Lepsza reżyseria daje lepszy występ.

---

## 🛠️ Praktyka (5 min)

### Krok 1 — Poczuj różnicę

Otwórz dowolny czat AI i wyślij ten niejasny prompt:

```text
Napisz coś o psach.
```

Potem wyreżyserowany:

```text
Napisz 4-zdaniowy wstęp do wpisu blogowego dla osób pierwszy raz mających psa,
ciepły i zachęcający w tonie, kończący się pytaniem zapraszającym do komentarzy.
```

Porównaj. Ten sam model — drugi prompt wykonał pracę.

### Krok 2 — Nazwij, co się zmieniło

Drugi prompt dodał **zadanie**, **odbiorcę**, **długość**, **ton** i **format**. To cała gra, a każdy element zbudujemy w tym kursie.

### Krok 3 — Wypróbuj ten sam prompt na dwóch modelach

Jeśli masz dostęp do więcej niż jednego (Claude / Gemini / ChatGPT), wyślij wyreżyserowany prompt do każdego. Zauważ, że *styl* się różni, ale oba podążają za Twoją reżyserią — dowód, że umiejętność się przenosi.

### Krok 4 — Załóż dziennik promptów

Utwórz notatkę `my-prompts.md`. Za każdym razem, gdy prompt dobrze zadziała, wklej go. Do Lekcji 14 będziesz mieć początek biblioteki wielokrotnego użytku.

---

## 🧩 Niejasny vs wyreżyserowany

| Niejasny prompt | Wyreżyserowany prompt |
|--------------|-----------------|
| „Napisz o psach" | „Napisz 4-zdaniowy wstęp dla osób pierwszy raz z psem, ciepły, kończący się pytaniem" |
| „Napraw to" | „Znajdź błąd powodujący X i wyjaśnij poprawkę w jednym akapicie" |
| „Podsumuj to" | „Podsumuj to w 5 punktach, które zabiegany menedżer przejrzy" |

---

## ✅ Sprawdzian

- [ ] Umiesz w jednym zdaniu wyjaśnić, co robi LLM (przewiduje tekst z kontekstu).
- [ ] Zobaczyłeś/aś, jak niejasny i wyreżyserowany prompt dają bardzo różne wyniki.
- [ ] Umiesz nazwać co najmniej trzy rzeczy, które określił wyreżyserowany prompt.
- [ ] Założyłeś/aś dziennik `my-prompts.md`.

---

## 🎯 Praca domowa

Weź jedną rzecz, o którą naprawdę zapytasz AI w tym tygodniu. Napisz ją dwa razy — raz jak zwykle, raz w pełni wyreżyserowaną (zadanie, odbiorca, długość, ton, format). Uruchom obie i zapisz lepszą do dziennika.

---

## 💡 Najważniejsze wnioski

- **Inżynieria promptów** to reżyserowanie LLM-a — to prompt, nie model, jest zwykle wąskim gardłem.
- LLM-y **przewidują tekst z bieżącego kontekstu**; to płynne dopasowywacze wzorców, które potrafią być pewnie w błędzie.
- Umiejętności **przenoszą się między Claude, Gemini i ChatGPT** — zasady ponad ciekawostki produktów.

🌐 [English](../../en/lessons/01-what-is-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Anatomia promptu →](02-anatomia-promptu.md)
