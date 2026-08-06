# G2 — Komendy ukośnik (wbudowane i własne)

⏱️ **15 minut** · Ścieżka: 🅶 Claude Code w głąb · Potrzebne: Claude Code zainstalowany i zalogowany

🌐 [English](../../en/track-g/02-slash-commands.md) · [← Wstecz](01-claude-md-i-tryb-planowania.md) · [Indeks ścieżki](../README.md) · [Dalej: Podagenci →](03-podagenci.md)

---

## 🧠 Teoria (4 min)

**Komendy ukośnik** to skróty wpisywane w Claude Code, zaczynające się od `/`. Dwa rodzaje:

- **Wbudowane** — komendy dostarczane z Claude Code: zarządzają sesją, modelami, MCP, pamięcią i więcej.
- **Własne** — komendy, które *Ty* tworzysz. Własna komenda to po prostu **plik Markdown**; jego zawartość staje się promptem wielokrotnego użytku, który odpalasz przez `/<nazwa>`. Tak zamieniasz powtarzalny przepływ („zrecenzuj ten kod”, „napisz wiadomość commita”, „wyjaśnij ten plik”) w jedno naciśnięcie.

Własne komendy to najszybszy sposób ujednolicenia, jak pracujesz z Claude Code.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zwiedź wbudowane

W Claude Code wpisz `/` i przeczytaj listę. Przydatne do zapamiętania:

| Komenda | Robi |
|---------|------|
| `/help` | Wypisz dostępne komendy |
| `/init` | Wygeneruj `CLAUDE.md` projektu (G1) |
| `/clear` | Zacznij świeży kontekst (jak nowy czat) |
| `/model` | Przełącz model (Sonnet/Opus…) |
| `/agents` | Zarządzaj podagentami (G3) |
| `/mcp` | Zarządzaj serwerami MCP (G5) |

Wypróbuj `/clear` między niezwiązanymi zadaniami — ten sam nawyk „jedno zadanie = jeden kontekst” z D2, i oszczędza tokeny.

### Krok 2 — Utwórz pierwszą własną komendę

Własne komendy mieszkają w folderze `.claude/commands/` w projekcie. Utwórz jedną:

```powershell
mkdir .claude\commands
notepad .claude\commands\explain.md
```

Wstaw prompt wielokrotnego użytku:

```markdown
Wyjaśnij plik, który wskażę, prostym językiem dla początkującego:
co robi, jego główne części i cokolwiek ryzykownego. Zmieść się w 200 słowach.
```

Zapisz. Teraz w Claude Code:

```text
/explain
```

Twój prompt się uruchamia — bez przepisywania.

### Krok 3 — Przekazuj argumenty

Uelastycznij komendy przez `$ARGUMENTS`. Utwórz `.claude/commands/commit.md`:

```markdown
Napisz jasną wiadomość commita git dla obecnie zastagowanych zmian.
Jeśli dałem dodatkowy kontekst, użyj go: $ARGUMENTS
Temat poniżej 60 znaków; dodaj krótkie ciało, jeśli trzeba.
```

Potem:

```text
/commit skup się na poprawce bezpieczeństwa
```

Claude użyje Twojego tekstu tam, gdzie stoi `$ARGUMENTS`.

### Krok 4 — Zbuduj małą bibliotekę komend

Dodaj komendy do powtarzalnych robót:

- `.claude/commands/review.md` — „Zrecenzuj moje ostatnie zmiany pod kątem błędów i jasności; wypisz znaleziska wg wagi.”
- `.claude/commands/readme.md` — „Naszkicuj/zaktualizuj README dla projektu z kodu.”
- `.claude/commands/plan.md` — „Zaproponuj plan krok po kroku dla zadania, które opiszę; nie edytuj jeszcze.”

Każda staje się `/review`, `/readme`, `/plan`.

### Krok 5 — Komendy osobiste vs projektu

- **Komendy projektu** (`.claude/commands/` w repo) idą z projektem — świetne do konwencji zespołu.
- **Komendy osobiste** (w Twoim folderze użytkownika Claude Code) podążają za *Tobą* we wszystkich projektach.

Przepływy zespołu do projektu; osobiste pomocniki do folderu użytkownika.

---

## 🧩 Dobre własne komendy

| Komenda | Zamienia tę robotę w jedno naciśnięcie |
|---------|-------------------------------------|
| `/review` | Recenzowanie własnych zmian |
| `/commit` | Pisanie dobrej wiadomości commita |
| `/explain` | Zrozumienie nieznanego pliku |
| `/plan` | Uzyskanie planu przed edycjami |
| `/readme` | Utrzymanie dokumentacji aktualnej |

> 💡 Plik komendy to po prostu prompt. Jeśli wciąż wpisujesz tę samą prośbę, zrób z niej komendę.

---

## ✅ Sprawdzenie

- [ ] Zwiedziłeś wbudowane komendy i użyłeś `/clear` między zadaniami.
- [ ] Utworzyłeś własną komendę `/explain` i ją uruchomiłeś.
- [ ] Zrobiłeś komendę używającą `$ARGUMENTS`.
- [ ] Umiesz wyjaśnić komendy projektu vs osobiste.

---

## 🎯 Zadanie

Zamień trzy najczęściej powtarzane prośby do Claude Code w własne komendy. Daj jednej slot `$ARGUMENTS`. Używaj ich przez dzień i dopracuj brzmienie tam, gdzie wyjście nie jest idealne.

---

## 💡 Najważniejsze wnioski

- **Wbudowane** komendy ukośnik zarządzają sesją; `/clear`, `/model`, `/init`, `/agents`, `/mcp` warto znać.
- **Własne komendy** to pliki Markdown (`.claude/commands/*.md`) stające się `/<nazwa>` — Twoje powtarzalne prompty, jedno naciśnięcie.
- Używaj **`$ARGUMENTS`** dla elastyczności; przepływy zespołu do projektu, osobiste pomocniki do folderu użytkownika.

🌐 [English](../../en/track-g/02-slash-commands.md) · [← Wstecz](01-claude-md-i-tryb-planowania.md) · [Indeks ścieżki](../README.md) · [Dalej: Podagenci →](03-podagenci.md)
