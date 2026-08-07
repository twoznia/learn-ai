# G2 — Własne komendy (i wbudowane)

⏱️ **15 minut** · Ścieżka: 🅶 Gemini CLI w głąb · Potrzebne: Gemini CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/02-custom-commands.md) · [← Wstecz](01-gemini-md-i-kontekst.md) · [Indeks ścieżki](../README.md) · [Dalej: Narzędzia i zatwierdzenia →](03-narzedzia-i-zatwierdzenia.md)

---

## 🧠 Teoria (4 min)

**Komendy ukośnik** to skróty wpisywane w Gemini CLI, zaczynające się od `/`. Dwa rodzaje:

- **Wbudowane** — komendy dostarczane z CLI do zarządzania sesją, pamięcią, narzędziami i MCP.
- **Własne** — komendy, które *Ty* tworzysz. W Gemini CLI własna komenda to mały plik **TOML**; jego `prompt` staje się prośbą wielokrotnego użytku, którą odpalasz przez `/<nazwa>`. To zamienia powtarzalny przepływ („zrecenzuj kod”, „napisz commit”, „wyjaśnij plik”) w jedno naciśnięcie.

Własne komendy to najszybszy sposób ujednolicenia pracy.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zwiedź wbudowane

Wpisz `/` i przeczytaj listę. Warto znać:

| Komenda | Robi |
|---------|------|
| `/help` | Wypisz komendy |
| `/init` | Wygeneruj `GEMINI.md` projektu (G1) |
| `/memory` | Pokaż/odśwież/dodaj kontekst (G1) |
| `/tools` | Wypisz wbudowane narzędzia (G3) |
| `/mcp` | Wypisz serwery MCP (Ścieżka E) |
| `/chat` | Zapisz / wznów rozmowę |
| `/clear` | Wyczyść ekran/kontekst do świeżego startu |

Używaj `/clear` między niezwiązanymi zadaniami — nawyk „jedno zadanie = jeden kontekst” z D2, który też oszczędza użycie.

### Krok 2 — Utwórz pierwszą własną komendę

Własne komendy mieszkają w folderze `commands` — projektu (`.gemini/commands/`) lub globalnym (`~/.gemini/commands/`). Utwórz jedną:

```powershell
mkdir .gemini\commands
notepad .gemini\commands\explain.toml
```

Wstaw `prompt`:

```toml
description = "Wyjaśnij plik prostym językiem"
prompt = """
Wyjaśnij plik, który wskażę, prostym językiem dla początkującego:
co robi, jego główne części i cokolwiek ryzykownego. Zmieść się w 200 słowach.
"""
```

Zapisz. Teraz w CLI:

```text
/explain
```

Twój prompt się uruchamia — bez przepisywania.

### Krok 3 — Przekazuj argumenty

Uelastycznij komendy przez `{{args}}`. Utwórz `.gemini/commands/commit.toml`:

```toml
description = "Napisz wiadomość commita"
prompt = """
Napisz jasną wiadomość commita git dla obecnie zastagowanych zmian.
Jeśli dałem dodatkowy kontekst, użyj go: {{args}}
Temat poniżej 60 znaków; dodaj krótkie ciało, jeśli trzeba.
"""
```

Potem:

```text
/commit skup się na poprawce bezpieczeństwa
```

Twój tekst ląduje tam, gdzie stoi `{{args}}`.

### Krok 4 — Zbuduj małą bibliotekę komend

- `.gemini/commands/review.toml` — „Zrecenzuj moje ostatnie zmiany pod kątem błędów i jasności; wypisz znaleziska wg wagi.”
- `.gemini/commands/readme.toml` — „Naszkicuj/zaktualizuj README z kodu.”
- `.gemini/commands/plan.toml` — „Zaproponuj plan krok po kroku dla zadania; nie edytuj jeszcze.”

Każda staje się `/review`, `/readme`, `/plan`.

### Krok 5 — Przestrzenie nazw i zakres

- **Podfoldery tworzą przestrzenie nazw:** `.gemini/commands/git/commit.toml` staje się `/git:commit`.
- **Projekt vs globalny:** komendy projektu (`.gemini/commands/`) idą z repo; globalne (`~/.gemini/commands/`) podążają za Tobą wszędzie.

> Format pliku komendy i składnia argumentów mogą ewoluować — uruchom `/help` lub sprawdź aktualną dokumentację Gemini CLI, jeśli komenda się nie ładuje.

---

## 🧩 Dobre własne komendy

| Komenda | Zamienia tę robotę w jedno naciśnięcie |
|---------|-------------------------------------|
| `/review` | Recenzowanie własnych zmian |
| `/commit` | Pisanie dobrej wiadomości commita |
| `/explain` | Zrozumienie nieznanego pliku |
| `/plan` | Uzyskanie planu przed edycjami |
| `/readme` | Utrzymanie dokumentacji aktualnej |

---

## ✅ Sprawdzenie

- [ ] Zwiedziłeś wbudowane komendy i użyłeś `/clear` między zadaniami.
- [ ] Utworzyłeś własną komendę `/explain` (TOML) i ją uruchomiłeś.
- [ ] Zrobiłeś komendę używającą `{{args}}`.
- [ ] Umiesz wyjaśnić komendy projektu vs globalne i przestrzenie nazw podfolderów.

---

## 🎯 Zadanie

Zamień trzy najczęściej powtarzane prośby do Gemini CLI w własne komendy TOML. Daj jednej slot `{{args}}`. Używaj ich przez dzień i dopracuj brzmienie tam, gdzie wyjście nie jest idealne.

---

## 💡 Najważniejsze wnioski

- **Wbudowane** komendy zarządzają sesją; `/clear`, `/memory`, `/tools`, `/mcp`, `/chat` warto znać.
- **Własne komendy** to pliki TOML (`.gemini/commands/*.toml`), których `prompt` staje się `/<nazwa>` — Twoje powtarzalne prompty, jedno naciśnięcie.
- Używaj **`{{args}}`**, **przestrzeni nazw podfolderów** i zakresu **projekt vs globalny**, by je organizować.

🌐 [English](../../en/track-g/02-custom-commands.md) · [← Wstecz](01-gemini-md-i-kontekst.md) · [Indeks ścieżki](../README.md) · [Dalej: Narzędzia i zatwierdzenia →](03-narzedzia-i-zatwierdzenia.md)
