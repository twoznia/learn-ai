# E4 — Azure w Codex CLI

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: konto Azure, Node.js + Azure CLI, Codex CLI

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Poprzedni](03-atlassian-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)

---

## 🧠 Teoria (4 min)

**Serwer MCP Azure** pozwala GPT eksplorować i pracować z Twoimi **zasobami chmury Azure** — magazynem, bazami danych, grupami zasobów, Key Vault, logami — przez język naturalny.

Azure MCP zwykle uruchamia się **lokalnie**: mały serwer odpalany przez `npx`, który rozmawia z Azure, używając poświadczeń, którymi już jesteś zalogowany/a (Azure CLI). To więc wzorzec **serwera lokalnego** z E1.

Dlaczego lokalnie + Twoje istniejące logowanie to zaleta:
- **Brak nowego sekretu do wklejenia** — używa ponownie Twojej sesji `az login`.
- **Obowiązują Twoje uprawnienia** — GPT może dotknąć tylko tego, co już może Twoje konto Azure.

> Nazwy pakietów i komendy serwera Azure MCP Microsoftu mogą się zmieniać. Jeśli `@azure/mcp` się nie uruchamia, sprawdź bieżącą dokumentację Microsoftu **„Azure MCP Server"** po dokładny pakiet/komendę i podmień.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zaloguj się do Azure lokalnie

Zainstaluj Azure CLI, jeśli trzeba, potem:

```powershell
az login
```

Otworzy się przeglądarka; zaloguj się. Tę sesję Azure MCP użyje ponownie.

### Krok 2 — Dodaj serwer Azure MCP

Dodaj go do Codex CLI:

```powershell
codex mcp add azure -- npx -y @azure/mcp@latest server start
```

> Lub dodaj to samo pod `[mcp_servers.azure]` w `~/.codex/config.toml`. Zrestartuj Codeksa, by uruchomił serwer.

### Krok 3 — Potwierdź i eksploruj, tylko-do-odczytu

```text
/mcp
```

Potem patrz, nigdy nie zmieniaj:

```text
Wylistuj moje subskrypcje Azure, a dla domyślnej wylistuj grupy zasobów.
```
```text
Pokaż konta magazynu w grupie zasobów <nazwa> i ich lokalizacje.
```

GPT uruchamia narzędzia Azure lokalnie i zwraca wyniki na żywo — przewodnik po Twojej chmurze.

### Krok 4 — Zadawaj prawdziwe pytania

```text
Które zasoby w subskrypcji <nazwa> utworzono najbardziej niedawno? Zgrupuj je według typu.
```
```text
Podsumuj kontenery w koncie magazynu <nazwa> i z grubsza, ile każdy przechowuje.
```

Odpytujesz swoją chmurę prostym językiem zamiast szukać w portalu.

### Krok 5 — Bądź rozważny/a przy zmianach

Akcje Azure mogą kosztować pieniądze lub usuwać dane. Podczas nauki:
- Trzymaj prompty **tylko-do-odczytu** („wylistuj", „pokaż", „podsumuj").
- Nigdy nie usuwaj/skaluj/wdrażaj bez zrozumienia dokładnego efektu.
- Przy każdej zmianie każ GPT **najpierw wyjaśnić, co uruchomi i dlaczego**, i potwierdź cel.

```text
Może zmienię rozmiar <zasób>. Najpierw wyjaśnij dokładnie, jaka to zmiana, ryzyka
i jak ją cofnąć — NIE wprowadzaj jeszcze żadnej zmiany.
```

---

## 🧩 Przydatne ruchy z Azure

| Poproś o… | Dostajesz |
|----------|---------|
| „Wylistuj subskrypcje / grupy zasobów" | Mapę Twojej chmury |
| „Pokaż konta magazynu / bazy w RG X" | Inwentarz bez portalu |
| „Co utworzono niedawno, według typu?" | Szybki audyt |
| „Wyjaśnij konfigurację tego zasobu" | Dokumentacja prostym językiem |
| „Wyjaśnij zmianę przed jej wykonaniem" | Bezpieczeństwo przed akcją |

> ⚠️ **Zasięg rażenia:** zmiany w Azure są prawdziwe i mogą kosztować pieniądze lub utracić dane. Domyślnie tylko-do-odczytu; rozumiej każdy zapis; uprawnienia `az login` to twardy limit.

---

## ✅ Sprawdzian

- [ ] `az login` działa, a serwer Azure MCP jest dodany do Codeksa.
- [ ] GPT wylistował Twoje subskrypcje/grupy zasobów.
- [ ] Uruchomiłeś/aś kilka zapytań tylko-do-odczytu o prawdziwe zasoby.
- [ ] Umiesz wyjaśnić, czemu trzymasz prompty Azure tylko-do-odczytu podczas nauki.

---

## 🎯 Praca domowa

Daj GPT tylko-do-odczytu wycieczkę po jednej subskrypcji: wylistuj grupy zasobów, zinwentaryzuj największą i niech wytworzy krótkie, prostym językiem podsumowanie tego, co masz uruchomione. Nie wprowadzaj żadnych zmian.

---

## 💡 Najważniejsze wnioski

- **Serwer Azure MCP** działa **lokalnie** i używa ponownie Twojej sesji **`az login`** — bez nowego sekretu, obowiązują Twoje uprawnienia.
- Dodaj go do Codex CLI, potem odpytuj swoją chmurę prostym językiem.
- Zmiany w chmurze są **wysokiego ryzyka** — pozostań tylko-do-odczytu i każ GPT wyjaśnić każdy zapis, zanim nastąpi.

🌐 [English](../../en/track-e/04-azure-mcp.md) · [← Poprzedni](03-atlassian-mcp.md) · [Spis ścieżki](../README.md) · [Dalej: Zbuduj własny serwer →](05-zbuduj-wlasny-serwer-mcp.md)
