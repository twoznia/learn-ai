# E2 — GitHub w Codex CLI

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: konto GitHub, Codex CLI

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Poprzedni](01-narzedzia-konektory-i-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Atlassian w Codeksie →](03-atlassian-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer MCP GitHuba** pozwala GPT pracować z Twoimi repozytoriami jak członek zespołu: czytać kod, przeglądać zgłoszenia i pull requesty, tworzyć zgłoszenia, otwierać PR-y i sprawdzać CI — przez wywołania narzędzi, które zatwierdzasz, wprost w Codex CLI.

Dodajesz go jako serwer MCP. GitHub publikuje oficjalny serwer MCP (endpoint `https://api.githubcopilot.com/mcp/`), są też opcje lokalne. Tak czy inaczej Codex staje się świadomy GitHuba.

> Dokładne URL-e serwera i konfiguracja się zmieniają — sprawdź bieżącą dokumentację **„GitHub MCP server"** po najnowszy endpoint i uwierzytelnianie. **Zakresy liczą się najbardziej:** token tylko-do-odczytu pozwala GPT *patrzeć*; token z zapisem pozwala *zmieniać*. Zacznij od tylko-do-odczytu, ucząc się.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Dodaj serwer GitHuba

Użyj `mcp add` z CLI (dostosuj do bieżącego serwera GitHuba + Twojego tokena):

```powershell
codex mcp add github -- npx -y @modelcontextprotocol/server-github
```

Podasz token GitHuba, gdy zostaniesz o to poproszony/a (lub przez udokumentowane ustawienie serwera). Na start wolej token **tylko-do-odczytu**.

> Wolisz edytować config? Dodaj ten sam serwer pod `[mcp_servers.github]` w `~/.codex/config.toml` (zob. E1). Uruchom `codex mcp --help` po bieżące opcje.

### Krok 2 — Potwierdź połączenie

```text
/mcp
```

Powinieneś/aś zobaczyć `github` i jego narzędzia. Zrestartuj Codeksa, jeśli się nie pojawia.

### Krok 3 — Czytaj, zanim zapiszesz

Zacznij od bezpiecznych pytań tylko-do-odczytu:

```text
Wylistuj 5 ostatnio zaktualizowanych repozytoriów na moim koncie GitHub.
```
```text
W moim repo <owner/repo> pokaż 5 najnowszych otwartych zgłoszeń z etykietami.
```

Obserwuj, jak GPT wywołuje narzędzia GitHuba i zwraca dane na żywo — bez kopiuj-wklej.

### Krok 4 — Zbadaj pull requesta

```text
W <owner/repo> podsumuj otwarty pull request #<N>: co zmienia oraz wszelkie
komentarze recenzji czy niezaliczone kontrole. Oznacz cokolwiek ryzykownego.
```

### Krok 5 — Utwórz zgłoszenie (Twoja pierwsza akcja zapisu)

```text
Utwórz w <owner/repo> zgłoszenie zatytułowane „Docs: dodaj kroki instalacji na Windows"
z krótką listą kontrolną w treści. Pokaż mi najpierw szkic i poczekaj na moje OK.
```

GPT szkicuje je, **pyta przed utworzeniem** i — po zatwierdzeniu — zakłada je i zwraca link. Ten krok zatwierdzenia to Twoja siatka bezpieczeństwa.

### Krok 6 — Prawdziwy mini-przepływ pracy

Połącz swoje pliki z GitHubem — Codex potrafi jedno i drugie:

```text
Przeczytaj komentarze TODO w tym projekcie, potem naszkicuj zgłoszenie GitHuba
ujmujące pracę do wykonania. Zapytaj przed utworzeniem.
```

Rozumienie lokalnego kodu + prawdziwa akcja zapisu, chronione Twoim zatwierdzeniem.

---

## 🧩 Przydatne ruchy z GitHubem

| Poproś o… | Dostajesz |
|----------|---------|
| „Wylistuj ostatnie zgłoszenia / PR-y w repo X" | Segregacja na żywo w terminalu |
| „Podsumuj PR #N + jego kontrole" | Briefing recenzji |
| „Utwórz zgłoszenie / komentarz (zapytaj najpierw)" | Naszkicowane, zatwierdzone, założone |
| „Co się zmieniło w ostatnich 5 commitach?" | Changelog prostym językiem |
| „Z moich TODO naszkicuj zgłoszenie" | Pliki + GitHub w jednym przepływie |

> ⚠️ **Sprawdzenie zakresu:** jeśli GPT może pushować lub otwierać PR-y, używa tokena z **zapisem**. Przyznawaj go tylko, gdy potrzeba, i nadal zatwierdzaj każdą akcję.

---

## ✅ Sprawdzian

- [ ] Dodałeś/aś serwer MCP GitHuba i zobaczyłeś/aś go pod `/mcp`.
- [ ] Uruchomiłeś/aś zapytania tylko-do-odczytu wobec prawdziwego repo.
- [ ] GPT utworzył zgłoszenie **po** poproszeniu o zatwierdzenie.
- [ ] Umiesz powiedzieć, czy Twój token jest tylko-do-odczytu czy z zapisem.

---

## 🎯 Praca domowa

Wybierz jedno swoje repo. Użyj Codex CLI + GitHub, by posegregować jego zgłoszenia, podsumować jeden PR i naszkicować (za zatwierdzeniem) jedno zgłoszenie z TODO w kodzie. Zanotuj, które akcje wymagały dostępu z zapisem.

---

## 💡 Najważniejsze wnioski

- **Serwer MCP GitHuba** czyni Codex CLI świadomym repo: czyta zgłoszenia/PR-y/kod, tworzy zgłoszenia/PR-y — przez zatwierdzone wywołania narzędzi.
- Dodaj go przez `codex mcp add` (lub `config.toml`); sprawdź bieżącą dokumentację GitHuba po endpoint/uwierzytelnianie.
- **Ograniczaj starannie zakres**: tylko-do-odczytu, by się uczyć; zapis przyznawaj tylko, gdy potrzeba, i zatwierdzaj każdą zmianę.

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Poprzedni](01-narzedzia-konektory-i-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Atlassian w Codeksie →](03-atlassian-mcp.md)
