# Projekt końcowy — Zbuduj agenta Drugiego Mózgu

🌐 **Język:** [English](../en/README.md) · **Polski** · [↩ Strona projektu](../README.md) · [↩ Wszystkie kursy](../../README.md)

Projekt końcowy spinający całe repo. **Zbudujesz prawdziwego agenta AI** — **Drugi Mózg**, który przechwytuje Twoje notatki, przeszukuje je i odpowiada na pytania osadzone w Twojej własnej wiedzy — działającego na Twoim **abonamencie Claude Pro/Max** (bez płatnego API), w całości na Twoim PC z Windows.

Po drodze łączysz wielkie idee z pozostałych kursów:

- **Inżynieria promptów** — docstringi narzędzi i opisy Skilli, które czynią agenta niezawodnym.
- **MCP z narzędziami** — własny serwer Python, który budujesz, by agent mógł czytać i zapisywać notatki.
- **Skille** — spakowana wiedza kształtująca, jak agent robi notatki i przegląda tydzień.
- **Przepływ GitHub** — testowanie, README i wydanie projektu.

Na koniec masz działającego agenta, którego naprawdę zachowasz — i umiejętności, by budować więcej.

---

## Co zbudujesz

```
Ty ⇄ Claude Code (agent) ── ładuje ──▶ Skille (note-style, weekly-review)
              │
              └── wywołuje narzędzia (MCP) ──▶ Twój serwer Python ──▶ notes/ (Markdown)
```

- **Agent:** Claude Code, na Twoim abonamencie (bez klucza API).
- **Narzędzia:** `save_note`, `search_notes`, `get_note`, `list_notes` — serwer FastMCP, który piszesz.
- **Skille:** note-style (jak przechwytywać) + weekly-review (przepływ).
- **Dane:** zwykłe notatki Markdown na Twoim dysku — darmowe, prywatne, przenośne.

---

## Wymagania wstępne

Pomocne (nie wszystkie wymagane) przed startem:

- Abonament **Claude Pro lub Max** (agent na nim działa — bez klucza API).
- Zainstalowane **Node.js** i **Python** (kurs podstawowy omawia oba).
- Podstawowa swoboda z **PowerShell** i folderem plików.
- Zalecane tło: **[kurs Inżynierii promptów](../../prompting/pl/README.md)** oraz **Claude zaawansowany** Ścieżki D–E (Skille, MCP, Claude Code). Ten projekt wprowadza je w praktykę.

---

## Budowa (8 lekcji)

| # | Lekcja | Będziesz… |
|---|--------|---------|
| 01 | [Przegląd i architektura](lessons/01-przeglad-i-architektura.md) | Widzieć, jak agent + narzędzia + Skille + notatki pasują |
| 02 | [Skonfiguruj agenta](lessons/02-skonfiguruj-agenta.md) | Zainstalować Claude Code na abonamencie |
| 03 | [Zaprojektuj Drugi Mózg](lessons/03-zaprojektuj-drugi-mozg.md) | Zdecydować o modelu notatki, narzędziach, Skillach |
| 04 | [Zbuduj serwer MCP](lessons/04-zbuduj-serwer-mcp.md) | Napisać cztery narzędzia notatek w Pythonie |
| 05 | [Podłącz i przetestuj narzędzia](lessons/05-podlacz-i-przetestuj-narzedzia.md) | Połączyć serwer z agentem; wywołać każde narzędzie |
| 06 | [Napisz swoje Skille](lessons/06-napisz-swoje-skille.md) | Napisać Skille note-style + weekly-review |
| 07 | [Uruchom agenta](lessons/07-uruchom-agenta.md) | Przechwytywanie, osadzone przypominanie, przegląd |
| 08 | [Testuj, utwardź i wydaj](lessons/08-testuj-utwardz-i-wydaj.md) | Uczynić bezpiecznym, udokumentować, wrzucić na GitHub |

---

## Zacznij tutaj 👉 [Projekt końcowy 01 — Przegląd i architektura](lessons/01-przeglad-i-architektura.md)

*Materiał edukacyjny. Nazwy produktów i szczegóły CLI zmieniają się z czasem — architektura (agent + narzędzia MCP + Skille + lokalne notatki) nadal obowiązuje. Sprawdź bieżącą dokumentację Claude Code, MCP i Skilli, gdy polecenie się przesunęło.*
