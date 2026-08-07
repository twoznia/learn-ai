# GitHub Copilot + VS Code — praktyczne lekcje pod Windows

🌐 **Język:** [English](../en/README.md) · **Polski** · [↩ Strona kursu](../README.md) · [↩ Wszystkie kursy](../../README.md)

Praktyczny kurs, który uczy, jak **naprawdę używać GitHub Copilota** z VS Code i GitHubem — od pierwszego uzupełnienia kodu przez AI po automatyczne przeglądy PR, generowane README i delegowanie całych zadań agentowi kodującemu Copilota. Pod Windows, gotowe do skopiowania kroki, ~10–13 minut na lekcję.

Każda lekcja ma:

- 🧠 **Teoria** — idea, wyjaśniona prosto
- 🛠️ **Praktyka** — krok po kroku / kopiuj-wklej na Twoim PC z **Windows**
- ✅ **Sprawdzian** — jak poznać, że zadziałało
- 🎯 **Praca domowa** — drobne zadanie utrwalające
- 💡 **Najważniejsze wnioski**

Zaczyna łatwo i stopniowo się pogłębia — bez wcześniejszego doświadczenia z Copilotem czy GitHubem. Wszystko instalujemy razem.

---

## Jak korzystać z kursu

1. Rób lekcje **po kolei** — każda buduje na poprzedniej.
2. Faktycznie rób **Praktykę** na własnym PC. Copilota uczysz się, używając go.
3. Wszystkie polecenia są gotowe do **skopiowania i wklejenia**.
4. Utknąłeś/aś? Zapytaj Copilota! Wklej błąd i zapytaj „co to znaczy i jak to naprawić na Windows?"

---

## Program

### Część 1 — Podstawy: Copilot w VS Code

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 01 | [Czym jest GitHub Copilot?](lessons/01-czym-jest-github-copilot.md) | Szeroki obraz, plany i logowanie |
| 02 | [Konfiguracja VS Code + Copilot](lessons/02-konfiguracja-vscode-i-copilot.md) | Instalacja, logowanie, pierwsze uzupełnienia |
| 03 | [Podstawy Copilot Chat](lessons/03-podstawy-copilot-chat.md) | Widok czatu, czat w linii, komendy ze slashem |
| 04 | [Dobre promptowanie Copilota](lessons/04-dobre-promptowanie-copilota.md) | Kontekst + intencja + ograniczenia |

### Część 2 — Codzienne kodowanie z Copilotem

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 05 | [Copilot Edits i tryb agenta](lessons/05-edits-i-tryb-agenta.md) | Skoordynowane zmiany wieloplikowe |
| 06 | [Testy, dokumentacja i refactoring](lessons/06-testy-dokumentacja-refactoring.md) | Generuj testy/dokumentację, refactoruj bezpiecznie |
| 07 | [Własne instrukcje i styl projektu](lessons/07-wlasne-instrukcje.md) | Stałe reguły `copilot-instructions.md` |
| 08 | [Dawanie Copilotowi kontekstu](lessons/08-kontekst-uczestnicy-referencje.md) | `@workspace`, `#file`, uczestnicy |

### Część 3 — Podstawy GitHuba

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 09 | [Podstawy Git i GitHub](lessons/09-podstawy-git-i-github.md) | Commit, push i Copilot jako korepetytor |
| 10 | [Gałęzie i pull requesty](lessons/10-galezie-i-pull-requesty.md) | Przepływ PR, od początku do końca |
| 11 | [Zgłoszenia, etykiety i projekty](lessons/11-zgloszenia-etykiety-projekty.md) | Śledź pracę, na której agent może działać |

### Część 4 — Optymalizacja PR-ów, przeglądów i dokumentacji

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 12 | [Świetne pull requesty](lessons/12-swietne-pull-requesty.md) | Tytuły i opisy generowane przez Copilota |
| 13 | [Automatyczny przegląd kodu](lessons/13-automatyczny-przeglad-kodu.md) | Przegląd Copilota w VS Code i na PR |
| 14 | [README i dokumentacja](lessons/14-readme-i-dokumentacja.md) | Generuj dokumentację zgodną z kodem |
| 15 | [Copilot na github.com](lessons/15-copilot-na-github-com.md) | Czat o repo i podsumowania PR w przeglądarce |

### Część 5 — Zaawansowane i automatyzacja

| # | Lekcja | Czego się nauczysz |
|---|--------|-------------------|
| 16 | [Agent kodujący Copilota](lessons/16-agent-kodujacy-copilot.md) | Przypisz zgłoszenie, dostań pull request |
| 17 | [Copilot CLI + GitHub Actions](lessons/17-copilot-cli-i-actions.md) | Pomoc w terminalu, CI i Autofix |
| 18 | [Koszty, limity i kolejne kroki](lessons/18-koszty-limity-i-kolejne-kroki.md) | Używaj odpowiedzialnie; Twoja mapa drogowa |

---

## Narzędzia, których dotkniesz

- **VS Code** — darmowy edytor kodu Microsoftu (Lekcja 2)
- Rozszerzenia **GitHub Copilot** + **Copilot Chat** (Lekcja 2)
- **Git** + **GitHub** — kontrola wersji i hosting (Lekcja 9)
- Rozszerzenie **GitHub Pull Requests** (opcjonalnie, Lekcja 10)
- **GitHub CLI / Copilot CLI** — pomoc w terminalu (Lekcja 17)
- **GitHub Actions** — automatyczne CI (Lekcja 17)

---

## Szybki słowniczek (do zakładek)

| Termin | Znaczenie w jednej linii |
|------|---------------------|
| **Uzupełnienie** | Szary „ghost text", który Copilot podpowiada podczas pisania |
| **Copilot Chat** | Rozmowa z Copilotem o Twoim kodzie (widok lub w linii) |
| **Tryb Edit / Agent** | Edycje wieloplikowe; zmiany kierowane celem |
| **Repo** | Projekt śledzony przez Git i hostowany na GitHubie |
| **Commit** | Zapisana migawka zmian |
| **Gałąź** | Równoległa kopia kodu do bezpiecznych zmian |
| **Pull request (PR)** | Propozycja scalenia gałęzi, z przeglądem |
| **CI** | Automatyzacja uruchamiająca testy na każdym PR |
| **Agent kodujący** | Copilot pracujący ze zgłoszenia, by otworzyć PR |

---

## Zacznij tutaj 👉 [Lekcja 01 — Czym jest GitHub Copilot?](lessons/01-czym-jest-github-copilot.md)

*Materiał edukacyjny. Ekrany i nazwy menu w produktach zmieniają się z czasem — jeśli przycisk się przesunął, otaczające kroki nadal obowiązują, a zawsze możesz zapytać Copilota „gdzie jest teraz X?".*
