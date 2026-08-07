# G1 — AGENTS.md i kontekst projektu

⏱️ **15 minut** · Ścieżka: 🅶 Codex CLI w głąb · Wymagania: Codex CLI zainstalowany i zalogowany (zob. D5)

🌐 [English](../../en/track-g/01-agents-md-and-context.md) · [← Spis ścieżki](../README.md) · [Dalej: Tryby zatwierdzania i sandbox →](02-tryby-zatwierdzania-i-sandbox.md)

---

## 🧠 Teoria (4 min)

W D5 uruchomiłeś/aś Codex CLI na planie ChatGPT. Teraz uczynimy go *dobrym* — zaczynając od **kontekstu**.

Plik **AGENTS.md** to zwykły Markdown, który Codex **czyta automatycznie**, by poznać Twój projekt. Umieść tam stały kontekst — czym jest projekt, jak go uruchomić, konwencje, co robić i czego nie — i przestań tłumaczyć to co sesję. (`AGENTS.md` to otwarta konwencja, którą dzieli kilka agentów kodowych, więc ten sam plik pomaga też innym narzędziom.)

Kontekst jest **warstwowy**, co jest potężne:

- **Globalny** (`~/.codex/AGENTS.md`) — *Twoje* preferencje w każdym projekcie.
- **Projektowy** (`AGENTS.md` w korzeniu repo) — fakty o tym projekcie.
- **Podfolderowy** (`AGENTS.md` głębiej w drzewie) — szczegóły jednej części.

Codex scala je, najbardziej szczegółowe na końcu.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Utwórz projektowy AGENTS.md

W folderze prawdziwego projektu utwórz plik:

```powershell
notepad AGENTS.md
```

Dobry projektowy AGENTS.md zawiera:

```markdown
# Projekt: <nazwa>

## Czym to jest
Krótki opis i cel.

## Jak uruchomić
- Instalacja: <komenda>
- Uruchomienie: <komenda>
- Testy: <komenda>

## Konwencje
- Reguły języka/stylu do przestrzegania.
- Foldery i co gdzie mieszka.

## Rób / Nie rób
- Rób: trzymaj zmiany małe i wyjaśnione.
- Nie rób: nie ruszaj <x> ani nie dodawaj zależności bez pytania.
```

Teraz każda sesja startuje z tym załadowanym — bez tłumaczenia od nowa.

> Wskazówka: możesz poprosić Codeksa o szkic — „Spójrz na ten projekt i napisz AGENTS.md opisujący, czym jest, jak go uruchomić i jego konwencje". Przejrzyj przed zapisaniem.

### Krok 2 — Ustaw preferencje globalne

Utwórz globalny plik kontekstu dla nawyków, które podążają za *Tobą* wszędzie:

```powershell
notepad $HOME\.codex\AGENTS.md
```

```markdown
# Moje preferencje
- Jestem na Windowsie; podawaj komendy PowerShell.
- Bądź zwięzły; zaczynaj od odpowiedzi.
- Wyjaśniaj ryzykowne zmiany przed ich wykonaniem.
```

### Krok 3 — Potwierdź, że jest używany

Uruchom Codeksa w projekcie i zapytaj o coś, co polega na kontekście:

```text
Jak uruchomić i przetestować ten projekt? Odpowiedz tylko z własnych instrukcji projektu.
```

Jeśli powtarza Twój AGENTS.md, kontekst się ładuje.

### Krok 4 — Trzymaj go zwięzłym i aktualnym

- Umieść fakty, których Codex nie zgadnie (jak uruchomić, konwencje, strefy zakazane).
- Usuwaj cokolwiek nieaktualnego — błędny AGENTS.md wprowadza w błąd każdą sesję.
- Nie wklejaj sekretów; jest współdzielony z każdym, kto ma repo.

### Krok 5 — Umieszczaj fakty tam, gdzie należą

- Fakty projektu → projektowy `AGENTS.md`.
- Twoje osobiste nawyki → globalny `~/.codex/AGENTS.md`.
- Osobliwości jednej części → `AGENTS.md` w tym podfolderze.

---

## 🧩 Gdzie idzie kontekst

| Fakt | Umieść w |
|------|-----------|
| Jak uruchomić/testować ten projekt | Projektowy `AGENTS.md` |
| Konwencje projektu i strefy zakazane | Projektowy `AGENTS.md` |
| „Jestem na Windowsie, bądź zwięzły" | Globalny `~/.codex/AGENTS.md` |
| Specjalne reguły jednego modułu | Podfolderowy `AGENTS.md` |

---

## ✅ Sprawdzian

- [ ] Utworzyłeś/aś projektowy `AGENTS.md` z prawdziwym kontekstem.
- [ ] Utworzyłeś/aś globalny `~/.codex/AGENTS.md` ze swoimi preferencjami.
- [ ] Codex odpowiedział na pytanie, używając kontekstu Twojego projektu.
- [ ] Umiesz wyjaśnić warstwowanie globalny → projektowy → podfolderowy.

---

## 🎯 Praca domowa

Napisz prawdziwy AGENTS.md dla projektu, na którym Ci zależy (czym jest, jak go uruchomić, konwencje, strefy zakazane) i globalny ze swoimi osobistymi nawykami. Uruchom sesję i potwierdź, że Codex ich przestrzega.

---

## 💡 Najważniejsze wnioski

- **AGENTS.md** to auto-ładowany **kontekst projektu** — umieść tam stałe fakty i przestań tłumaczyć (osobiste nawyki idą do `~/.codex/AGENTS.md`).
- Jest **warstwowy**: globalny (Ty) → projektowy → podfolderowy, scalany najbardziej szczegółowo na końcu.
- Trzymaj go **zwięzłym, aktualnym i bez sekretów** — błędny AGENTS.md wprowadza w błąd każdą sesję.

🌐 [English](../../en/track-g/01-agents-md-and-context.md) · [← Spis ścieżki](../README.md) · [Dalej: Tryby zatwierdzania i sandbox →](02-tryby-zatwierdzania-i-sandbox.md)
