# Projekt końcowy 01 — Przegląd i architektura

⏱️ **12 minut** · Poziom: Projekt końcowy · Wymagania: ciekawość (narzędzia konfigurujemy w następnej lekcji)

🌐 [English](../../en/lessons/01-overview-and-architecture.md) · [Strona projektu](../README.md) · [Dalej: Skonfiguruj agenta →](02-skonfiguruj-agenta.md)

---

## 🧠 Co zbudujesz

**Agent Drugiego Mózgu**: agent AI, który przechwytuje Twoje notatki, przeszukuje je i odpowiada na pytania **osadzone w Twojej własnej wiedzy** — działając na Twoim **abonamencie Claude Pro/Max** (bez płatnego API), w całości na Twoim PC z Windows.

Na koniec będziesz mieć prawdziwe, warte zachowania narzędzie *i* połączysz trzy wielkie idee z tych kursów:

- **Inżynieria promptów** — pisanie opisów narzędzi i instrukcji Skilli, które czynią agenta niezawodnym.
- **MCP z narzędziami** — własny serwer, który zbudujesz, pozwalający agentowi czytać i zapisywać Twoje notatki.
- **Skille** — spakowana wiedza kształtująca, *jak* agent robi notatki i przegląda Twój tydzień.

To projekt-nagroda. Jest prowadzony, ale Twój do zachowania i rozwijania.

---

## 🧩 Architektura

Cztery części współpracują:

```
        Ty (czat)
           │
           ▼
   ┌──────────────────┐   ładuje    ┌───────────────┐
   │   Claude Code    │◀───────────▶│    Skille     │
   │   (AGENT)        │   wiedza    │ note-style,   │
   │  na Claude Pro   │             │ weekly-review │
   └───────┬──────────┘             └───────────────┘
           │ wywołuje narzędzia (MCP)
           ▼
   ┌──────────────────┐  czyta/zapisuje   ┌───────────────┐
   │   serwer MCP     │──────────────────▶│  folder notes/ │
   │ (Twój Python)    │                   │  (Markdown)    │
   │ save/search/get  │                   │  dane Twojego  │
   │ /list notes      │                   │  Drugiego Mózgu│
   └──────────────────┘                   └───────────────┘
```

- **Agent** to **Claude Code** — planuje, decyduje, które narzędzie wywołać, i iteruje, z Twoim zatwierdzaniem akcji. Działa na Twoim **abonamencie**, bez klucza API.
- **Serwer MCP** to mały program **Python**, który *Ty* piszesz (używając FastMCP, jak w Claude zaawansowany Ścieżka E). Udostępnia **narzędzia** — `save_note`, `search_notes`, `get_note`, `list_notes` — działające na lokalnym folderze `notes\`.
- **Skille** to foldery z instrukcjami, które agent **auto-ładuje**, gdy istotne: Skill **note-style** (jak formatować i tagować notatki) i Skill **weekly-review** (przepływ pracy).
- **Twoje notatki** to zwykłe pliki **Markdown** na dysku — przejrzyste, przenośne i darmowe.

---

## 🗺️ Plan (8 lekcji)

| # | Lekcja | Będziesz… |
|---|--------|--------|
| 01 | Przegląd i architektura | Rozumieć części (ta lekcja) |
| 02 | Skonfiguruj agenta | Zainstalować Claude Code na abonamencie + Python |
| 03 | Zaprojektuj Drugi Mózg | Zdecydować o modelu notatki, narzędziach, Skillach |
| 04 | Zbuduj serwer MCP | Napisać 4 narzędzia notatek w Pythonie |
| 05 | Podłącz i przetestuj narzędzia | Połączyć serwer z agentem; wywołać każde narzędzie |
| 06 | Napisz swoje Skille | Napisać note-style + weekly-review |
| 07 | Uruchom agenta | Przechwytywać, wyszukiwać i odpowiadać z notatek |
| 08 | Testuj, utwardź i wydaj | Uczynić bezpiecznym, wrzucić na GitHub, rozwinąć |

---

## ✅ Sprawdzian

- [ ] Umiesz nazwać cztery części: agent, serwer MCP (narzędzia), Skille, notatki.
- [ ] Rozumiesz, że agent działa na Twoim **abonamencie** (bez klucza API).
- [ ] Wiesz, że narzędzia działają na **lokalnych plikach Markdown**.
- [ ] Umiesz wyjaśnić różnicę między **narzędziem** (akcja) a **Skillem** (wiedza).

---

## 🎯 Praca domowa

Naszkicuj *swój* Drugi Mózg na papierze. Co chcesz przechwytywać (pomysły, notatki ze spotkań, linki, decyzje)? Jakie pytania byś mu później zadał/a? Zachowaj szkic — zamienisz go w prawdziwy projekt w Lekcji 3.

---

## 💡 Najważniejsze wnioski

- Budujesz **agenta Drugiego Mózgu**: Claude Code + własny **serwer MCP (narzędzia)** + **Skille** + lokalne notatki Markdown.
- Działa na Twoim **abonamencie Claude Pro/Max** — bez płatnego API, wszystko na Twoim PC.
- **Narzędzia** dają agentowi *zasięg* (czytaj/zapisuj notatki); **Skille** dają *wiedzę* (jak robić notatki, jak przeglądać).

🌐 [English](../../en/lessons/01-overview-and-architecture.md) · [Strona projektu](../README.md) · [Dalej: Skonfiguruj agenta →](02-skonfiguruj-agenta.md)
