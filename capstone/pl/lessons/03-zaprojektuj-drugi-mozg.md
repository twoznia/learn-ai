# Projekt końcowy 03 — Zaprojektuj Drugi Mózg

⏱️ **13 minut** · Poziom: Projekt końcowy · Wymagania: konfiguracja z Lekcji 2

🌐 [English](../../en/lessons/03-design-your-second-brain.md) · [← Poprzednia](02-skonfiguruj-agenta.md) · [Strona projektu](../README.md) · [Dalej: Zbuduj serwer MCP →](04-zbuduj-serwer-mcp.md)

---

## 🧠 Teoria (5 min)

Przed pisaniem kodu — **zaprojektuj**. Trochę planowania tutaj czyni budowę w Lekcji 4 prostą. Decydujemy o trzech rzeczach: **modelu notatki**, **narzędziach** i **Skillach**.

### Model notatki

Każda notatka to jeden **plik Markdown** w `notes\` z małym nagłówkiem **frontmatter**:

```markdown
---
title: Sync zespołu — priorytety Q3
tags: [work, meeting]
created: 2026-08-07
---

Uzgodniliśmy skupienie na onboardingu. Właściciel: ja. Follow-up w przyszłym tygodniu.
```

Zwykłe pliki znaczą, że Twój Drugi Mózg jest **przejrzysty, przenośny i Twój** — czytelny bez żadnej specjalnej aplikacji.

### Narzędzia (co udostępnia serwer MCP)

Cztery narzędzia pokrywają przechwytywanie i przypominanie. Zauważ, że każde ma jasną **nazwę**, **wejścia** i **wyjście** — oraz precyzyjny **docstring**, bo tak agent wie, kiedy go użyć (prosto z kursu Inżynierii promptów):

| Narzędzie | Wejścia | Zwraca | Zadanie |
|------|--------|---------|-----|
| `save_note` | title, content, tags | ścieżkę zapisanego pliku | Przechwyć nową notatkę |
| `search_notes` | query | pasujące notatki (tytuł + fragment) | Znajdź istotne notatki |
| `get_note` | title | pełną treść notatki | Przeczytaj jedną notatkę |
| `list_notes` | tag (opcjonalnie) | tytuły notatek | Przeglądaj/przegląd |

### Skille (wiedza, którą agent auto-ładuje)

- **note-style** — jak napisać dobrą notatkę: jasny tytuł, właściwe tagi, dzielenie dużych zrzutów na osobne notatki. Ładuje się, gdy agent *tworzy* notatki.
- **weekly-review** — przepływ: zbierz notatki tygodnia, znajdź motywy, wydobądź otwarte pętle i zadania, zaproponuj kolejne działania. Ładuje się, gdy prosisz o przegląd.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Napisz kontrakty narzędzi

W pliku roboczym napisz jedno precyzyjne zdanie na narzędzie opisujące dokładnie, co robi i zwraca. Przykład:

```text
save_note(title, content, tags): Zapisz nową notatkę jako plik Markdown z
frontmatter (tytuł, tagi, data utworzenia). Zwraca ścieżkę pliku. Użyj, gdy
użytkownik chce przechwycić informację.
```

Te zdania staną się Twoimi **docstringami** w Lekcji 4 — a dobre docstringi to, co sprawia, że agent wywoła właściwe narzędzie.

### Krok 2 — Zdecyduj o taksonomii tagów

Wybierz 5–8 startowych tagów pasujących do *Twojego* życia: np. `work`, `idea`, `person`, `decision`, `learning`, `todo`. Mały, spójny zestaw czyni wyszukiwanie i przegląd znacznie lepszymi niż dowolne tagi.

### Krok 3 — Naszkicuj reguły note-style

Napisz 4–5 reguł dobrej notatki (wkleisz je do Skilla w Lekcji 6):

```text
- Jedna idea na notatkę; dziel duże zrzuty.
- Tytuł to konkretna, wyszukiwalna fraza.
- Taguj 1–3 tagami z taksonomii.
- Zakończ linią akcji, jeśli jest follow-up („TODO: …").
```

### Krok 4 — Naszkicuj przepływ weekly-review

Wypisz kroki, jakich chcesz:

```text
1. Wylistuj notatki utworzone w tym tygodniu.
2. Zgrupuj je w motywy.
3. Wyciągnij wszystkie linie TODO.
4. Zaproponuj 3 priorytety na przyszły tydzień.
```

### Krok 5 — Potwierdź, że wszystko darmowe i lokalne

Wszystko czyta/zapisuje lokalne pliki, a agent działa na abonamencie. Bez usług zewnętrznych, bez kluczy API, bez kosztu poza planem.

---

## 🧩 Twój projekt w skrócie

| Warstwa | Twoja decyzja |
|-------|---------------|
| Model notatki | Markdown + frontmatter (tytuł, tagi, created) |
| Narzędzia | save / search / get / list notes |
| Tagi | Twoja taksonomia 5–8 |
| Skill note-style | Twoje 4–5 reguł notatki |
| Skill weekly-review | Twoje kroki przeglądu |

---

## ✅ Sprawdzian

- [ ] Napisałeś/aś jednozdaniowy kontrakt (przyszły docstring) dla każdego z 4 narzędzi.
- [ ] Wybrałeś/aś małą taksonomię tagów.
- [ ] Naszkicowałeś/aś reguły note-style.
- [ ] Naszkicowałeś/aś kroki weekly-review.

---

## 🎯 Praca domowa

Sfinalizuj projekt w pliku `DESIGN.md` w projekcie. To Twój plan na kolejne lekcje — i świetny przykład nawyku „projektuj przed budową", który sprawia, że projekty wspierane AI idą gładko.

---

## 💡 Najważniejsze wnioski

- Najpierw projektuj: **model notatki**, cztery **narzędzia** i dwa **Skille**.
- **Docstringi** narzędzi (z Twoich jednozdaniowych kontraktów) to, jak agent wybiera właściwe narzędzie — pisz je precyzyjnie.
- Mała, spójna **taksonomia tagów** i jasne **reguły notatek** czynią wyszukiwanie i przegląd znacznie lepszymi.

🌐 [English](../../en/lessons/03-design-your-second-brain.md) · [← Poprzednia](02-skonfiguruj-agenta.md) · [Strona projektu](../README.md) · [Dalej: Zbuduj serwer MCP →](04-zbuduj-serwer-mcp.md)
