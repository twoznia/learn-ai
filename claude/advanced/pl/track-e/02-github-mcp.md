# E2 — GitHub MCP

⏱️ **15 minut** · Ścieżka: 🅴 Mistrzostwo MCP · Potrzebne: konto GitHub, Claude Desktop lub Claude.ai

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Wstecz](01-czym-jest-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Atlassian MCP →](03-atlassian-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer GitHub MCP** pozwala Claude pracować z Twoimi repozytoriami jak członek zespołu: czytać kod, przeglądać zgłoszenia i pull requesty, tworzyć zgłoszenia, otwierać PR-y i sprawdzać CI — przez wywołania narzędzi, które zatwierdzasz.

Dwa sposoby połączenia (użyj tego, który daje Twoja konfiguracja):

- **Konektor zdalny (najłatwiej)** — włącz GitHub w **Settings → Connectors** i zaloguj przez OAuth. Hostowany, nic do instalacji.
- **Własny / lokalny** — skieruj klienta na URL serwera MCP GitHuba (`https://api.githubcopilot.com/mcp/`) z tokenem GitHub, albo uruchom serwer GitHuba lokalnie. Przydatne w Claude Code i dla precyzyjnych zakresów.

> Dokładne nazwy konektorów i URL-e się zmieniają — jeśli ekran wygląda inaczej, sprawdź aktualną dokumentację GitHuba **„GitHub MCP server”** po najnowszy endpoint i konfigurację.

**Zakresy mają tu największe znaczenie.** Token tylko-odczyt pozwala Claude *patrzeć*; token odczyt-zapis pozwala *zmieniać* rzeczy (push, otwieranie PR). Zacznij od tylko-odczyt podczas nauki.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Podłącz GitHub

**Opcja A — Konektor (zalecane):**
1. Aplikacja Claude → **Settings → Connectors** → znajdź **GitHub** → **Connect**.
2. Przejdź logowanie OAuth; zatwierdź dostęp, o który prosi.

**Opcja B — Własny konektor po URL (aplikacje Claude, które to wspierają, lub Claude Code):**
- URL serwera: `https://api.githubcopilot.com/mcp/`
- Autoryzuj kontem GitHub / tokenem, gdy poprosi.

### Krok 2 — Czytaj, zanim zapiszesz

Zacznij od bezpiecznych pytań tylko do odczytu, by zobaczyć działające narzędzia:

```text
Wypisz 5 ostatnio zaktualizowanych repozytoriów na moim koncie GitHub.
```
```text
W moim repo <owner/repo> pokaż 5 najnowszych otwartych zgłoszeń z ich etykietami.
```

Patrz, jak Claude woła narzędzia GitHuba i zwraca dane na żywo — bez kopiuj-wklej.

### Krok 3 — Zbadaj pull request

```text
W <owner/repo> streść otwarty pull request #<N>: co zmienia oraz wszelkie
komentarze recenzji czy nieudane testy. Zaznacz cokolwiek ryzykownego.
```

Claude czyta PR, jego zmiany i status CI przez serwer i daje Ci brief.

### Krok 4 — Utwórz zgłoszenie (Twoja pierwsza akcja zapisu)

```text
Utwórz zgłoszenie w <owner/repo> o tytule „Docs: dodaj kroki instalacji dla Windows”
z krótkim ciałem w formie listy. Pokaż mi najpierw szkic i poczekaj na moje OK.
```

Claude szkicuje je, **pyta przed utworzeniem**, a po zatwierdzeniu zakłada i zwraca link. Ten krok zatwierdzenia to Twoja siatka bezpieczeństwa.

### Krok 5 — Prawdziwy miniprzepływ

Połącz czytanie i pisanie:

```text
Znajdź zgłoszenia w <owner/repo> z etykietą „good first issue”. Wybierz jedno i
naszkicuj plan naprawy krok po kroku jako komentarz do tego zgłoszenia. Zapytaj przed publikacją.
```

Przeszedłeś od przeglądania do działania — z bramką człowieka na każdej zmianie.

---

## 🧩 Przydatne ruchy GitHub MCP

| Poproś o… | Dostajesz |
|----------|---------|
| „Wypisz ostatnie zgłoszenia / PR w repo X” | Triage na żywo bez wychodzenia z czatu |
| „Streść PR #N + jego testy” | Brief recenzji |
| „Utwórz zgłoszenie / komentarz (zapytaj najpierw)” | Naszkicowane, zatwierdzone, założone |
| „Co się zmieniło w ostatnich 5 commitach?” | Changelog prostym językiem |
| „Wyszukaj w kodzie `<termin>` w repo X” | Zlokalizowane odniesienia |

> ⚠️ **Kontrola zakresu:** jeśli Claude może pushować kod lub otwierać PR-y, używa tokenu **zapisu**. Przyznawaj to tylko gdy potrzebujesz i zatwierdzaj każdą akcję.

---

## ✅ Sprawdzenie

- [ ] GitHub jest podłączony (konektor lub URL).
- [ ] Uruchomiłeś zapytania tylko-odczyt na prawdziwym repo.
- [ ] Claude utworzył zgłoszenie lub komentarz **po** zapytaniu o zatwierdzenie.
- [ ] Umiesz powiedzieć, czy Twoje połączenie jest tylko-odczyt czy odczyt-zapis.

---

## 🎯 Zadanie

Wybierz prawdziwe repo, które posiadasz. Użyj GitHub MCP do triage otwartych zgłoszeń, streść jeden PR i naszkicuj (z zatwierdzeniem) jedno zgłoszenie ujmujące zadanie, o którym wciąż zapominasz. Zanotuj, które akcje wymagały dostępu zapisu.

---

## 💡 Najważniejsze wnioski

- GitHub MCP zamienia Claude w członka zespołu świadomego repo: czyta zgłoszenia/PR-y/kod, tworzy zgłoszenia/PR-y — przez zatwierdzone wywołania narzędzi.
- Podłącz przez **konektor zdalny** (OAuth, najłatwiej) lub **URL/token** dla większej kontroli.
- **Ograniczaj zakres**: tylko-odczyt do nauki; przyznawaj zapis tylko gdy trzeba i zatwierdzaj każdą zmianę.

🌐 [English](../../en/track-e/02-github-mcp.md) · [← Wstecz](01-czym-jest-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Atlassian MCP →](03-atlassian-mcp.md)
