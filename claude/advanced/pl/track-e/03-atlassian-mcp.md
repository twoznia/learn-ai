# E3 — Atlassian MCP (Jira i Confluence)

⏱️ **15 minut** · Ścieżka: 🅴 Mistrzostwo MCP · Potrzebne: konto Atlassian (Jira i/lub Confluence)

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Wstecz](02-github-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Azure MCP →](04-azure-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer Atlassian MCP** łączy Claude z **Jirą** (zgłoszenia, tablice, sprinty) i **Confluence** (strony, dokumenty). Zwykle to **konektor zdalny** — hostowany przez Atlassian, włączany przez OAuth, nic do instalacji.

Co odblokowuje:

- **Jira** — znajdź i streść zgłoszenia, twórz taski, przesuwaj je po tablicy, komentuj.
- **Confluence** — przeszukuj strony, czytaj dokumenty, szkicuj nowe strony z notatek.

Wzorzec jest ten sam co przy GitHubie: **najpierw czytaj, zapisuj z zatwierdzeniem, ściśle ograniczaj zakres.** Różnica to *dziedzina* — zgłoszenia projektowe i dokumenty zespołu zamiast kodu.

> Zdalny serwer MCP Atlassiana i jego dokładny URL zapewnia Atlassian i mogą się zmieniać. Jeśli nie widzisz go w **Settings → Connectors**, poszukaj aktualnej dokumentacji Atlassiana **„Atlassian Remote MCP Server”** po endpoint i włącz jako własny konektor.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Podłącz Atlassian

1. Aplikacja Claude → **Settings → Connectors** → znajdź **Atlassian** → **Connect**.
2. Zaloguj przez OAuth; zatwierdź dostęp do swojego serwisu Jira/Confluence.
3. Jeśli go nie ma na liście, dodaj jako **własny konektor** używając opublikowanego URL serwera MCP Atlassiana.

### Krok 2 — Czytaj swoją Jirę

Zacznij tylko-odczyt, by zobaczyć działające narzędzia:

```text
Pokaż otwarte zgłoszenia Jira przypisane do mnie, od najnowszych, ze statusem i priorytetem.
```
```text
Streść, co jest w bieżącym sprincie projektu <KLUCZ>: co zrobione, w toku i zablokowane.
```

Claude pobiera zgłoszenia na żywo i daje podsumowanie gotowe na stand-up.

### Krok 3 — Utwórz zgłoszenie Jira (z zatwierdzeniem)

```text
Utwórz task Jira w projekcie <KLUCZ>: „Zaktualizuj checklistę onboardingu dla użytkowników Windows”,
priorytet Medium, z 3-punktowym opisem. Pokaż mi szkic i poczekaj na moje OK.
```

Claude szkicuje, **pyta najpierw**, potem zakłada i zwraca klucz/link zgłoszenia.

### Krok 4 — Przeszukaj i użyj Confluence

```text
Przeszukaj Confluence po naszą stronę „Proces wydania” i streść kroki jako listę.
```

Potem twórz na jej bazie:

```text
Naszkicuj nową stronę Confluence „Proces wydania — szybki przewodnik” z tej listy.
Pokaż mi szkic przed utworzeniem czegokolwiek.
```

Czytaj z jednej strony, napisz czystszą — z bramką człowieka.

### Krok 5 — Przepływ między narzędziami

Zwiąż Jirę i Confluence:

```text
Dla projektu <KLUCZ> wypisz zgłoszenia rozwiązane w tym tygodniu, potem naszkicuj
krótką stronę Confluence „Aktualizacja tygodniowa” streszczającą je. Zapytaj przed utworzeniem strony.
```

To prawdziwe zadanie raportowe zrobione od początku do końca w czacie.

---

## 🧩 Przydatne ruchy Atlassian MCP

| Poproś o… | Dostajesz |
|----------|---------|
| „Moje otwarte zgłoszenia Jira” / „status sprintu” | Natychmiastowy triage / notatki na stand-up |
| „Utwórz task Jira (zapytaj najpierw)” | Naszkicowane, zatwierdzone, założone |
| „Przeszukaj Confluence po <temat>” | Właściwa strona, streszczona |
| „Naszkicuj stronę Confluence z tych notatek” | Czysty dokument, po zatwierdzeniu |
| „Aktualizacja tygodniowa z rozwiązanych zgłoszeń” | Auto-naszkicowany raport |

> ⚠️ **Zakres:** podłącz tylko serwis Jira/Confluence, którego potrzebujesz, preferuj odczyt podczas nauki i zatwierdzaj zapisy (nowe zgłoszenia, edycje stron).

---

## ✅ Sprawdzenie

- [ ] Atlassian jest podłączony (konektor lub własny URL).
- [ ] Streściłeś prawdziwe zgłoszenia Jira lub sprint.
- [ ] Utworzyłeś zgłoszenie Jira lub stronę Confluence **po** zatwierdzeniu szkicu.
- [ ] Uruchomiłeś jeden przepływ obejmujący Jirę **i** Confluence.

---

## 🎯 Zadanie

Użyj Atlassian MCP do prawdziwej cotygodniowej roboty: pobierz swoje otwarte zgłoszenia, naszkicuj jedno zgłoszenie, które ciągle chcesz założyć (z zatwierdzeniem), i wygeneruj krótką stronę statusu z rozwiązanej pracy tego tygodnia.

---

## 💡 Najważniejsze wnioski

- Atlassian MCP łączy Claude z **Jirą** (zgłoszenia, sprinty) i **Confluence** (strony) — zwykle konektor zdalny OAuth.
- Ta sama dyscyplina co przy GitHubie: **najpierw czytaj, zapisuj z zatwierdzeniem, ograniczaj do jednego serwisu**.
- Nagrodą są **przepływy między narzędziami** — np. rozwiązane zgłoszenia Jira → naszkicowana aktualizacja Confluence.

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Wstecz](02-github-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Azure MCP →](04-azure-mcp.md)
