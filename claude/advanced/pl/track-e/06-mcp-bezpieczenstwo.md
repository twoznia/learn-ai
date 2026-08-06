# E6 — MCP na skalę: auth, bezpieczeństwo i zarządzanie

⏱️ **15 minut** · Ścieżka: 🅴 Mistrzostwo MCP · Potrzebne: serwery z E2–E5 podłączone

🌐 [English](../../en/track-e/06-mcp-at-scale-security.md) · [← Wstecz](05-zbuduj-wlasny-serwer-mcp.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (5 min)

Gdy masz kilka serwerów MCP — GitHub, Atlassian, Azure, własny — wyzwanie przesuwa się z *podłączania* na **bezpieczne uruchamianie i utrzymanie porządku**. Trzy zasady niosą wszystko:

1. **Najmniejsze uprawnienia.** Daj każdemu serwerowi *najwęższy* dostęp, który wciąż wykonuje zadanie. Tylko-odczyt bije odczyt-zapis; jedno repo/serwis/subskrypcja bije „wszystko”.
2. **Człowiek w pętli.** Claude pyta przed akcjami zmieniającymi lub wysyłającymi rzeczy. Nigdy nie wyłączaj tego odruchu dla narzędzi, które zapisują, usuwają, wdrażają lub piszą do ludzi.
3. **Wiedz, co działa i gdzie.** Każdy serwer to albo program na Twoim PC (lokalny), albo autoryzowany link do chmury (zdalny). Trzymaj tylko te, które rozumiesz i którym ufasz.

### Jak różni się auth zależnie od typu serwera

| Typ | Auth | Gdzie mieszka sekret |
|------|------|------------------------|
| **Konektor zdalny** (GitHub, Atlassian) | Logowanie OAuth; zatwierdzasz zakresy | Trzymany przez dostawcę, nie wklejany przez Ciebie |
| **Lokalny, wykorzystuje sesję** (Azure) | Twój istniejący `az login` | Sesja CLI Twojej maszyny |
| **Lokalny z tokenem** (niektóre serwery) | Token, który ustawiasz w konfiguracji | Twój plik konfig. — traktuj jak hasło |
| **Twój własny serwer** | Działa jako *Ty* | Uprawnienia Twojego OS |

Najbezpieczniejszy domyślny to **konektory OAuth i serwery lokalne oparte na sesji** — brak długożyjącego sekretu w pliku tekstowym.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zaudytuj, co jest podłączone

- **Zdalne:** aplikacja Claude → **Settings → Connectors**. Wypisz każdy włączony konektor.
- **Lokalne:** otwórz konfigurację i wypisz każdy wpis `mcpServers`.

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Zapisz dla każdego: *do czego może sięgnąć i czy może zapisywać?*

### Krok 2 — Dokręć każdy do najmniejszych uprawnień

Dla każdego serwera zapytaj „jaki najmniejszy zakres wciąż działa?” i napraw:

- Token GitHub z dostępem zapisu, którego nie używasz → obniż do tylko-odczyt.
- Serwer plików skierowany na Twój folder domowy → skieruj na **jeden** folder projektu.
- Konektor do serwisu, którego już nie dotykasz → **odłącz** go.

### Krok 3 — Usuń to, czego nie używasz

Mniej serwerów = mniej ryzyk i mniej zamieszania dla Claude. Usuń stare wpisy lokalne i odłącz nieużywane konektory. Zrestartuj Claude Desktop po edycji konfiguracji.

### Krok 4 — Trzymaj sekrety poza czystym tekstem

Jeśli jakiś serwer lokalny potrzebuje tokenu:
- Nigdy nie commituj konfiguracji do gita ani nie wklejaj jej do czatu.
- Preferuj serwery używające **OAuth** lub **sesji CLI** nad te wymagające wklejonego tokenu.
- Zrotuj token natychmiast, jeśli kiedykolwiek wycieknie.

### Krok 5 — Ustaw swoją dyscyplinę zatwierdzania

Zdecyduj swoją osobistą zasadę i trzymaj się jej:

```text
Dla każdego narzędzia, które tworzy, edytuje, usuwa, wdraża lub cokolwiek wysyła,
pokaż mi dokładnie, co zrobisz, i poczekaj na moje wyraźne „tak”.
```

Powiedz to na początku sesji, w których Claude ma narzędzia zdolne do zapisu. To ponownie uzbraja bramkę człowieka.

### Krok 6 — Diagnozuj połączenia spokojnie

Jeśli serwer się nie ładuje:
- Całkowicie **zamknij i otwórz** Claude Desktop (zmiany konfiguracji wymagają restartu).
- Sprawdź, czy JSON jest poprawny (błędny przecinek psuje cały plik).
- Potwierdź, że polecenie działa samo (`npx ...` / `python my_server.py` w terminalu).
- Dla konektorów zdalnych ponów logowanie OAuth.

---

## 🔒 Checklista bezpieczeństwa MCP

| Sprawdź | Dlaczego |
|-------|-----|
| Najmniejsze uprawnienia na serwer? | Najmniejszy zasięg szkód |
| Tylko-odczyt, gdzie możesz? | Nie zepsuje tego, czego nie zmieni |
| Zatwierdzenie człowieka na wszystkich zapisach? | Zostajesz w kontroli |
| Jakieś sekrety w konfiguracji tekstowej? | Przenieś na OAuth/sesję, jeśli możesz |
| Usunięte serwery, których nie używasz? | Mniej ruchomych części |
| Czy ufam źródłu każdego serwera? | Działa z realnym dostępem |
| Konfiguracja poza gitem/czatami? | Nie wyciekaj tokenów |

---

## ✅ Sprawdzenie

- [ ] Zaudytowałeś każdy podłączony serwer (zdalny i lokalny).
- [ ] Dokręciłeś co najmniej jeden do najmniejszych uprawnień i usunąłeś co najmniej jeden nieużywany.
- [ ] Żaden długożyjący sekret nie siedzi w konfiguracji tekstowej (albo wiesz dokładnie który i czemu).
- [ ] Masz wyraźną zasadę zatwierdzania dla narzędzi zdolnych do zapisu.

---

## 🎯 Zadanie

Napisz swoją osobistą „politykę MCP” w notatce: które serwery trzymasz, ich zakres, odczyt vs zapis i Twoją zasadę zatwierdzania. Zastosuj ją — odłącz, obniż lub usuń wszystko, co nie pasuje. Wracaj do niej co miesiąc.

---

## 💡 Najważniejsze wnioski

- Skaluj MCP bezpiecznie przez **najmniejsze uprawnienia**, **człowieka w pętli** na zapisach i **wiedzę, co działa i gdzie**.
- Preferuj **konektory OAuth** i serwery lokalne **oparte na sesji** nad wklejone tokeny; trzymaj konfiguracje poza gitem i czatami.
- **Audytuj i przycinaj** regularnie — mniej, ściśle ograniczonych serwerów jest bezpieczniejsze i łatwiejsze dla Claude.

🌐 [English](../../en/track-e/06-mcp-at-scale-security.md) · [← Wstecz](05-zbuduj-wlasny-serwer-mcp.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
