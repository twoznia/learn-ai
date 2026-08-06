# E1 — Czym naprawdę jest MCP

⏱️ **15 minut** · Ścieżka: 🅴 Mistrzostwo MCP · Potrzebne: Claude Desktop (z kursu podstawowego)

🌐 [English](../../en/track-e/01-mcp-explained.md) · [← Indeks ścieżki](../README.md) · [Dalej: GitHub MCP →](02-github-mcp.md)

---

## 🧠 Teoria (6 min)

**MCP (Model Context Protocol)** to otwarty standard pozwalający Claude rozmawiać z **zewnętrznymi narzędziami i danymi** w spójny sposób. To jak **uniwersalna wtyczka**: zamiast każda aplikacja wymyśla własny sposób łączenia AI, MCP daje jedno wspólne gniazdko.

Trzy role:

| Rola | Co to | Przykłady |
|------|-----------|----------|
| **Host / Klient** | Aplikacja, której używasz, *łącząca się z* serwerami | Claude Desktop, Claude Code, aplikacja webowa Claude |
| **Serwer** | Mały program *udostępniający* możliwości | GitHub, Atlassian, Azure, serwer plików, taki, który zbudujesz |
| **Ty** | Zatwierdzasz dostęp i przeglądasz, co się dzieje | 🧑 |

Serwer może udostępniać trzy rodzaje rzeczy:

- **Narzędzia (tools)** — akcje, które Claude może wykonać (utwórz zgłoszenie, uruchom zapytanie, wypisz pliki).
- **Zasoby (resources)** — dane, które Claude może czytać (plik, strona, rekord).
- **Prompty (prompts)** — gotowe szablony promptów oferowane przez serwer.

W większości pracy gwiazdą są **narzędzia**: to nimi Claude *robi* rzeczy w Twoich systemach.

### Dwa sposoby połączenia serwera

```
LOKALNY (stdio)                        ZDALNY (konektor, URL + OAuth)
Claude Desktop ──uruchamia──▶ program   Claude ──HTTPS──▶ hostowany serwer
na Twoim PC, przez plik konfig.         logujesz się raz, bez instalacji
np. serwer plików, Twój własny          np. GitHub, Atlassian
```

- **Serwery lokalne** działają *na Twojej maszynie*. Rejestrujesz je w pliku konfiguracyjnym; Claude Desktop je uruchamia. Świetne do dostępu do plików i serwerów, które budujesz.
- **Serwery zdalne (konektory)** są *hostowane*. Włączasz je w aplikacji i logujesz przez OAuth — kilka kliknięć, nic do instalacji. Świetne do dużych usług jak GitHub i Atlassian.

Ta ścieżka używa **obu**: konektorów dla dużych dostawców (E2–E4) i lokalnego serwera, który sam zbudujesz (E5).

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zobacz, gdzie mieszkają serwery lokalne

Otwórz konfigurację Claude Desktop (utwórz, jeśli brak):

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Każdy serwer lokalny to wpis pod `mcpServers`. Oto minimalny kształt, który powtórzysz w całej ścieżce:

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
- `args` — co mu przekazać (pakiet, potem ustawienia).

### Krok 2 — Zobacz, gdzie mieszkają konektory zdalne

W aplikacji Claude: **Settings → Connectors**. To zdalne serwery MCP — włączasz i logujesz się, bez pliku konfiguracyjnego. Zauważ różnicę względem Kroku 1: brak `command`, brak instalacji, tylko autoryzowany link.

### Krok 3 — Poznaj anatomię wywołania narzędzia

Gdy Claude używa narzędzia MCP, dzieją się cztery rzeczy:

1. Claude **decyduje**, że narzędzie pasuje do zadania.
2. **Woła** je ze strukturalnymi danymi (np. `create_issue(title, body)`).
3. Serwer je **uruchamia** i zwraca wynik.
4. Ty go **widzisz i zatwierdzasz** (Claude pyta przed akcjami zmieniającymi rzeczy).

Pozostajesz w pętli — MCP daje Claude *zasięg*, nie *wolną rękę*.

### Krok 4 — Zmapuj własne potrzeby

Na kartce wypisz systemy, do których Claude miałby sięgać: kod (GitHub?), zgłoszenia (Jira?), chmura (Azure?), własne pliki lub skrypty. Obok każdego zaznacz **odczyt** vs **zapis** — będziesz ograniczać serwery do minimum (E6).

---

## 🧩 Lokalny vs zdalny w skrócie

| | **Serwer lokalny (stdio)** | **Konektor zdalny (URL)** |
|---|---|---|
| Działa | Na Twoim PC | Hostowany przez dostawcę |
| Konfiguracja | Edycja pliku konfig. | Włączenie + logowanie OAuth |
| Instalacja | Zwykle tak (`npx`/`python`) | Nie |
| Najlepsze do | Plików, własnych serwerów | GitHub, Atlassian, duże SaaS |
| Auth | Lokalny / tokeny, które ustawisz | OAuth, zatwierdzasz zakresy |

---

## ✅ Sprawdzenie

- [ ] Umiesz nazwać trzy role MCP (host/klient, serwer, Ty).
- [ ] Umiesz wyjaśnić narzędzia vs zasoby vs prompty.
- [ ] Znalazłeś i plik konfiguracyjny lokalny, **i** ekran Connectors.
- [ ] Wypisałeś systemy, do których Claude ma sięgać, z oznaczeniem odczyt/zapis.

---

## 🎯 Zadanie

Naszkicuj idealną konfigurację MCP: których dostawców podłączysz zdalnie, które serwery uruchomisz lokalnie i jaki minimalny dostęp każdy potrzebuje. Zachowaj szkic — kolejne lekcje wdrażają go dostawca po dostawcy.

---

## 💡 Najważniejsze wnioski

- MCP to **uniwersalna wtyczka**: hosty (Claude) łączą się z **serwerami** udostępniającymi **narzędzia**, **zasoby** i **prompty**.
- Serwery są albo **lokalne** (plik konfig., działają na PC), albo **konektory zdalne** (URL + OAuth, nic do instalacji).
- Claude dostaje **zasięg**, nie wolną rękę — zatwierdzasz akcje i ograniczasz każdy serwer.

🌐 [English](../../en/track-e/01-mcp-explained.md) · [← Indeks ścieżki](../README.md) · [Dalej: GitHub MCP →](02-github-mcp.md)
