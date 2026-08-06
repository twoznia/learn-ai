# G1 — CLAUDE.md i tryb planowania

⏱️ **15 minut** · Ścieżka: 🅶 Claude Code w głąb · Potrzebne: Claude Code zainstalowany i zalogowany (patrz D5)

🌐 [English](../../en/track-g/01-claude-md-and-plan-mode.md) · [← Indeks ścieżki](../README.md) · [Dalej: Komendy ukośnik →](02-komendy-ukosnik.md)

---

## 🧠 Teoria (4 min)

W D5 uruchomiłeś Claude Code na abonamencie. Teraz zrobimy go *dobrym* — zaczynając od dwóch nawyków, które dzielą frustrującą sesję od świetnej:

- **CLAUDE.md — pamięć projektu.** Zwykły plik Markdown w projekcie, który Claude Code **czyta automatycznie** w każdej sesji. Umieść tam stały kontekst — czym jest projekt, jak go uruchomić, konwencje, co robić i czego nie — i przestań tłumaczyć go w każdym czacie.
- **Tryb planowania — myśl, zanim dotkniesz.** Tryb, w którym Claude **najpierw bada i proponuje plan**, i nic nie edytuje, aż zatwierdzisz. Idealny do czegokolwiek nietrywialnego: przeglądasz podejście przed zmianami kodu.

Razem: Claude, który **zna Twój projekt** i **planuje przed działaniem**.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Wygeneruj CLAUDE.md

W prawdziwym folderze projektu uruchom Claude Code i komendę init:

```text
/init
```

Claude skanuje projekt i pisze **CLAUDE.md** opisujący go. Otwórz plik — to zwykły Markdown do edycji.

### Krok 2 — Zrób go swoim

Dodaj rzeczy, które inaczej powtarzałbyś za każdym razem. Dobry CLAUDE.md zawiera:

```markdown
# Projekt: <nazwa>

## Czym to jest
Krótki opis projektu i celu.

## Jak uruchomić
- Instalacja: <polecenie>
- Uruchomienie: <polecenie>
- Testy: <polecenie>

## Konwencje
- Zasady języka/stylu do przestrzegania.
- Foldery i co gdzie mieszka.

## Rób / Nie rób
- Rób: małe zmiany z wyjaśnieniem.
- Nie: dotykaj <x> ani nie dodawaj zależności bez pytania.
```

Teraz każda sesja startuje z tym kontekstem — bez tłumaczenia od nowa.

### Krok 3 — Poznaj dwa poziomy pamięci

- **Pamięć projektu:** `CLAUDE.md` w projekcie (współdzielony z każdym, kto ma repo).
- **Pamięć osobista:** CLAUDE.md w Twoim folderze użytkownika Claude Code (`~/.claude/CLAUDE.md`) na *Twoje* globalne preferencje we wszystkich projektach (np. „wyjaśniaj zmiany krótko”, „jestem na Windows”).

Fakty projektu do pliku projektu; nawyki osobiste do pliku użytkownika.

### Krok 4 — Wejdź w tryb planowania

Do nietrywialnego zadania przełącz Claude Code w **tryb planowania** (w CLI przełączaj tryby wejścia — np. **Shift+Tab** — aż pokaże *plan mode*). Potem poproś:

```text
Dodaj walidację danych do formularza rejestracji i pokaż przyjazny komunikat błędu.
Najpierw zaplanuj — nie zmieniaj jeszcze żadnych plików.
```

Claude **bada i proponuje plan** i czeka. Czytasz podejście przed jakąkolwiek edycją.

### Krok 5 — Zatwierdź, potem pozwól wykonać

Jeśli plan wygląda dobrze, zatwierdź i pozwól Claude go zrealizować, przeglądając każdą zmianę. Jeśli nie, doprecyzuj plan słowami najpierw — dużo taniej niż cofanie złych edycji.

### Krok 6 — Zbuduj nawyk

- **Małe/oczywiste zadanie?** Po prostu poproś wprost.
- **Cokolwiek ryzykownego lub wieloetapowego?** Najpierw tryb planowania.
- **Powtarzasz kontekst co sesję?** To należy do CLAUDE.md.

---

## 🧩 Co gdzie trafia

| Fakt | Umieść w |
|------|-----------|
| Jak uruchomić/testować projekt | `CLAUDE.md` projektu |
| Konwencje i strefy zakazane | `CLAUDE.md` projektu |
| „Jestem na Windows, bądź zwięzły” | Osobisty `~/.claude/CLAUDE.md` |
| Ryzykowna/wieloetapowa zmiana | Tryb planowania (najpierw zatwierdź) |
| Jednolinijkowa oczywista poprawka | Po prostu poproś |

---

## ✅ Sprawdzenie

- [ ] Wygenerowałeś `CLAUDE.md` przez `/init` i dodałeś prawdziwy kontekst.
- [ ] Umiesz wyjaśnić pamięć projektu vs osobistą.
- [ ] Użyłeś **trybu planowania**, by dostać propozycję przed edycjami.
- [ ] Zatwierdziłeś plan i pozwoliłeś Claude go wykonać.

---

## 🎯 Zadanie

Napisz prawdziwy CLAUDE.md dla projektu, na którym Ci zależy: czym jest, jak uruchomić, konwencje i strefy zakazane. Potem daj Claude Code naprawdę wieloetapowe zadanie w trybie planowania i zatwierdź dopiero, gdy plan jest dobry.

---

## 💡 Najważniejsze wnioski

- **CLAUDE.md** to auto-ładowana **pamięć projektu** — umieść tam stały kontekst i przestań tłumaczyć (nawyki osobiste do `~/.claude/CLAUDE.md`).
- **Tryb planowania** każe Claude **proponować przed edycją** — przejrzyj podejście, potem zatwierdź.
- Wprost do małych zadań; **najpierw plan** do czegokolwiek ryzykownego lub wieloetapowego.

🌐 [English](../../en/track-g/01-claude-md-and-plan-mode.md) · [← Indeks ścieżki](../README.md) · [Dalej: Komendy ukośnik →](02-komendy-ukosnik.md)
