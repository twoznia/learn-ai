# G5 — MCP wewnątrz Claude Code

⏱️ **15 minut** · Ścieżka: 🅶 Claude Code w głąb · Potrzebne: Claude Code zainstalowany i zalogowany (Ścieżka E pomaga)

🌐 [English](../../en/track-g/05-mcp-in-claude-code.md) · [← Wstecz](04-haki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Ścieżka E podłączyła serwery MCP do **Claude Desktop**. Claude Code też mówi MCP — i to prawdopodobnie najlepsze miejsce, by go używać, bo Claude Code może **łączyć Twoje pliki, terminal i narzędzia MCP** w jednym przepływie. Wyobraź sobie jedną sesję, w której Claude czyta kod, uruchamia testy **i** otwiera zgłoszenie GitHub — wszystko przez zatwierdzone narzędzia.

W Claude Code zarządzasz serwerami MCP z **wiersza poleceń** (lub konfiguracji projektu), nie z pliku JSON, którego szukasz. Model myślowy jest ten sam co w E1: **hosty** (Claude Code) łączą się z **serwerami** udostępniającymi **narzędzia**; trzymasz najmniejsze uprawnienia i zatwierdzasz zapisy.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zobacz, co podłączone

W Claude Code:

```text
/mcp
```

To wypisuje serwery MCP dostępne w sesji i pozwala nimi zarządzać. Pusto jest w porządku — dodamy jeden.

### Krok 2 — Dodaj serwer z terminala

Claude Code ma podkomendę `mcp`. Ogólny kształt:

```powershell
claude mcp add <nazwa> -- <polecenie uruchamiające serwer>
```

Na przykład serwer plików ograniczony do jednego folderu:

```powershell
claude mcp add workspace -- npx -y @modelcontextprotocol/server-filesystem C:\Users\TwojaNazwa\mcp-workspace
```

Teraz ten serwer jest dostępny w Twoich sesjach Claude Code.

> Dokładne flagi ewoluują — uruchom `claude mcp --help` (lub `claude mcp add --help`), by zobaczyć aktualne opcje dla serwerów lokalnych (stdio) vs zdalnych (URL) i konfigurację per zakres.

### Krok 3 — Używaj narzędzi MCP obok plików i terminala

Uruchom Claude Code w projekcie i poproś o coś obejmującego wiele możliwości:

```text
Przeczytaj komentarze TODO w tym projekcie, potem utwórz krótką listę markdown
z nich w folderze workspace przez serwer plików. Pokaż mi przed zapisem.
```

Claude łączy czytanie kodu (wbudowane) z narzędziem MCP (pliki) — jeden przepływ, kilka możliwości.

### Krok 4 — Dodaj większego dostawcę (opcjonalnie)

Jeśli używasz GitHuba (Ścieżka E2), możesz dodać jego serwer do Claude Code i uzyskać przepływy end-to-end:

```text
Streść, co zmieniło się w moich ostatnich commitach, potem naszkicuj zgłoszenie GitHub
ujmujące dalszą pracę. Zapytaj przed utworzeniem zgłoszenia.
```

Rozumienie kodu + prawdziwa akcja zapisu, z bramką Twojego zatwierdzenia.

### Krok 5 — Zakres per projekt

Konfiguracja MCP może być **projektowa** (dostępna w tym repo) lub szersza. Trzymaj serwery tam, gdzie należą:
- Serwer specyficzny dla projektu → zakres projektu.
- Osobisty pomocnik używany wszędzie → zakres użytkownika.

Uruchom komendę `/mcp` lub pomoc `claude mcp`, by zobaczyć i ustawić zakres.

### Krok 6 — To samo bezpieczeństwo, ostrzejsza stawka

Claude Code może działać na plikach, terminalu **i** narzędziach MCP razem — więc dyscyplina ze Ścieżek E6 i G4 ma jeszcze większe znaczenie:
- **Najmniejsze uprawnienia** na każdym serwerze.
- **Tylko-odczyt podczas nauki**; zatwierdzaj każdy zapis.
- Połącz z **hakiem PreToolUse** (G4), jeśli chcesz twardą barierkę na ryzykownych akcjach.

---

## 🧩 Czemu MCP błyszczy w Claude Code

| Możliwość | Przykład |
|------------|---------|
| Pliki + MCP | Przeczytaj kod → zapisz checklistę przez serwer plików |
| Terminal + MCP | Uruchom testy → otwórz zgłoszenie GitHub przy porażce (z zatwierdzeniem) |
| Wiele serwerów | Pliki + GitHub w jednym zadaniu |
| Konfiguracja z zakresem | Serwery per projekt vs osobiste |

> ⚠️ **Większy zasięg = większa ostrożność.** Łączenie lokalnych plików, powłoki i zapisów MCP jest potężne; trzymaj serwery wąsko ograniczone i zatwierdzaj akcje zmieniające lub wysyłające.

---

## ✅ Sprawdzenie

- [ ] Wypisałeś serwery MCP przez `/mcp`.
- [ ] Dodałeś serwer przez `claude mcp add` (sprawdzając `--help` po aktualne flagi).
- [ ] Claude Code połączył wbudowaną możliwość z narzędziem MCP w jednym zadaniu.
- [ ] Umiesz wyjaśnić zakres projektu vs użytkownika i zasady bezpieczeństwa.

---

## 🎯 Zadanie

Dodaj jeden serwer MCP do Claude Code ograniczony do prawdziwego projektu. Uruchom zadanie łączące Twoje pliki (lub terminal) z tym serwerem — przeczytaj coś, potem wyprodukuj lub załóż coś przez MCP, zatwierdzając każdy zapis. Zanotuj, gdzie hak mógłby dodać barierkę.

---

## 💡 Najważniejsze wnioski

- Claude Code mówi **MCP** i zarządza serwerami z **CLI** (`/mcp`, `claude mcp add`) — sprawdź `--help` po aktualne flagi.
- Jego przewaga to **łączenie plików, terminala i narzędzi MCP** w jednym przepływie (np. przeczytaj kod → otwórz zgłoszenie GitHub).
- **Zakres per projekt**, trzymaj **najmniejsze uprawnienia**, zatwierdzaj każdy zapis i dodaj **hak** dla twardych barierek.

🌐 [English](../../en/track-g/05-mcp-in-claude-code.md) · [← Wstecz](04-haki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
