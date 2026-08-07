# E2 — GitHub z Gemini CLI

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: konto GitHub, Gemini CLI

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Wstecz](01-narzedzia-i-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Atlassian z Gemini →](03-atlassian-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer GitHub MCP** pozwala Gemini pracować z repozytoriami jak członek zespołu: czytać kod, przeglądać zgłoszenia i PR-y, tworzyć zgłoszenia, otwierać PR-y i sprawdzać CI — przez wywołania narzędzi, które zatwierdzasz, wprost w Gemini CLI.

Dodajesz go jako serwer MCP. GitHub publikuje oficjalny serwer MCP (endpoint `https://api.githubcopilot.com/mcp/`), są też opcje lokalne. Tak czy inaczej CLI staje się świadome GitHuba.

> Dokładne URL-e serwera i konfiguracja ewoluują — sprawdź aktualną dokumentację GitHuba **„GitHub MCP server”** po najnowszy endpoint i auth. **Zakresy mają największe znaczenie:** token tylko-odczyt pozwala *patrzeć*; token zapisu pozwala *zmieniać*. Zacznij od tylko-odczyt.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Dodaj serwer GitHub

Użyj `mcp add` CLI. Ogólny kształt (dostosuj do aktualnego serwera GitHub + Twojego tokenu):

```powershell
gemini mcp add github -- npx -y @modelcontextprotocol/server-github
```

Podasz token GitHub, gdy poprosi (lub przez udokumentowane ustawienie serwera). Zacznij od tokenu **tylko-odczyt**.

> Wolisz edytować konfigurację? Dodaj ten sam serwer pod `mcpServers` w `.gemini/settings.json` (patrz E1). Uruchom `gemini mcp --help` po aktualne opcje.

### Krok 2 — Potwierdź podłączenie

```text
/mcp
```

Powinieneś zobaczyć `github` i jego narzędzia. Zrestartuj CLI, jeśli się nie pojawi.

### Krok 3 — Czytaj, zanim zapiszesz

Zacznij od bezpiecznych pytań tylko-odczyt:

```text
Wypisz 5 ostatnio zaktualizowanych repozytoriów na moim koncie GitHub.
```
```text
W moim repo <owner/repo> pokaż 5 najnowszych otwartych zgłoszeń z etykietami.
```

Patrz, jak Gemini woła narzędzia GitHuba i zwraca dane na żywo — bez kopiuj-wklej.

### Krok 4 — Zbadaj pull request

```text
W <owner/repo> streść otwarty PR #<N>: co zmienia oraz komentarze recenzji
czy nieudane testy. Zaznacz cokolwiek ryzykownego.
```

### Krok 5 — Utwórz zgłoszenie (pierwsza akcja zapisu)

```text
Utwórz zgłoszenie w <owner/repo> o tytule „Docs: dodaj kroki instalacji dla Windows”
z krótkim ciałem w formie listy. Pokaż mi najpierw szkic i poczekaj na OK.
```

Gemini szkicuje je, **pyta przed utworzeniem**, a po zatwierdzeniu zakłada i zwraca link. Ten krok zatwierdzenia to Twoja siatka bezpieczeństwa.

### Krok 6 — Prawdziwy miniprzepływ

Połącz swoje pliki z GitHubem — CLI potrafi oba:

```text
Przeczytaj komentarze TODO w tym projekcie, potem naszkicuj zgłoszenie GitHub
ujmujące dalszą pracę. Zapytaj przed utworzeniem.
```

Lokalne rozumienie kodu + prawdziwa akcja zapisu, z bramką Twojego zatwierdzenia.

---

## 🧩 Przydatne ruchy GitHub

| Poproś o… | Dostajesz |
|----------|---------|
| „Wypisz ostatnie zgłoszenia / PR w repo X” | Triage na żywo w terminalu |
| „Streść PR #N + jego testy” | Brief recenzji |
| „Utwórz zgłoszenie / komentarz (zapytaj)” | Naszkicowane, zatwierdzone, założone |
| „Co zmieniło się w ostatnich 5 commitach?” | Changelog prostym językiem |
| „Z moich TODO naszkicuj zgłoszenie” | Pliki + GitHub w jednym przepływie |

> ⚠️ **Kontrola zakresu:** jeśli Gemini może pushować lub otwierać PR-y, używa tokenu **zapisu**. Przyznawaj to tylko gdy trzeba i zatwierdzaj każdą akcję.

---

## ✅ Sprawdzenie

- [ ] Dodałeś serwer GitHub MCP i widzisz go pod `/mcp`.
- [ ] Uruchomiłeś zapytania tylko-odczyt na prawdziwym repo.
- [ ] Gemini utworzył zgłoszenie **po** zapytaniu o zatwierdzenie.
- [ ] Umiesz powiedzieć, czy token jest tylko-odczyt czy odczyt-zapis.

---

## 🎯 Zadanie

Wybierz repo, które posiadasz. Użyj Gemini CLI + GitHub do triage zgłoszeń, streść jeden PR i naszkicuj (z zatwierdzeniem) jedno zgłoszenie z TODO w kodzie. Zanotuj, które akcje wymagały dostępu zapisu.

---

## 💡 Najważniejsze wnioski

- **Serwer GitHub MCP** czyni Gemini CLI świadomym repo: czyta zgłoszenia/PR-y/kod, tworzy zgłoszenia/PR-y — przez zatwierdzone narzędzia.
- Dodaj przez `gemini mcp add` (lub `settings.json`); sprawdź aktualną dokumentację GitHuba po endpoint/auth.
- **Ograniczaj zakres**: tylko-odczyt do nauki; zapis tylko gdy trzeba, zatwierdzaj każdą zmianę.

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Wstecz](01-narzedzia-i-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Atlassian z Gemini →](03-atlassian-mcp.md)
