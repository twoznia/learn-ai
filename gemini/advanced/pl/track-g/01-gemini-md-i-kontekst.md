# G1 — GEMINI.md i kontekst (pamięć projektu)

⏱️ **15 minut** · Ścieżka: 🅶 Gemini CLI w głąb · Potrzebne: Gemini CLI zainstalowany i zalogowany (patrz D5)

🌐 [English](../../en/track-g/01-gemini-md-and-context.md) · [← Indeks ścieżki](../README.md) · [Dalej: Własne komendy →](02-wlasne-komendy.md)

---

## 🧠 Teoria (4 min)

W D5 uruchomiłeś Gemini CLI na koncie. Teraz zrobimy go *dobrym* — zaczynając od **plików kontekstu**.

Plik **GEMINI.md** to zwykły Markdown, który CLI **czyta automatycznie**, by poznać Twój projekt. Umieść tam stały kontekst — czym jest projekt, jak go uruchomić, konwencje, co robić i czego nie — i przestań tłumaczyć to co sesję.

Kontekst jest **hierarchiczny**, co jest potężne:

- **Globalny** (`~/.gemini/GEMINI.md`) — *Twoje* preferencje we wszystkich projektach.
- **Projektu** (`GEMINI.md` w korzeniu projektu) — fakty o tym projekcie.
- **Podfolderu** (`GEMINI.md` głębiej w drzewie) — detale jednej części.

CLI je scala, najbardziej szczegółowy na końcu. Zarządzasz nimi komendą `/memory`.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Wygeneruj GEMINI.md projektu

W prawdziwym folderze projektu uruchom CLI i:

```text
/init
```

CLI skanuje projekt i pisze **GEMINI.md** opisujący go. Otwórz plik — to zwykły Markdown do edycji.

### Krok 2 — Zrób go swoim

Dodaj rzeczy, które inaczej powtarzałbyś. Dobry GEMINI.md projektu zawiera:

```markdown
# Projekt: <nazwa>

## Czym to jest
Krótki opis i cel.

## Jak uruchomić
- Instalacja: <polecenie>
- Uruchomienie: <polecenie>
- Testy: <polecenie>

## Konwencje
- Zasady języka/stylu.
- Foldery i co gdzie mieszka.

## Rób / Nie rób
- Rób: małe zmiany z wyjaśnieniem.
- Nie: dotykaj <x> ani nie dodawaj zależności bez pytania.
```

Teraz każda sesja startuje z tym załadowanym — bez tłumaczenia.

### Krok 3 — Ustaw preferencje globalne

Utwórz globalny plik kontekstu na nawyki, które podążają za *Tobą* wszędzie:

```powershell
notepad $HOME\.gemini\GEMINI.md
```

```markdown
# Moje preferencje
- Jestem na Windows; podawaj polecenia PowerShell.
- Bądź zwięzły; zacznij od odpowiedzi.
- Wyjaśniaj ryzykowne zmiany przed ich wykonaniem.
```

### Krok 4 — Sprawdź, co załadowane

```text
/memory show
```

To pokazuje scalony kontekst używany przez CLI. Jeśli edytujesz GEMINI.md w trakcie:

```text
/memory refresh
```

### Krok 5 — Dodaj szybką notatkę bez edycji plików

```text
/memory add Zawsze preferuj wbudowane biblioteki nad nowe zależności.
```

Przydatne do faktu, który chcesz zapamiętać w trakcie sesji.

### Krok 6 — Umieść fakty tam, gdzie należą

- Fakty projektu → `GEMINI.md` projektu.
- Twoje osobiste nawyki → globalny `~/.gemini/GEMINI.md`.
- Dziwactwa jednej części → `GEMINI.md` w tym podfolderze.

---

## 🧩 Gdzie trafia kontekst

| Fakt | Umieść w |
|------|-----------|
| Jak uruchomić/testować projekt | `GEMINI.md` projektu |
| Konwencje i strefy zakazane | `GEMINI.md` projektu |
| „Jestem na Windows, bądź zwięzły” | Globalny `~/.gemini/GEMINI.md` |
| Specjalne zasady jednego modułu | `GEMINI.md` w podfolderze |
| Przypomnienie w trakcie sesji | `/memory add` |

---

## ✅ Sprawdzenie

- [ ] Wygenerowałeś `GEMINI.md` przez `/init` i dodałeś prawdziwy kontekst.
- [ ] Utworzyłeś globalny `~/.gemini/GEMINI.md` z preferencjami.
- [ ] Zobaczyłeś scalony kontekst przez `/memory show`.
- [ ] Umiesz wyjaśnić hierarchię globalny → projekt → podfolder.

---

## 🎯 Zadanie

Napisz prawdziwy GEMINI.md projektu (czym jest, jak uruchomić, konwencje, strefy zakazane) i globalny z osobistymi nawykami. Uruchom sesję i potwierdź przez `/memory show`, że oba są załadowane.

---

## 💡 Najważniejsze wnioski

- **GEMINI.md** to auto-ładowany **kontekst/pamięć** — umieść tam stałe fakty i przestań tłumaczyć.
- Kontekst jest **hierarchiczny**: globalny (Ty) → projekt → podfolder, scalany najbardziej szczegółowy na końcu.
- Zarządzaj nim przez **`/memory show`, `/memory refresh`, `/memory add`**.

🌐 [English](../../en/track-g/01-gemini-md-and-context.md) · [← Indeks ścieżki](../README.md) · [Dalej: Własne komendy →](02-wlasne-komendy.md)
