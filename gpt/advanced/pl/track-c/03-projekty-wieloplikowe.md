# C3 — Projekty wieloplikowe z Codex CLI

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Codex CLI (podstawowa lekcja 13)

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Dotąd Twoje skrypty były pojedynczymi plikami. Prawdziwe narzędzia mają **kilka plików**: kod, konfigurację, README. Zarządzanie tym ręcznie jest żmudne — tu błyszczy **Codex CLI** (asystent terminala z podstawowej lekcji 13). Tworzy i edytuje **wiele plików naraz**, utrzymuje je spójnymi i realizuje plan krok po kroku.

Umiejętność to nie pisanie kodu — to dobre **kierowanie** AI:

1. **Opisz cel i ograniczenia**, nie tylko „zbuduj aplikację”.
2. **Pozwól zaproponować plan** przed pisaniem plików.
3. **Sprawdzaj każdą zmianę** przed zatwierdzeniem.
4. **Iteruj** małymi krokami.

---

## 🛠️ Praktyka (9 min)

Poprosimy Codex o zbudowanie małego narzędzia wieloplikowego: **CLI zamieniające folder notatek w stronę HTML**.

### Krok 1 — Zacznij czysty folder projektu

```powershell
mkdir $HOME\notes-site
cd $HOME\notes-site
codex
```

### Krok 2 — Opisz cel i najpierw poproś o plan

```text
Chcę mały projekt w Pythonie, który czyta wszystkie pliki .txt w podfolderze "notes"
i buduje jeden index.html z ich listą, każdy z jednozdaniowym streszczeniem
wygenerowanym przez GPT.

Zanim napiszesz jakiekolwiek pliki, zaproponuj krótki plan: jakie pliki utworzysz
i co każdy robi. Poczekaj na moje OK, zanim cokolwiek utworzysz.
```

Przeczytaj plan. Zatwierdzasz **projekt**, zanim powstaną pliki.

### Krok 3 — Zatwierdź i pozwól budować

```text
Wygląda dobrze. Utwórz pliki. Zrób to prosto i dodaj README.md wyjaśniające, jak uruchomić.
```

Codex tworzy kilka plików i pokazuje każdy do zatwierdzenia. **Przeczytaj każdy** przed „tak”.

### Krok 4 — Uruchom i iteruj

Postępuj według napisanego README (pewnie `python build_site.py`). Jeśli coś nie gra, opisz poprawkę — nie edytuj ręcznie:

```text
Streszczenia są za długie. Zrób każde na maks 12 słów i posortuj notatki od najnowszych.
```
```text
Dodaj prosty blok stylów CSS, aby strona wyglądała czysto, z czytelną czcionką i odstępami.
```

Każda prośba dotyka potrzebnych plików; Codex utrzymuje je spójnymi.

### Krok 5 — Poproś o wyjaśnienie projektu

```text
Daj mi jednoakapitowe omówienie, jak te pliki się łączą, dla początkującego.
```

Teraz rozumiesz projekt wieloplikowy, którego nie napisałeś — i możesz go dalej rozwijać.

---

## 🧩 Dobre kierowanie Codeksem

| Rób | Zamiast |
|----|------------|
| „Oto cel + ograniczenia; najpierw zaproponuj plan” | „zbuduj mi aplikację” |
| Zatwierdź plan, potem pliki | Ślepo akceptować wszystko |
| „Popraw X: skróć streszczenia” | Edytować pliki ręcznie |
| Małe iteracje | Jedna gigantyczna prośba |
| „Wyjaśnij, jak to się łączy” | Zostawić czarną skrzynkę |

> **Bezpieczeństwo:** Codex pyta przed tworzeniem/edycją plików lub uruchamianiem poleceń. W prawdziwym projekcie pracuj w **dedykowanym folderze** (lub gałęzi git), by zmiany łatwo sprawdzać i cofać.

---

## ✅ Sprawdzenie

- [ ] Codex zaproponował **plan** przed pisaniem plików.
- [ ] Utworzył projekt wieloplikowy, który zatwierdziłeś plik po pliku.
- [ ] Iterowałeś prośbami o zmiany zwykłym językiem.
- [ ] Umiesz wyjaśnić, jak pliki się łączą.

---

## 🎯 Zadanie

Wybierz małe, przydatne narzędzie (tracker nawyków, organizer linków, kreator fiszek) i zbuduj je z Codeksem, stosując przepływ „najpierw plan”. Trzymaj prośby małe, sprawdzaj każdą zmianę, zakończ prośbą o README.

---

## 💡 Najważniejsze wnioski

- Codex CLI zarządza **projektami wieloplikowymi** — tworzy i edytuje wiele plików spójnie.
- Umiejętność to **kierowanie**: cel + ograniczenia → plan → zatwierdź → iteruj.
- Sprawdzaj każdą zmianę; pracuj w dedykowanym folderze lub gałęzi git.
- Zakończ prośbą o wyjaśnienie projektu, by nie był czarną skrzynką.

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
