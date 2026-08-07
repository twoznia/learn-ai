# E1 — Narzędzia, konektory i MCP — wyjaśnienie

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: Codex CLI zainstalowany i zalogowany (zob. D5)

🌐 [English](../../en/track-e/01-tools-connectors-and-mcp.md) · [← Spis ścieżki](../README.md) · [Dalej: GitHub w Codeksie →](02-github-mcp.md)

---

## 🧠 Teoria (6 min)

Żeby wykonywać prawdziwą pracę, GPT musi sięgnąć do **zewnętrznych narzędzi i danych**. Robi to na trzy powiązane sposoby — poznaj różnicę:

| Sposób | Co to jest | Gdzie |
|-----|-----------|-------|
| **Konektory** | Łączą ChatGPT z Twoimi aplikacjami (Google Drive, GitHub itd.) | **Aplikacja** ChatGPT (Ścieżka F) |
| **Akcje Custom GPT** | Dają Custom GPT własne wywołania API | Custom GPT (A1) |
| **Serwery MCP** | Otwarty standard podłączania *dowolnego* zewnętrznego narzędzia | Codex CLI (ta ścieżka) |

**MCP (Model Context Protocol)** to ten uniwersalny. Jest jak **standardowa wtyczka**: zamiast żeby każde narzędzie wymyślało własne połączenie, MCP daje jedno wspólne gniazdo. **Codex CLI to host MCP** — łączy się z **serwerami** MCP, które udostępniają **narzędzia** (akcje, jakie GPT może wykonać: utworzyć zgłoszenie, uruchomić zapytanie, wylistować zasoby).

```
Codex CLI (host) ── łączy się z ──▶ serwer MCP ── udostępnia ──▶ narzędzia
   Ty zatwierdzasz akcje              (GitHub, Azure, własny)
```

Dwa sposoby połączenia serwera:
- **Lokalny (stdio)** — mały program uruchamiany na Twoim PC (np. serwer systemu plików lub taki, który zbudujesz).
- **Zdalny (URL)** — hostowany serwer, na który wskazujesz Codeksowi.

Ta ścieżka podłącza dużych dostawców (GitHub, Atlassian, Azure) i jeden, który zbudujesz sam/a — wszystko przez Codex CLI.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Znajdź, gdzie Codex trzyma konfigurację

Codex CLI trzyma ustawienia w `~/.codex/config.toml` (na Windowsie to `C:\Users\TwojaNazwa\.codex\config.toml`). Serwery MCP mieszkają tam pod `[mcp_servers.<nazwa>]`.

```powershell
notepad $HOME\.codex\config.toml
```

Kształt, który będziesz wielokrotnie używać (lokalny serwer systemu plików):

```toml
[mcp_servers.workspace]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "C:\\Users\\TwojaNazwa\\mcp-workspace"]
```

- `command` — program do uruchomienia (`npx`, `python`, `node`…).
- `args` — pakiet i wszelkie ustawienia.

Jest też podkomenda-skrót: `codex mcp add <nazwa> -- <komenda>` (użyjesz jej w E2). Uruchom `codex mcp --help` po bieżące opcje.

### Krok 2 — Wylistuj serwery MCP

Wewnątrz Codeksa wylistuj podłączone serwery (lub uruchom `codex mcp list` w terminalu):

```text
/mcp
```

Pusto to w porządku — dodamy kilka w kolejnych lekcjach.

### Krok 3 — Zrozum wywołanie narzędzia

Gdy GPT używa narzędzia MCP: **decyduje**, że narzędzie pasuje → **wywołuje** je ze strukturalnymi danymi → serwer je **uruchamia** → **Ty zatwierdzasz** wynik (Codex pyta przed akcjami, które coś zmieniają). Pozostajesz w pętli.

### Krok 4 — Rozróżnij te trzy powierzchnie

- **Konektory** to łatwe integracje włączane kliknięciem w **aplikacji ChatGPT** (Ścieżka F).
- **Akcje Custom GPT** pozwalają Custom GPT wywołać konkretne API, które skonfigurujesz.
- **MCP** to deweloperska, uniwersalna droga w **Codex CLI** — i tam też możesz uruchamiać serwery, które zbudujesz.

### Krok 5 — Zmapuj swoje potrzeby

Wypisz systemy, do których chciałbyś/chciałabyś, by GPT sięgał: kod (GitHub?), zgłoszenia (Jira?), chmura (Azure?), własne pliki/skrypty. Zaznacz **odczyt** vs **zapis** — każdy serwer ograniczysz do minimum, jakiego potrzebuje (E6).

---

## 🧩 Trzy sposoby sięgania na zewnątrz

| | **Konektory (aplikacja)** | **Akcje Custom GPT** | **MCP (Codex CLI)** |
|---|---|---|---|
| Gdzie | Aplikacja ChatGPT | Custom GPT | Codex CLI |
| Konfiguracja | Włącz + zaloguj | Skonfiguruj API | Config / `codex mcp add` |
| Najlepsze do | Drive, GitHub, codzienne aplikacje | Konkretne API jednego GPT | Dowolne zewnętrzne narzędzie, własne serwery |

---

## ✅ Sprawdzian

- [ ] Umiesz wymienić trzy sposoby, jakimi GPT sięga do narzędzi (konektory, Akcje, MCP).
- [ ] Znalazłeś/aś `~/.codex/config.toml` i kształt `[mcp_servers.*]`.
- [ ] Wylistowałeś/aś serwery MCP poleceniem `/mcp` (lub `codex mcp list`).
- [ ] Wypisałeś/aś systemy do podłączenia, oznaczając odczyt vs zapis.

---

## 🎯 Praca domowa

Naszkicuj idealną konfigurację Codex CLI: które serwery MCP dodasz, ograniczone do czego, tylko-do-odczytu czy nie. Zachowaj szkic — kolejne lekcje wdrażają go dostawca po dostawcy.

---

## 💡 Najważniejsze wnioski

- GPT sięga do narzędzi na trzy sposoby: **konektory** (aplikacja), **Akcje Custom GPT** i **MCP** (Codex CLI).
- **MCP** to uniwersalna wtyczka; **Codex CLI to host MCP** łączący się z **serwerami**, które udostępniają **narzędzia**.
- Serwery są **lokalne** (program) lub **zdalne** (URL), konfigurowane w `~/.codex/config.toml`; ograniczasz je i **zatwierdzasz** akcje.

🌐 [English](../../en/track-e/01-tools-connectors-and-mcp.md) · [← Spis ścieżki](../README.md) · [Dalej: GitHub w Codeksie →](02-github-mcp.md)
