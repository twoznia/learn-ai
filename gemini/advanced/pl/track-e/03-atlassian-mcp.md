# E3 — Atlassian z Gemini CLI (Jira i Confluence)

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: konto Atlassian, Gemini CLI

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Wstecz](02-github-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Azure z Gemini →](04-azure-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer Atlassian MCP** łączy Gemini z **Jirą** (zgłoszenia, tablice, sprinty) i **Confluence** (strony, dokumenty). Atlassian publikuje zdalny serwer MCP, który dodajesz do Gemini CLI i autoryzujesz przez OAuth.

Co odblokowuje:

- **Jira** — znajdź i streść zgłoszenia, twórz taski, przesuwaj je, komentuj.
- **Confluence** — przeszukuj strony, czytaj dokumenty, szkicuj nowe strony z notatek.

Ta sama dyscyplina co przy GitHubie: **najpierw czytaj, zapisuj z zatwierdzeniem, ściśle ograniczaj zakres.** Różnica to *dziedzina* — zgłoszenia i dokumenty zespołu zamiast kodu.

> Zdalny serwer MCP Atlassiana i jego dokładny URL zapewnia Atlassian i mogą się zmieniać. Sprawdź aktualną dokumentację **„Atlassian Remote MCP Server”** po endpoint, potem dodaj go do Gemini CLI.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Dodaj serwer Atlassian

Dodaj serwer MCP Atlassiana do CLI (użyj aktualnego URL/polecenia z dokumentacji Atlassiana):

```powershell
gemini mcp add atlassian -- <polecenie lub URL z dokumentacji Atlassiana>
```

Przejdź logowanie OAuth, o które poprosi; zatwierdź dostęp do serwisu Jira/Confluence.

> Możesz też dodać go pod `mcpServers` w `.gemini/settings.json`. Uruchom `gemini mcp --help` po opcje serwera zdalnego (URL).

### Krok 2 — Potwierdź i czytaj Jirę

```text
/mcp
```

Potem zacznij tylko-odczyt:

```text
Pokaż otwarte zgłoszenia Jira przypisane do mnie, od najnowszych, ze statusem i priorytetem.
```
```text
Streść bieżący sprint projektu <KLUCZ>: zrobione, w toku, zablokowane.
```

Gemini pobiera zgłoszenia na żywo i daje podsumowanie gotowe na stand-up.

### Krok 3 — Utwórz ticket Jira (z zatwierdzeniem)

```text
Utwórz task Jira w projekcie <KLUCZ>: „Zaktualizuj checklistę onboardingu dla Windows”,
priorytet Medium, z 3-punktowym opisem. Pokaż szkic i poczekaj na OK.
```

Gemini szkicuje, **pyta najpierw**, potem zakłada i zwraca klucz/link.

### Krok 4 — Przeszukaj i użyj Confluence

```text
Przeszukaj Confluence po naszą stronę „Proces wydania” i streść kroki jako listę.
```

Potem twórz na jej bazie:

```text
Naszkicuj nową stronę Confluence „Proces wydania — szybki przewodnik” z tej listy.
Pokaż mi szkic przed utworzeniem czegokolwiek.
```

### Krok 5 — Przepływ między narzędziami

```text
Dla projektu <KLUCZ> wypisz zgłoszenia rozwiązane w tym tygodniu, potem naszkicuj
krótką stronę Confluence „Aktualizacja tygodniowa”. Zapytaj przed utworzeniem strony.
```

Prawdziwe zadanie raportowe, od początku do końca, w terminalu.

---

## 🧩 Przydatne ruchy Atlassian

| Poproś o… | Dostajesz |
|----------|---------|
| „Moje otwarte zgłoszenia Jira” / „status sprintu” | Natychmiastowy triage / notatki |
| „Utwórz task Jira (zapytaj)” | Naszkicowane, zatwierdzone, założone |
| „Przeszukaj Confluence po <temat>” | Właściwa strona, streszczona |
| „Naszkicuj stronę Confluence z notatek” | Czysty dokument, po zatwierdzeniu |
| „Aktualizacja tygodniowa z rozwiązanych” | Auto-naszkicowany raport |

> ⚠️ **Zakres:** podłącz tylko serwis, którego potrzebujesz, preferuj odczyt podczas nauki, zatwierdzaj każdy zapis.

---

## ✅ Sprawdzenie

- [ ] Dodałeś serwer Atlassian MCP i widzisz go pod `/mcp`.
- [ ] Streściłeś prawdziwe zgłoszenia Jira lub sprint.
- [ ] Utworzyłeś ticket Jira lub stronę Confluence **po** zatwierdzeniu szkicu.
- [ ] Uruchomiłeś jeden przepływ obejmujący Jirę **i** Confluence.

---

## 🎯 Zadanie

Użyj Atlassiana do cotygodniowej roboty: pobierz otwarte zgłoszenia, naszkicuj jeden ticket (z zatwierdzeniem) i wygeneruj krótką stronę statusu z rozwiązanej pracy tygodnia.

---

## 💡 Najważniejsze wnioski

- **Serwer Atlassian MCP** łączy Gemini CLI z **Jirą** i **Confluence** — dodaj i autoryzuj przez OAuth.
- Ta sama dyscyplina co GitHub: **najpierw czytaj, zapisuj z zatwierdzeniem, ograniczaj do jednego serwisu**.
- Nagrodą są **przepływy między narzędziami** — rozwiązane zgłoszenia Jira → naszkicowana aktualizacja Confluence.

🌐 [English](../../en/track-e/03-atlassian-mcp.md) · [← Wstecz](02-github-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Azure z Gemini →](04-azure-mcp.md)
