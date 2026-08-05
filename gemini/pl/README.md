# Naucz się AI z Gemini — 10-minutowe lekcje dla Windows

🌐 **Język:** [English](../en/README.md) · **Polski** · [↩ Strona kursu](../README.md) · [↩ Wszystkie kursy](../../README.md)

Praktyczny kurs dla początkujących, który uczy, jak **używać AI opartego na Google Gemini** — od pierwszej rozmowy w przeglądarce po pisanie kodu rozmawiającego z Gemini z poziomu Pythona, PowerShell, VS Code i wiersza poleceń.

Każda lekcja zajmuje około **10 minut**. Każda zawiera:

- 🧠 **Teorię** — pomysł wyjaśniony prostym językiem
- 🛠️ **Praktykę** — kroki krok po kroku na Twoim komputerze z **Windows**
- ✅ **Sprawdzenie** — jak poznać, że się udało
- 🎯 **Zadanie** — małe ćwiczenie utrwalające

Nie potrzebujesz wcześniejszego doświadczenia w programowaniu. Wszystko instalujemy razem. Wielki plus Gemini: **Google AI Studio ma darmowy poziom**, więc większość kursu zrobisz bez wydawania grosza.

---

## Jak korzystać z kursu

1. Czytaj lekcje **po kolei** — każda opiera się na poprzedniej.
2. Wykonuj sekcję **Praktyka** na własnym komputerze. Samo czytanie nie wystarczy.
3. Wszystkie bloki kodu są gotowe do **skopiowania**. Szukaj przycisku kopiowania w rogu bloku kodu na GitHubie.
4. Utknąłeś? Zapytaj Gemini! Wklej komunikat błędu i zapytaj „co to znaczy i jak to naprawić na Windows?”.

---

## Program kursu

### Część 1 — Podstawy (bez kodowania)

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 01 | [Czym jest AI i czym jest Gemini?](lessons/01-czym-jest-ai-i-gemini.md) | Ogólny obraz prostymi słowami |
| 02 | [Twoja pierwsza rozmowa z Gemini](lessons/02-pierwsza-rozmowa.md) | Używaj Gemini w sieci z kontem Google |
| 03 | [Podstawy tworzenia promptów](lessons/03-podstawy-promptow.md) | Jak pytać, aby dostać świetne odpowiedzi |
| 04 | [Praca z plikami i obrazami](lessons/04-pliki-i-obrazy.md) | Gemini jest natywnie multimodalny |

### Część 2 — Gemini na co dzień

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 05 | [Gemini w Chrome i Google](lessons/05-gemini-w-chrome-i-google.md) | Panel boczny, Wyszukiwarka i Workspace |
| 06 | [Codzienne zadania z Gemini](lessons/06-codzienne-zadania.md) | Realne przepływy: e-maile, podsumowania, planowanie |
| 07 | [Gems: Twoi własni asystenci AI](lessons/07-gems-wlasni-asystenci.md) | Osobowości i instrukcje wielokrotnego użytku |

### Część 3 — Twój pierwszy kod (wszystko instalujemy)

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 08 | [Instalacja Pythona na Windows](lessons/08-instalacja-python.md) | Uruchom poprawnie Python + pip |
| 09 | [Zdobądź klucz API Google AI Studio](lessons/09-klucz-api.md) | Darmowy klucz, dzięki któremu kod używa Gemini |
| 10 | [Twój pierwszy skrypt w Pythonie z Gemini](lessons/10-python-pierwszy-skrypt.md) | Wywołaj Gemini z Pythona |
| 11 | [Wywołaj Gemini z PowerShell](lessons/11-powershell.md) | Bez Pythona — tylko Windows PowerShell |

### Część 4 — Kodowanie z AI jako partnerem

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 12 | [VS Code + Gemini Code Assist](lessons/12-vscode-gemini-code-assist.md) | Darmowa pomoc AI w popularnym edytorze |
| 13 | [Gemini CLI w terminalu](lessons/13-gemini-cli.md) | AI, które edytuje pliki z wiersza poleceń |
| 14 | [Zbuduj mini projekt z AI](lessons/14-mini-projekt.md) | Prawdziwy „asystent notatek AI” |

### Część 5 — Wyższy poziom

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 15 | [Ugruntowanie w Wyszukiwarce Google](lessons/15-grounding-google-search.md) | Pozwól Gemini sprawdzać rzeczy na żywo |
| 16 | [Prompt engineering, który działa](lessons/16-prompt-engineering.md) | Wzorce używane przez profesjonalistów |
| 17 | [Koszty, limity, prywatność i bezpieczeństwo](lessons/17-koszty-bezpieczenstwo.md) | Darmowy vs płatny; używaj AI odpowiedzialnie |
| 18 | [Co dalej](lessons/18-co-dalej.md) | Twoja mapa drogowa po kursie |

---

## Narzędzia, których dotkniesz

- **gemini.google.com** — Gemini w przeglądarce (Lekcja 2)
- **Google AI Studio** — darmowe klucze API i piaskownica (Lekcja 9)
- **Python** + biblioteka **google-genai** (Lekcja 10)
- **PowerShell** — już wbudowany w Windows (Lekcja 11)
- **VS Code** + **Gemini Code Assist** (Lekcja 12)
- **Gemini CLI** — asystent Google w wierszu poleceń (Lekcja 13)

---

## Szybki słowniczek (dodaj do zakładek)

| Termin | Znaczenie w jednym zdaniu |
|------|---------------------|
| **LLM** | Duży model językowy — „mózg”, który przewiduje tekst, jak Gemini |
| **Prompt** | Wiadomość/instrukcja, którą podajesz AI |
| **Token** | Kawałek tekstu (~¾ słowa). Koszt i limity liczy się w tokenach |
| **API** | Sposób, w jaki Twój kod rozmawia z Gemini przez internet |
| **Klucz API** | Tajne hasło identyfikujące Twój kod wobec Google |
| **Model** | Konkretna wersja Gemini (np. Pro, Flash, Flash-Lite) |
| **Okno kontekstu** | Ile tekstu Gemini widzi naraz (u Gemini jest bardzo duże) |
| **Multimodalny** | Rozumie tekst, obrazy, dźwięk i więcej w jednym modelu |
| **Grounding (ugruntowanie)** | Łączenie odpowiedzi z żywymi źródłami jak Wyszukiwarka Google |
| **Halucynacja** | Gdy AI podaje coś błędnego jako prawdę |

---

## Zacznij tutaj 👉 [Lekcja 01 — Czym jest AI i czym jest Gemini?](lessons/01-czym-jest-ai-i-gemini.md)

*To materiał edukacyjny. Ekrany i nazwy menu w produktach zmieniają się z czasem — jeśli przycisk się przesunął, otaczające kroki nadal obowiązują, a zawsze możesz zapytać Gemini „gdzie teraz jest X?”.*
