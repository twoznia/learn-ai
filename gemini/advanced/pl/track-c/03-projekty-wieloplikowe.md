# C3 — Projekty wielo-plikowe z Gemini CLI

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Gemini CLI (podstawowa Lekcja 13)

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Dotąd Twoje skrypty były pojedynczymi plikami. Prawdziwe narzędzia mają **kilka plików**: kod, konfigurację, README. Zarządzanie tym ręcznie jest żmudne — i tu błyszczy **Gemini CLI** (asystent terminalowy z podstawowej Lekcji 13). Tworzy i edytuje **wiele plików naraz**, utrzymuje je spójnie i przechodzi przez plan krok po kroku.

Umiejętność to nie pisanie kodu — to dobre **kierowanie** AI:

1. **Opisz cel i ograniczenia**, nie tylko „zbuduj aplikację”.
2. **Pozwól zaproponować plan** przed pisaniem plików.
3. **Przeglądaj każdą zmianę** przed zatwierdzeniem.
4. **Iteruj** małymi krokami.

---

## 🛠️ Praktyka (9 min)

Zlecimy Gemini CLI zbudowanie małego wielo-plikowego narzędzia: **CLI zamieniające folder notatek w stronę HTML**.

### Krok 1 — Zacznij czysty folder projektu

```powershell
mkdir $HOME\notes-site
cd $HOME\notes-site
gemini
```

### Krok 2 — Opisz cel i poproś najpierw o plan

```text
Chcę mały projekt w Pythonie, który czyta wszystkie pliki .txt w podfolderze "notes"
i buduje jeden index.html wymieniający je, każdy z jednozdaniowym streszczeniem
wygenerowanym przez Gemini.

Zanim napiszesz jakiekolwiek pliki, zaproponuj krótki plan: jakie pliki utworzysz i
co każdy robi. Poczekaj na moją zgodę, zanim cokolwiek utworzysz.
```

Przeczytaj plan. Zatwierdzasz **projekt** zanim powstaną pliki.

### Krok 3 — Zatwierdź i pozwól zbudować

```text
Wygląda dobrze. Utwórz pliki. Zachowaj prostotę i dodaj README.md wyjaśniający, jak to uruchomić.
```

Gemini CLI utworzy kilka plików i pokaże każdy do zatwierdzenia. **Przeczytaj każdy** przed zgodą.

### Krok 4 — Uruchom i iteruj

Postępuj zgodnie z README (prawdopodobnie `python build_site.py`). Jeśli coś nie gra, opisz poprawkę — nie edytuj ręcznie:

```text
Streszczenia są za długie. Zrób każde maks. 12 słów i sortuj notatki od najnowszych.
```
```text
Dodaj prosty blok CSS, aby strona wyglądała czysto, z czytelną czcionką i odstępami.
```

Każda prośba dotyka potrzebnych plików; Gemini CLI utrzymuje je spójnie.

### Krok 5 — Poproś, aby wyjaśnił projekt

```text
Daj mi jednoakapitowy przegląd, jak te pliki do siebie pasują, dla początkującego.
```

Teraz rozumiesz projekt wielo-plikowy, którego nie napisałeś — i możesz go rozwijać.

---

## 🧩 Dobre kierowanie Gemini CLI

| Rób | Zamiast |
|----|------------|
| „Oto cel + ograniczenia; zaproponuj najpierw plan” | „zbuduj mi aplikację” |
| Zatwierdź plan, potem pliki | Ślepe akceptowanie wszystkiego |
| „Popraw X: skróć streszczenia” | Ręczne edytowanie plików |
| Małe iteracje | Jedna gigantyczna prośba |
| „Wyjaśnij, jak to pasuje” | Pozostawienie czarnej skrzynki |

> **Bezpieczeństwo:** Gemini CLI pyta przed tworzeniem/edycją plików lub uruchamianiem komend. W prawdziwym projekcie pracuj w **dedykowanym folderze** (lub gałęzi git).

---

## ✅ Sprawdzenie

- [ ] Gemini CLI zaproponował **plan** przed pisaniem plików.
- [ ] Utworzył projekt wielo-plikowy, który zatwierdziłeś plik po pliku.
- [ ] Iterowałeś prośbami o zmiany prostym językiem.
- [ ] Potrafisz wyjaśnić, jak pliki do siebie pasują.

---

## 🎯 Zadanie

Wybierz małe, przydatne narzędzie (śledzik nawyków, organizator linków, twórca fiszek) i zbuduj je z Gemini CLI, używając przepływu „najpierw plan”. Trzymaj prośby małe, przeglądaj każdą zmianę, zakończ prośbą o README.

---

## 💡 Najważniejsze wnioski

- Gemini CLI zarządza **projektami wielo-plikowymi** — tworząc i edytując wiele plików spójnie.
- Umiejętnością jest **kierowanie**: cel + ograniczenia → plan → zatwierdź → iteruj.
- Przeglądaj każdą zmianę; pracuj w dedykowanym folderze lub gałęzi git.
- Zakończ prośbą o wyjaśnienie projektu.

🌐 [English](../../en/track-c/03-multi-file-projects.md) · [← Wstecz](02-potoki.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
