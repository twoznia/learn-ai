# E1 — Narzędzia i MCP (z Gemini CLI)

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: Gemini CLI zainstalowany i zalogowany (patrz D5)

🌐 [English](../../en/track-e/01-tools-and-mcp-explained.md) · [← Indeks ścieżki](../README.md) · [Dalej: GitHub z Gemini →](02-github-mcp.md)

---

## 🧠 Teoria (6 min)

By wykonywać prawdziwą pracę, Gemini musi sięgać do **zewnętrznych narzędzi i danych**. Robi to na trzy powiązane sposoby — poznaj różnicę:

| Sposób | Co to | Gdzie |
|-----|-----------|-------|
| **Wbudowane narzędzia** | Czytaj/zapisuj pliki, uruchamiaj polecenia powłoki, przeszukuj web | Gemini CLI, od ręki |
| **Rozszerzenia / połączone aplikacje** | Google Workspace, Maps, YouTube itd. | Aplikacja Gemini (Ścieżka F) |
| **Serwery MCP** | Otwarty standard do wpięcia *dowolnego* zewnętrznego narzędzia | Gemini CLI (ta ścieżka) |

**MCP (Model Context Protocol)** to ten uniwersalny. To jak **standardowa wtyczka**: zamiast każde narzędzie wymyśla własne połączenie, MCP daje jedno wspólne gniazdko. **Gemini CLI jest hostem MCP** — łączy się z **serwerami** MCP udostępniającymi **narzędzia** (akcje: utwórz zgłoszenie, uruchom zapytanie, wypisz zasoby).

```
Gemini CLI (host) ── łączy się z ──▶ serwer MCP ── udostępnia ──▶ narzędzia
   zatwierdzasz akcje                 (GitHub, Azure, Twój własny)
```

Dwa sposoby połączenia serwera:
- **Lokalny (stdio)** — mały program uruchamiany na PC (np. serwer plików albo Twój własny).
- **Zdalny (URL)** — hostowany serwer, na który kierujesz CLI.

Ta ścieżka łączy dużych dostawców (GitHub, Atlassian, Azure) i jeden, który sam zbudujesz — wszystko przez Gemini CLI.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zobacz wbudowane narzędzia

Uruchom Gemini CLI w projekcie i wypisz narzędzia:

```text
/tools
```

Zobaczysz wbudowane (odczyt/zapis plików, powłoka, web). One już czynią Gemini agentowym — MCP *dodaje* do nich.

### Krok 2 — Zobacz serwery MCP

```text
/mcp
```

To wypisuje serwery MCP podłączone do CLI (pusto jest w porządku — dodamy w kolejnych lekcjach).

### Krok 3 — Poznaj, gdzie mieszka konfiguracja MCP

CLI przechowuje serwery MCP w **pliku ustawień** — na poziomie użytkownika (`~/.gemini/settings.json`) lub projektu (`.gemini/settings.json`). Kształt do powtarzania:

```json
{
  "mcpServers": {
    "workspace": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "C:\\Users\\TwojaNazwa\\mcp-workspace"]
    }
  }
}
```

- `command` — program do uruchomienia (`npx`, `python`, `node`…).
- `args` — pakiet i ustawienia.

Jest też skrót: `gemini mcp add <nazwa> -- <polecenie>` (użyjesz w E2).

### Krok 4 — Zrozum wywołanie narzędzia

Gdy Gemini używa narzędzia MCP: **decyduje**, że pasuje → **woła** ze strukturalnymi danymi → serwer je **uruchamia** → **Ty zatwierdzasz** wynik (CLI pyta przed akcjami zmieniającymi rzeczy). Zostajesz w pętli.

### Krok 5 — Zmapuj potrzeby

Wypisz systemy, do których Gemini miałby sięgać: kod (GitHub?), zgłoszenia (Jira?), chmura (Azure?), własne pliki/skrypty. Zaznacz **odczyt** vs **zapis** — będziesz ograniczać każdy serwer do minimum (E6).

---

## 🧩 Trzy sposoby sięgania

| | **Wbudowane** | **Rozszerzenia (aplikacja)** | **MCP (CLI)** |
|---|---|---|---|
| Gdzie | Gemini CLI | Aplikacja Gemini | Gemini CLI |
| Konfiguracja | Brak | Włącz + zaloguj | Konfig / `gemini mcp add` |
| Najlepsze do | Pliki, powłoka, web | Workspace, Maps, YouTube | Dowolne narzędzie, własne serwery |

---

## ✅ Sprawdzenie

- [ ] Umiesz nazwać trzy sposoby sięgania (wbudowane, rozszerzenia, MCP).
- [ ] Wypisałeś wbudowane narzędzia przez `/tools` i serwery MCP przez `/mcp`.
- [ ] Wiesz, gdzie mieszka konfiguracja MCP (`settings.json`) i kształt serwera.
- [ ] Wypisałeś systemy do podłączenia, zaznaczone odczyt/zapis.

---

## 🎯 Zadanie

Naszkicuj idealną konfigurację Gemini CLI: które serwery MCP dodasz, ograniczone do czego, tylko-odczyt czy nie. Zachowaj szkic — kolejne lekcje wdrażają go dostawca po dostawcy.

---

## 💡 Najważniejsze wnioski

- Gemini sięga narzędzi na trzy sposoby: **wbudowane** i **MCP** (oba w CLI) oraz **rozszerzenia** (w aplikacji).
- **MCP** to uniwersalna wtyczka; **Gemini CLI jest hostem MCP** łączącym się z **serwerami** udostępniającymi **narzędzia**.
- Serwery są **lokalne** (program) lub **zdalne** (URL); ograniczasz je i **zatwierdzasz** akcje.

🌐 [English](../../en/track-e/01-tools-and-mcp-explained.md) · [← Indeks ścieżki](../README.md) · [Dalej: GitHub z Gemini →](02-github-mcp.md)
