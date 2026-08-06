# E4 — Azure MCP

⏱️ **15 minut** · Ścieżka: 🅴 Mistrzostwo MCP · Potrzebne: konto Azure, Node.js + Azure CLI, Claude Desktop

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Wstecz](03-atlassian-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer Azure MCP** pozwala Claude eksplorować i pracować z Twoimi **zasobami chmury Azure** — kontami magazynu, bazami danych, grupami zasobów, Key Vault, logami i więcej — przez język naturalny.

W odróżnieniu od GitHuba/Atlassiana, Azure MCP zwykle uruchamia się **lokalnie**: mały serwer, który startujesz na PC (przez `npx`), rozmawiający z Azure przy użyciu poświadczeń, którymi już jesteś zalogowany (Azure CLI). Więc konfiguracja to wzorzec **lokalny** z E1.

Czemu lokalny + istniejące logowanie jest fajne:
- **Brak nowego sekretu do wklejania** — używa ponownie sesji `az login`.
- **Obowiązują Twoje uprawnienia** — Claude może dotknąć tylko tego, co Twoje konto Azure już może.

> Nazwy pakietów i polecenia serwera Azure MCP Microsoftu mogą się zmieniać. Jeśli `@azure/mcp` się nie uruchamia, sprawdź aktualną dokumentację Microsoftu **„Azure MCP Server”** po dokładny pakiet/polecenie i wstaw je do poniższej konfiguracji.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zaloguj się do Azure lokalnie

Zainstaluj Azure CLI, jeśli trzeba, potem:

```powershell
az login
```

Otworzy się przeglądarka; zaloguj. Ta sesja to to, co Azure MCP wykorzysta ponownie.

### Krok 2 — Zarejestruj serwer Azure MCP

Otwórz konfigurację Claude Desktop:

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Dodaj wpis Azure (zachowaj istniejące serwery):

```json
{
  "mcpServers": {
    "azure": {
      "command": "npx",
      "args": ["-y", "@azure/mcp@latest", "server", "start"]
    }
  }
}
```

Zapisz, potem **całkowicie zamknij i otwórz ponownie** Claude Desktop, by uruchomił serwer.

### Krok 3 — Eksploruj tylko do odczytu

Zacznij od patrzenia, nigdy od zmieniania:

```text
Wypisz moje subskrypcje Azure, a dla domyślnej wypisz grupy zasobów.
```
```text
Pokaż konta magazynu w grupie zasobów <nazwa> i ich lokalizacje.
```

Claude uruchamia narzędzia Azure lokalnie i zwraca wyniki na żywo — przewodnik po Twojej chmurze.

### Krok 4 — Zadawaj realne pytania między usługami

```text
Które zasoby w subskrypcji <nazwa> utworzono najnowsze? Pogrupuj według typu.
```
```text
Streść kontenery w koncie magazynu <nazwa> i mniej więcej ile każdy zawiera.
```

Odpytujesz swoją chmurę zwykłym językiem zamiast polować w portalu.

### Krok 5 — Bądź rozważny przy zmianach

Akcje Azure mogą kosztować pieniądze lub usunąć dane. Zasady podczas nauki:

- Trzymaj prompty **tylko-odczyt** („wypisz”, „pokaż”, „streść”).
- Nigdy nie proś o usunięcie, skalowanie czy wdrożenie bez zrozumienia dokładnego skutku.
- Jeśli chcesz zmiany, poproś Claude, by **najpierw wyjaśnił, co uruchomi i dlaczego**, i potwierdź docelowy zasób.

```text
Może zmienię rozmiar <zasób>. Najpierw wyjaśnij dokładnie, co to za zmiana, ryzyka
i jak ją cofnąć — NIE rób jeszcze żadnej zmiany.
```

---

## 🧩 Przydatne ruchy Azure MCP

| Poproś o… | Dostajesz |
|----------|---------|
| „Wypisz subskrypcje / grupy zasobów” | Mapę Twojej chmury |
| „Pokaż konta magazynu / bazy w RG X” | Inwentarz bez portalu |
| „Co utworzono ostatnio, wg typu?” | Szybki audyt |
| „Wyjaśnij konfigurację tego zasobu” | Dokumentację prostym językiem |
| „Wyjaśnij zmianę przed jej wykonaniem” | Bezpieczeństwo przed akcją |

> ⚠️ **Zasięg szkód:** zmiany Azure są realne i mogą kosztować pieniądze lub utracić dane. Domyślnie tylko-odczyt; rozumiej każdy zapis; Twoje uprawnienia `az login` to twarda granica.

---

## ✅ Sprawdzenie

- [ ] `az login` działa, a Azure MCP jest zarejestrowany w konfiguracji.
- [ ] Claude wypisał Twoje subskrypcje/grupy zasobów po restarcie.
- [ ] Uruchomiłeś kilka zapytań tylko-odczyt o prawdziwe zasoby.
- [ ] Umiesz wyjaśnić, czemu trzymasz prompty Azure tylko-odczyt podczas nauki.

---

## 🎯 Zadanie

Daj Claude przewodnik tylko-odczyt po jednej subskrypcji: wypisz grupy zasobów, zinwentaryzuj największe i każ mu wyprodukować krótkie podsumowanie prostym językiem, co uruchamiasz. Nie rób żadnych zmian.

---

## 💡 Najważniejsze wnioski

- Azure MCP działa **lokalnie** (przez `npx`) i wykorzystuje ponownie sesję **`az login`** — brak nowego sekretu, obowiązują Twoje uprawnienia.
- To wzorzec **lokalnej konfiguracji** z E1: dodaj serwer, zrestartuj, potem odpytuj chmurę zwykłym językiem.
- Zmiany w chmurze są **wysokiego ryzyka** — zostań przy odczycie i każ Claude wyjaśnić każdy zapis przed jego wykonaniem.

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Wstecz](03-atlassian-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)
