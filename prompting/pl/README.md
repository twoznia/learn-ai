# Inżynieria promptów — lekcje niezależne od dostawcy

🌐 **Język:** [English](../en/README.md) · **Polski** · [↩ Strona kursu](../README.md) · [↩ Wszystkie kursy](../../README.md)

Praktyczny kurs, który uczy **pisać prompty niezawodnie działające** — z dowolnym czatem AI (Claude, Gemini lub ChatGPT). Od anatomii dobrego promptu przez przykłady few-shot, chain-of-thought, osadzanie przeciw halucynacjom, po testowanie promptów jak inżynier. ~10–12 minut na lekcję.

Każda lekcja ma:

- 🧠 **Teoria** — idea, wyjaśniona prosto
- 🛠️ **Praktyka** — prompty, które sam/a uruchamiasz w dowolnym czacie AI
- ✅ **Sprawdzian** — jak poznać, że zadziałało
- 🎯 **Praca domowa** — drobne zadanie utrwalające
- 💡 **Najważniejsze wnioski**

Umiejętności są **niezależne od dostawcy** — każda technika działa w Claude, Gemini i ChatGPT. Zaczyna łatwo i stopniowo się pogłębia; bez kodowania.

---

## Jak korzystać z kursu

1. Rób lekcje **po kolei** — każda buduje na poprzedniej.
2. Uruchamiaj każdy prompt z **Praktyki** sam/a w używanym czacie AI.
3. Prowadź dziennik **`my-prompts.md`** (Lekcja 1) — na koniec będziesz mieć bibliotekę wielokrotnego użytku.
4. Wypróbuj prompty na więcej niż jednym dostawcy, jeśli możesz — obserwuj, jak umiejętności się przenoszą.

---

## Program

### Część 1 — Podstawy

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 01 | [Czym jest inżynieria promptów?](lessons/01-czym-jest-inzynieria-promptow.md) | Jak LLM-y czytają prompty; czemu umiejętności się przenoszą |
| 02 | [Anatomia mocnego promptu](lessons/02-anatomia-promptu.md) | Rola, zadanie, kontekst, format, ograniczenia |
| 03 | [Bądź konkretny: klarowność i precyzja](lessons/03-badz-konkretny.md) | Usuń miejsce na błędne zgadywanie |
| 04 | [Kontekst i okno kontekstowe](lessons/04-kontekst-i-okno-kontekstowe.md) | Dostarcz, co potrzebne, wytnij szum |

### Część 2 — Techniki podstawowe

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 05 | [Struktura i formatowanie](lessons/05-struktura-i-formatowanie.md) | Ograniczniki, sekcje, kształt wyniku |
| 06 | [Few-shot](lessons/06-few-shot.md) | Przykłady, które sterują wzorcem |
| 07 | [Role i prompty systemowe](lessons/07-role-i-prompty-systemowe.md) | Persony i stałe instrukcje |
| 08 | [Rozumowanie krok po kroku](lessons/08-rozumowanie-krok-po-kroku.md) | Chain-of-thought przy trudnych problemach |
| 09 | [Dekompozycja i łańcuchy](lessons/09-dekompozycja-i-lancuchy.md) | Rozbij zadania; podaj wynik do wejścia |

### Część 3 — Niezawodność

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 10 | [Kontrola wyniku](lessons/10-kontrola-wyniku.md) | Długość, ton, tabele, JSON/schemat |
| 11 | [Ograniczanie halucynacji](lessons/11-ograniczanie-halucynacji.md) | Osadź, cytuj i weryfikuj |
| 12 | [Autokrytyka i iteracja](lessons/12-autokrytyka-i-iteracja.md) | Traktuj odpowiedzi jak szkice do dopracowania |
| 13 | [Praca z długimi dokumentami](lessons/13-dlugie-dokumenty.md) | Wskazuj, warstwuj, dziel, cytuj |

### Część 4 — Zastosowania i profesjonalizm

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 14 | [Biblioteka wzorców promptów](lessons/14-biblioteka-wzorcow-promptow.md) | Sparametryzowane, przetestowane szablony |
| 15 | [Ewaluacja i testowanie promptów](lessons/15-ewaluacja-promptow.md) | Rubryki, zestawy testowe, porównanie A/B |
| 16 | [Bezpieczeństwo i podsumowanie](lessons/16-bezpieczenstwo-i-podsumowanie.md) | Prompt injection, weryfikacja, mistrzowski prompt |

---

## Szybki słowniczek (do zakładek)

| Termin | Znaczenie w jednej linii |
|------|---------------------|
| **Prompt** | Instrukcje, które dajesz AI |
| **Kontekst** | Wszystko, co AI widzi w bieżącej rozmowie |
| **Okno kontekstowe** | Ile tekstu model może utrzymać naraz |
| **Zero-shot** | Opis zadania bez przykładów |
| **Few-shot** | Danie kilku przykładów wejście→wyjście |
| **Chain-of-thought** | Proszenie modelu o rozumowanie krok po kroku |
| **Prompt systemowy** | Stała instrukcja stosowana do każdej wiadomości |
| **Osadzanie** | Sprawianie, by odpowiedzi opierały się na dostarczonych źródłach |
| **Halucynacja** | Model podający coś fałszywego jako prawdę |
| **Prompt injection** | Ukryte instrukcje w niezaufanej treści |

---

## Zacznij tutaj 👉 [Lekcja 01 — Czym jest inżynieria promptów?](lessons/01-czym-jest-inzynieria-promptow.md)

*Materiał edukacyjny. Techniki są niezależne od dostawcy; konkretne ekrany i funkcje produktów zmieniają się z czasem, ale zasady obowiązują wszędzie.*
