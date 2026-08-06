# C3 — Projekty wielo-plikowe z Claude Code

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Claude Code (podstawowa Lekcja 13)

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Dotąd Twoje skrypty były pojedynczymi plikami. Prawdziwe narzędzia mają **kilka plików**: kod, konfigurację, README, może testy. Zarządzanie tym ręcznie jest żmudne — i tu właśnie błyszczy **Claude Code** (asystent terminalowy z podstawowej Lekcji 13). Potrafi tworzyć i edytować **wiele plików naraz**, utrzymywać je spójnie i przechodzić przez plan krok po kroku.

Umiejętność tutaj to nie pisanie kodu — to dobre **kierowanie** AI:

1. **Opisz cel i ograniczenia**, nie tylko „zbuduj aplikację”.
2. **Pozwól zaproponować plan** przed pisaniem plików.
3. **Przeglądaj każdą zmianę** przed zatwierdzeniem.
4. **Iteruj** małymi krokami.

---

## 🛠️ Praktyka (9 min)

Zlecimy Claude Code zbudowanie małego wielo-plikowego narzędzia: **CLI, które zamienia folder notatek w stronę HTML**.

### Krok 1 — Zacznij czysty folder projektu

```powershell
mkdir $HOME\notes-site
cd $HOME\notes-site
claude
```

### Krok 2 — Opisz cel i poproś najpierw o plan

W Claude Code wklej to — zauważ, że prosimy o **plan przed kodem**:

```text
Chcę mały projekt w Pythonie, który czyta wszystkie pliki .txt w podfolderze "notes"
i buduje jeden index.html wymieniający je, każdy z jednozdaniowym streszczeniem
wygenerowanym przez Claude.

Zanim napiszesz jakiekolwiek pliki, zaproponuj krótki plan: jakie pliki utworzysz i
co każdy robi. Poczekaj na moją zgodę, zanim cokolwiek utworzysz.
```

Przeczytaj jego plan. To kluczowy nawyk — zatwierdzasz **projekt** zanim powstaną pliki.

### Krok 3 — Zatwierdź i pozwól zbudować pliki

Odpowiedz:

```text
Wygląda dobrze. Utwórz pliki. Zachowaj prostotę i dodaj README.md wyjaśniający, jak to uruchomić.
```

Claude Code utworzy kilka plików (np. `build_site.py`, `README.md`, może przykładowy plik `notes/`). Pokazuje każdy i prosi o zatwierdzenie. **Przeczytaj każdy** przed zgodą.

### Krok 4 — Uruchom i iteruj

Postępuj zgodnie z README, które napisał (prawdopodobnie coś jak):

```powershell
python build_site.py
```

Jeśli coś nie gra, opisz poprawkę — nie edytuj ręcznie:

```text
Streszczenia są za długie. Zrób każde maks. 12 słów i sortuj notatki od najnowszych.
```
```text
Dodaj prosty blok CSS, aby strona wyglądała czysto, z czytelną czcionką i odstępami.
```

Każda prośba dotyka potrzebnych plików; Claude Code utrzymuje je spójnie.

### Krok 5 — Poproś, aby wyjaśnił projekt

```text
Daj mi jednoakapitowy przegląd, jak te pliki do siebie pasują, dla początkującego.
```

Teraz rozumiesz projekt wielo-plikowy, którego nie napisałeś — i możesz go dalej rozwijać.

---

## 🧩 Dobre kierowanie Claude Code

| Rób | Zamiast |
|----|------------|
| „Oto cel + ograniczenia; zaproponuj najpierw plan” | „zbuduj mi aplikację” |
| Zatwierdź plan, potem pliki | Ślepe akceptowanie wszystkiego |
| „Popraw X: skróć streszczenia” | Ręczne edytowanie plików |
| Małe iteracje | Jedna gigantyczna prośba |
| „Wyjaśnij, jak to pasuje” | Pozostawienie czarnej skrzynki |

> **Bezpieczeństwo:** Claude Code pyta przed tworzeniem/edycją plików lub uruchamianiem komend. W prawdziwym projekcie pracuj w **dedykowanym folderze** (lub gałęzi git), aby zmiany były łatwe do przeglądu i cofnięcia.

---

## ✅ Sprawdzenie

- [ ] Claude Code zaproponował **plan** przed pisaniem plików.
- [ ] Utworzył projekt wielo-plikowy, który zatwierdziłeś plik po pliku.
- [ ] Iterowałeś prośbami o zmiany prostym językiem.
- [ ] Potrafisz wyjaśnić, jak pliki do siebie pasują.

---

## 🎯 Zadanie

Wybierz małe, przydatne narzędzie (śledzik nawyków, organizator linków, twórca fiszek) i zbuduj je z Claude Code, używając przepływu „najpierw plan”. Trzymaj prośby małe, przeglądaj każdą zmianę i zakończ prośbą o README.

---

## 💡 Najważniejsze wnioski

- Claude Code zarządza **projektami wielo-plikowymi** — tworząc i edytując wiele plików spójnie.
- Umiejętnością jest **kierowanie**: cel + ograniczenia → plan → zatwierdź → iteruj.
- Przeglądaj każdą zmianę; pracuj w dedykowanym folderze lub gałęzi git.
- Zakończ prośbą o wyjaśnienie projektu, aby nie był czarną skrzynką.

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
