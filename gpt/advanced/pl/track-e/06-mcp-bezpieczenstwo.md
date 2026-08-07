# E6 — Narzędzia i MCP na skalę: bezpieczeństwo i zarządzanie

⏱️ **15 minut** · Ścieżka: 🅴 Narzędzia i MCP · Wymagania: serwery z E2–E5 dodane

🌐 [English](../../en/track-e/06-mcp-safety.md) · [← Poprzedni](05-zbuduj-wlasny-serwer-mcp.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)

---

## 🧠 Teoria (5 min)

Gdy masz w Codex CLI kilka serwerów MCP — GitHub, Atlassian, Azure, własny — plus wbudowane narzędzia plikowe/powłoki Codeksa, wyzwanie przesuwa się z *podłączania* na **bezpieczne uruchamianie tego wszystkiego**. Trzy zasady niosą całość:

1. **Najmniejszy przywilej.** Daj każdemu serwerowi *najwęższy* dostęp, który wciąż wykonuje zadanie. Tylko-do-odczytu bije zapis; jedno repo/witryna/subskrypcja bije „wszystko".
2. **Człowiek w pętli.** Codex pyta przed akcjami, które coś zmieniają lub wysyłają, i domyślnie działa w piaskownicy (Ścieżka G). Trzymaj zatwierdzenia włączone dla wszystkiego, co zapisuje, usuwa, wdraża lub wysyła wiadomości do ludzi — nie przeskakuj na tryb „pełnej automatyki" podczas nauki.
3. **Wiedz, co się uruchamia i gdzie.** Każdy serwer to albo program na Twoim PC (lokalny), albo autoryzowane łącze (zdalny). Trzymaj tylko te, które rozumiesz i którym ufasz.

### Jak różni się uwierzytelnianie według typu serwera

| Typ | Uwierzytelnianie | Gdzie mieszka sekret |
|------|------|------------------------|
| **Zdalny, OAuth** (Atlassian, GitHub) | Logowanie; zatwierdzasz zakresy | Trzyma go dostawca |
| **Lokalny, używa sesji** (Azure) | Twoje istniejące `az login` | Sesja CLI Twojej maszyny |
| **Lokalny z tokenem** (część serwerów) | Token ustawiony w configu | Twój `config.toml` — traktuj jak hasło |
| **Twój własny serwer** | Działa jako *Ty* | Uprawnienia Twojego OS |

Najbezpieczniejszy domyślny wybór: **serwery OAuth i oparte na sesji** — brak długożyjącego sekretu w pliku tekstowym.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zrób audyt podłączonego

```text
/mcp
```

Wylistuj każdy serwer MCP (i przypomnij sobie wbudowane narzędzia plikowe/powłoki Codeksa). Zanotuj dla każdego: *do czego może sięgnąć i czy może zapisywać?*

### Krok 2 — Dociśnij każdy do najmniejszego przywileju

Dla każdego serwera zapytaj „jaki jest najmniejszy zakres, który wciąż działa?":
- Token GitHuba z nieużywanym dostępem do zapisu → obniż do tylko-do-odczytu.
- Serwer systemu plików wskazany na folder domowy → wskaż go na **jeden** folder projektu.
- Serwer czegoś, czego już nie dotykasz → **usuń** go.

### Krok 3 — Usuń, czego nie używasz

Mniej serwerów = mniej ryzyk i mniej zamieszania dla GPT. Usuń nieświeże wpisy (`codex mcp remove <nazwa>` lub usuń z `config.toml`) i zrestartuj.

### Krok 4 — Trzymaj sekrety poza czystym tekstem

Jeśli serwer potrzebuje tokena:
- Nigdy nie commituj `config.toml` z tokenem do git ani nie wklejaj go do czatu.
- Wolej serwery używające **OAuth** lub **sesji CLI** niż wklejane tokeny.
- Natychmiast rotuj token, jeśli wycieknie.

### Krok 5 — Ustal swoją dyscyplinę zatwierdzania

**Tryb zatwierdzania** Codeksa (Ścieżka G) to Twój główny wyłącznik. Podczas nauki niech pyta przed edycjami i poleceniami:

```text
Dla każdego narzędzia, które tworzy, edytuje, usuwa, wdraża lub cokolwiek wysyła,
pokaż mi dokładnie, co zrobisz, i poczekaj najpierw na moje wyraźne „tak".
```

Nie przełączaj na tryb pełnej automatyki, dopóki w pełni nie zaufasz konfiguracji i nie jesteś w bezpiecznym folderze.

### Krok 6 — Rozwiązuj problemy spokojnie

Jeśli serwer się nie ładuje:
- **Zrestartuj** Codeksa (zmiany configu tego wymagają).
- Sprawdź, czy TOML jest poprawny (literówka psuje plik).
- Potwierdź, że komenda działa sama w terminalu (`npx ...` / `python my_server.py`).
- Dla serwerów zdalnych ponów logowanie OAuth.

---

## 🔒 Lista kontrolna bezpieczeństwa

| Sprawdź | Dlaczego |
|-------|-----|
| Najmniejszy przywilej na serwer? | Najmniejszy zasięg rażenia |
| Tylko-do-odczytu, gdzie się da? | Nie zepsuje tego, czego nie może zmienić |
| Zatwierdzenie człowieka przy każdym zapisie? | Zostajesz w kontroli |
| Jakieś sekrety w configu w czystym tekście? | Przenieś na OAuth/sesję, jeśli możliwe |
| Usunięte serwery, których nie używasz? | Mniej ruchomych części |
| Ufasz źródłu każdego serwera? | Działa z prawdziwym dostępem |
| Config trzymany poza git/czatami? | Nie wyciekaj tokenów |

---

## ✅ Sprawdzian

- [ ] Zrobiłeś/aś audyt każdego serwera (`/mcp`).
- [ ] Docisnąłeś/ęłaś co najmniej jeden do najmniejszego przywileju i usunąłeś/ęłaś jeden nieużywany.
- [ ] Żaden długożyjący sekret nie siedzi w configu w czystym tekście (albo wiesz dokładnie, który i dlaczego).
- [ ] Masz wyraźną zasadę zatwierdzania i nie włączyłeś/aś pełnej automatyki.

---

## 🎯 Praca domowa

Napisz swoją osobistą „politykę narzędzi": które serwery trzymasz, ich zakres, odczyt vs zapis i Twoją zasadę zatwierdzania. Zastosuj ją — usuń, obniż lub przeskaluj cokolwiek, co nie pasuje. Wracaj do niej co miesiąc.

---

## 💡 Najważniejsze wnioski

- Uruchamiaj narzędzia bezpiecznie z **najmniejszym przywilejem**, **człowiekiem w pętli** przy zapisach i **wiedząc, co działa gdzie**.
- Wolej serwery **OAuth / oparte na sesji** niż wklejane tokeny; trzymaj `config.toml` poza git i czatami.
- **Audytuj i przycinaj** regularnie i nie przełączaj Codeksa na pełną automatykę, dopóki w pełni nie zaufasz konfiguracji.

🌐 [English](../../en/track-e/06-mcp-safety.md) · [← Poprzedni](05-zbuduj-wlasny-serwer-mcp.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)
