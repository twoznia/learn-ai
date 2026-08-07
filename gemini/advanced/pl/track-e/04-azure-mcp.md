# E4 — Azure z Gemini CLI

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: konto Azure, Node.js + Azure CLI, Gemini CLI

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Wstecz](03-atlassian-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer Azure MCP** pozwala Gemini eksplorować i pracować z Twoimi **zasobami chmury Azure** — magazynem, bazami, grupami zasobów, Key Vault, logami — przez język naturalny.

Azure MCP zwykle uruchamia się **lokalnie**: mały serwer startowany przez `npx`, rozmawiający z Azure przy użyciu poświadczeń, którymi już jesteś zalogowany (Azure CLI). Więc to wzorzec **lokalny** z E1.

Czemu lokalny + istniejące logowanie jest fajne:
- **Brak nowego sekretu do wklejania** — używa ponownie sesji `az login`.
- **Obowiązują Twoje uprawnienia** — Gemini dotknie tylko tego, co Twoje konto Azure już może.

> Nazwy pakietów i polecenia serwera Azure MCP Microsoftu mogą się zmieniać. Jeśli `@azure/mcp` się nie uruchamia, sprawdź aktualną dokumentację **„Azure MCP Server”** po dokładny pakiet/polecenie.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zaloguj się do Azure lokalnie

Zainstaluj Azure CLI, jeśli trzeba, potem:

```powershell
az login
```

Otworzy się przeglądarka; zaloguj. Ta sesja to to, co Azure MCP wykorzysta.

### Krok 2 — Dodaj serwer Azure MCP

Dodaj do Gemini CLI:

```powershell
gemini mcp add azure -- npx -y @azure/mcp@latest server start
```

> Albo dodaj ten sam pod `mcpServers` w `.gemini/settings.json`. Zrestartuj CLI, by uruchomił serwer.

### Krok 3 — Potwierdź i eksploruj tylko-odczyt

```text
/mcp
```

Potem patrz, nigdy nie zmieniaj:

```text
Wypisz moje subskrypcje Azure, a dla domyślnej wypisz grupy zasobów.
```
```text
Pokaż konta magazynu w grupie zasobów <nazwa> i ich lokalizacje.
```

Gemini uruchamia narzędzia Azure lokalnie i zwraca wyniki na żywo — przewodnik po chmurze.

### Krok 4 — Zadawaj realne pytania

```text
Które zasoby w subskrypcji <nazwa> utworzono najnowsze? Pogrupuj według typu.
```
```text
Streść kontenery w koncie magazynu <nazwa> i mniej więcej ile każdy zawiera.
```

Odpytujesz chmurę zwykłym językiem zamiast polować w portalu.

### Krok 5 — Bądź rozważny przy zmianach

Akcje Azure mogą kosztować pieniądze lub usunąć dane. Podczas nauki:
- Trzymaj prompty **tylko-odczyt** („wypisz”, „pokaż”, „streść”).
- Nigdy nie usuwaj/skaluj/wdrażaj bez zrozumienia dokładnego skutku.
- Przy każdej zmianie każ Gemini **najpierw wyjaśnić, co uruchomi i dlaczego** i potwierdź cel.

```text
Może zmienię rozmiar <zasób>. Najpierw wyjaśnij dokładnie, co to za zmiana, ryzyka
i jak ją cofnąć — NIE rób jeszcze żadnej zmiany.
```

---

## 🧩 Przydatne ruchy Azure

| Poproś o… | Dostajesz |
|----------|---------|
| „Wypisz subskrypcje / grupy zasobów” | Mapę chmury |
| „Pokaż konta magazynu / bazy w RG X” | Inwentarz bez portalu |
| „Co utworzono ostatnio, wg typu?” | Szybki audyt |
| „Wyjaśnij konfigurację tego zasobu” | Dokumentację prostym językiem |
| „Wyjaśnij zmianę przed jej wykonaniem” | Bezpieczeństwo przed akcją |

> ⚠️ **Zasięg szkód:** zmiany Azure są realne i mogą kosztować lub utracić dane. Domyślnie tylko-odczyt; rozumiej każdy zapis; uprawnienia `az login` to twarda granica.

---

## ✅ Sprawdzenie

- [ ] `az login` działa, a serwer Azure MCP jest dodany do Gemini CLI.
- [ ] Gemini wypisał subskrypcje/grupy zasobów.
- [ ] Uruchomiłeś kilka zapytań tylko-odczyt o prawdziwe zasoby.
- [ ] Umiesz wyjaśnić, czemu trzymasz prompty Azure tylko-odczyt podczas nauki.

---

## 🎯 Zadanie

Daj Gemini przewodnik tylko-odczyt po jednej subskrypcji: wypisz grupy zasobów, zinwentaryzuj największe i każ wyprodukować krótkie podsumowanie prostym językiem. Nie rób zmian.

---

## 💡 Najważniejsze wnioski

- **Serwer Azure MCP** działa **lokalnie** i wykorzystuje ponownie sesję **`az login`** — brak nowego sekretu, obowiązują Twoje uprawnienia.
- Dodaj go do Gemini CLI, potem odpytuj chmurę zwykłym językiem.
- Zmiany w chmurze są **wysokiego ryzyka** — zostań przy odczycie i każ Gemini wyjaśnić każdy zapis przed jego wykonaniem.

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Wstecz](03-atlassian-mcp.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)
