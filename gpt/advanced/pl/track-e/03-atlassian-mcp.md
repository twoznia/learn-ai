# E3 — Atlassian w Codex CLI (Jira i Confluence)

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: konto Atlassian, Codex CLI

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Poprzedni](02-github-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Azure w Codeksie →](04-azure-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer MCP Atlassian** łączy GPT z **Jirą** (zgłoszenia, tablice, sprinty) i **Confluence** (strony, dokumenty). Atlassian publikuje zdalny serwer MCP, który dodajesz do Codex CLI i autoryzujesz przez OAuth.

Co odblokowuje:

- **Jira** — znajdź i podsumuj zgłoszenia, twórz zadania, przenoś je, komentuj.
- **Confluence** — przeszukuj strony, czytaj dokumenty, szkicuj nowe strony z Twoich notatek.

Ta sama dyscyplina co przy GitHubie: **najpierw czytaj, zapisuj za zatwierdzeniem, ograniczaj ściśle zakres.** Różnica to *dziedzina* — zgłoszenia projektowe i dokumenty zespołu zamiast kodu.

> Zdalny serwer MCP Atlassian i jego dokładny URL zapewnia Atlassian i mogą się zmienić. Sprawdź bieżącą dokumentację **„Atlassian Remote MCP Server"** po endpoint, potem dodaj go do Codex CLI.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Dodaj serwer Atlassian

Dodaj serwer MCP Atlassian do Codeksa (użyj bieżącego URL-a/komendy z dokumentacji Atlassian):

```powershell
codex mcp add atlassian -- <komenda lub URL z dokumentacji Atlassian>
```

Dokończ logowanie OAuth, o które prosi; zatwierdź dostęp do Twojej witryny Jira/Confluence.

> Możesz go też dodać pod `[mcp_servers.atlassian]` w `~/.codex/config.toml`. Uruchom `codex mcp --help` po opcje serwera zdalnego (URL).

### Krok 2 — Potwierdź i czytaj Jirę

```text
/mcp
```

Potem zacznij tylko-do-odczytu:

```text
Pokaż otwarte zgłoszenia Jira przypisane do mnie, od najnowszych, ze statusem i priorytetem.
```
```text
Podsumuj bieżący sprint projektu <KEY>: zrobione, w toku i zablokowane.
```

GPT pobiera zgłoszenia na żywo i daje Ci podsumowanie gotowe na stand-up.

### Krok 3 — Utwórz zadanie w Jirze (za zatwierdzeniem)

```text
Utwórz zadanie Jira w projekcie <KEY>: „Zaktualizuj listę wdrożeniową dla Windows",
priorytet Średni, z 3-punktowym opisem. Pokaż szkic i poczekaj na moje OK.
```

GPT szkicuje je, **pyta najpierw**, potem zakłada i zwraca klucz/link.

### Krok 4 — Przeszukaj i użyj Confluence

```text
Przeszukaj Confluence w poszukiwaniu naszej strony „Proces wydania" i podsumuj kroki jako listę kontrolną.
```

Potem skomponuj z niej:

```text
Naszkicuj nową stronę Confluence „Proces wydania — szybka ściąga" z tej listy.
Pokaż mi szkic przed utworzeniem czegokolwiek.
```

### Krok 5 — Przepływ między narzędziami

```text
Dla projektu <KEY> wylistuj zgłoszenia rozwiązane w tym tygodniu, potem naszkicuj krótką
stronę Confluence „Aktualizacja tygodniowa" je podsumowującą. Zapytaj przed utworzeniem strony.
```

Prawdziwe zadanie raportowe, od początku do końca, w terminalu.

---

## 🧩 Przydatne ruchy z Atlassian

| Poproś o… | Dostajesz |
|----------|---------|
| „Moje otwarte zgłoszenia Jira" / „status sprintu" | Natychmiastowa segregacja / notatki na stand-up |
| „Utwórz zadanie Jira (zapytaj najpierw)" | Naszkicowane, zatwierdzone, założone |
| „Przeszukaj Confluence pod kątem <temat>" | Właściwa strona, podsumowana |
| „Naszkicuj stronę Confluence z tych notatek" | Czysty dokument, po zatwierdzeniu |
| „Aktualizacja tygodniowa z rozwiązanych zgłoszeń" | Auto-naszkicowany raport |

> ⚠️ **Zakres:** podłącz tylko witrynę, której potrzebujesz, wolej odczyt podczas nauki i zatwierdzaj każdy zapis.

---

## ✅ Sprawdzian

- [ ] Dodałeś/aś serwer MCP Atlassian i zobaczyłeś/aś go pod `/mcp`.
- [ ] Podsumowałeś/aś prawdziwe zgłoszenia Jira lub sprint.
- [ ] Utworzyłeś/aś zadanie Jira lub stronę Confluence **po** zatwierdzeniu szkicu.
- [ ] Uruchomiłeś/aś jeden przepływ obejmujący Jirę **i** Confluence.

---

## 🎯 Praca domowa

Użyj Atlassian do prawdziwej cotygodniowej roboty: pobierz swoje otwarte zgłoszenia, naszkicuj jedno zadanie, które wciąż zapominasz założyć (za zatwierdzeniem), i wygeneruj krótką stronę statusu z tygodniowo rozwiązanej pracy.

---

## 💡 Najważniejsze wnioski

- **Serwer MCP Atlassian** łączy Codex CLI z **Jirą** i **Confluence** — dodaj go i autoryzuj przez OAuth.
- Ta sama dyscyplina co przy GitHubie: **najpierw czytaj, zapisuj za zatwierdzeniem, ograniczaj do jednej witryny**.
- Nagrodą są **przepływy między narzędziami** — rozwiązane zgłoszenia Jira → naszkicowana aktualizacja Confluence.

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Poprzedni](02-github-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Azure w Codeksie →](04-azure-mcp.md)
