# E6 — Narzędzia i MCP na skalę: bezpieczeństwo i zarządzanie

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Potrzebne: serwery z E2–E5 dodane

🌐 [English](../../en/track-e/06-mcp-safety.md) · [← Wstecz](05-zbuduj-wlasny-serwer-mcp.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (5 min)

Gdy masz kilka serwerów MCP w Gemini CLI — GitHub, Atlassian, Azure, własny — plus wbudowane narzędzia plik/powłoka, wyzwanie przesuwa się z *podłączania* na **bezpieczne uruchamianie tego wszystkiego**. Trzy zasady niosą wszystko:

1. **Najmniejsze uprawnienia.** Daj każdemu serwerowi *najwęższy* dostęp, który wciąż wykonuje zadanie. Tylko-odczyt bije odczyt-zapis; jedno repo/serwis/subskrypcja bije „wszystko”.
2. **Człowiek w pętli.** CLI pyta przed akcjami zmieniającymi lub wysyłającymi — trzymaj to dla wszystkiego, co zapisuje, usuwa, wdraża lub pisze do ludzi. (Unikaj trybów „zatwierdzaj wszystko” podczas nauki.)
3. **Wiedz, co działa i gdzie.** Każdy serwer to program na PC (lokalny) lub autoryzowany link (zdalny). Trzymaj tylko te, które rozumiesz i którym ufasz.

### Jak różni się auth zależnie od typu

| Typ | Auth | Gdzie mieszka sekret |
|------|------|------------------------|
| **Zdalny OAuth** (Atlassian, GitHub) | Logowanie; zatwierdzasz zakresy | Trzymany przez dostawcę |
| **Lokalny, sesja** (Azure) | Twój istniejący `az login` | Sesja CLI maszyny |
| **Lokalny z tokenem** (niektóre) | Token, który ustawiasz w konfiguracji | Twój `settings.json` — jak hasło |
| **Twój własny serwer** | Działa jako *Ty* | Uprawnienia Twojego OS |

Najbezpieczniejszy domyślny: **serwery OAuth i oparte na sesji** — brak długożyjącego sekretu w pliku tekstowym.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zaudytuj, co podłączone

```text
/mcp
```
```text
/tools
```

Wypisz każdy serwer MCP i wbudowane narzędzia. Zapisz dla każdego: *do czego może sięgnąć i czy może zapisywać?*

### Krok 2 — Dokręć każdy do najmniejszych uprawnień

Dla każdego zapytaj „jaki najmniejszy zakres wciąż działa?”:
- Token GitHub z nieużywanym dostępem zapisu → obniż do tylko-odczyt.
- Serwer plików na folder domowy → skieruj na **jeden** folder projektu.
- Serwer do czegoś, czego już nie dotykasz → **usuń** go.

### Krok 3 — Usuń to, czego nie używasz

Mniej serwerów = mniej ryzyk i mniej zamieszania dla Gemini. Usuń stare wpisy (`gemini mcp remove <nazwa>` lub usuń z `settings.json`) i zrestartuj.

### Krok 4 — Trzymaj sekrety poza czystym tekstem

Jeśli serwer potrzebuje tokenu:
- Nigdy nie commituj `settings.json` z tokenem do gita ani nie wklejaj do czatu.
- Preferuj serwery używające **OAuth** lub **sesji CLI** nad wklejone tokeny.
- Zrotuj token natychmiast, jeśli wycieknie.

### Krok 5 — Ustaw dyscyplinę zatwierdzania

Zdecyduj zasadę i trzymaj się jej:

```text
Dla każdego narzędzia, które tworzy, edytuje, usuwa, wdraża lub cokolwiek wysyła,
pokaż mi dokładnie, co zrobisz, i poczekaj na moje wyraźne „tak”.
```

Powiedz to na początku sesji, w których Gemini ma narzędzia zdolne do zapisu. Unikaj włączania trybów uruchamiających wszystko automatycznie, aż w pełni zaufasz konfiguracji.

### Krok 6 — Diagnozuj spokojnie

Jeśli serwer się nie ładuje:
- **Zrestartuj** CLI (zmiany konfiguracji tego wymagają).
- Sprawdź, czy JSON jest poprawny (błędny przecinek psuje plik).
- Potwierdź, że polecenie działa samo w terminalu (`npx ...` / `python my_server.py`).
- Dla serwerów zdalnych ponów logowanie OAuth.

---

## 🔒 Checklista bezpieczeństwa

| Sprawdź | Dlaczego |
|-------|-----|
| Najmniejsze uprawnienia na serwer? | Najmniejszy zasięg szkód |
| Tylko-odczyt, gdzie możesz? | Nie zepsuje tego, czego nie zmieni |
| Zatwierdzenie człowieka na zapisach? | Zostajesz w kontroli |
| Sekrety w konfiguracji tekstowej? | Przenieś na OAuth/sesję, jeśli możesz |
| Usunięte serwery, których nie używasz? | Mniej ruchomych części |
| Ufasz źródłu każdego serwera? | Działa z realnym dostępem |
| Konfiguracja poza gitem/czatami? | Nie wyciekaj tokenów |

---

## ✅ Sprawdzenie

- [ ] Zaudytowałeś każdy serwer (`/mcp`) i wbudowane narzędzia (`/tools`).
- [ ] Dokręciłeś co najmniej jeden do najmniejszych uprawnień i usunąłeś jeden nieużywany.
- [ ] Żaden długożyjący sekret nie siedzi w konfiguracji tekstowej (albo wiesz który i czemu).
- [ ] Masz wyraźną zasadę zatwierdzania i unikasz zbiorczego auto-uruchamiania.

---

## 🎯 Zadanie

Napisz swoją „politykę narzędzi”: które serwery trzymasz, ich zakres, odczyt vs zapis i zasadę zatwierdzania. Zastosuj ją — usuń, obniż lub przeorganizuj wszystko, co nie pasuje. Wracaj co miesiąc.

---

## 💡 Najważniejsze wnioski

- Uruchamiaj narzędzia bezpiecznie przez **najmniejsze uprawnienia**, **człowieka w pętli** na zapisach i **wiedzę, co działa i gdzie**.
- Preferuj serwery **OAuth / oparte na sesji** nad wklejone tokeny; trzymaj `settings.json` poza gitem i czatami.
- **Audytuj i przycinaj** regularnie i nie włączaj zbiorczego auto-zatwierdzania, aż w pełni zaufasz konfiguracji.

🌐 [English](../../en/track-e/06-mcp-safety.md) · [← Wstecz](05-zbuduj-wlasny-serwer-mcp.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
