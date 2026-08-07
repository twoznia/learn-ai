# G4 — Checkpointy i bezpieczna edycja

⏱️ **15 minut** · Ścieżka: 🅶 Gemini CLI w głąb · Potrzebne: Gemini CLI zainstalowany i zalogowany; git pomaga

🌐 [English](../../en/track-g/04-checkpointing-and-undo.md) · [← Wstecz](03-narzedzia-i-zatwierdzenia.md) · [Indeks ścieżki](../README.md) · [Dalej: Skryptowanie CLI →](05-skryptowanie-cli.md)

---

## 🧠 Teoria (5 min)

Agenci edytują prawdziwe pliki, więc pewność, by pozwolić im pracować, bierze się z możliwości **cofnięcia**. Gemini CLI wspiera **checkpointy** — potrafi zrobić migawkę projektu **przed** wprowadzeniem zmian, byś mógł **przywrócić** ten punkt, jeśli edycja pójdzie źle.

Dwie siatki bezpieczeństwa, używane razem:

- **Checkpointy** — własna migawka-i-przywracanie CLI (przez komendę `/restore`). Świetne do cofnięcia konkretnej akcji narzędzia.
- **Git** — Twoja kontrola wersji. Czysta gałąź + małe commity oznaczają, że zawsze możesz zrobić diff i cofnąć.

Z nimi pozwolenie CLI na edycję jest niskiego ryzyka: błędy są odwracalne, nie straszne.

> Checkpointy mogą wymagać włączenia w ustawieniach, a szczegóły ewoluują. Jeśli `/restore` jest niedostępne, **git jest Twoim pewnym cofnięciem** — ta lekcja opiera się na obu.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zacznij od czystego stanu git

Praca tam, gdzie git jest ustawiony, czyni wszystko odwracalnym:

```powershell
git status
```

Zacommituj lub zaschowaj cokolwiek oczekującego, byś miał czystą bazę. (Brak gita? `git init` w folderze roboczym do ćwiczeń.)

### Krok 2 — Pozwól CLI zrobić zmianę

Poproś o edycję i zatwierdź ją:

```text
Dodaj sekcję „## Notatki” do README z dwoma przykładowymi punktami.
```

### Krok 3 — Przywróć checkpointem

Jeśli checkpointy są włączone, możesz cofnąć ostatnią akcję narzędzia:

```text
/restore
```

CLI wypisuje punkty przywracania (migawki sprzed edycji) i przywraca projekt. To Twoje natychmiastowe „cofnij to”.

### Krok 4 — Cofnij gitem

Git to niezawodna siatka. By zobaczyć i cofnąć:

```powershell
git diff            # co się zmieniło
git restore .       # odrzuć niezastagowane zmiany
```

Albo, jeśli zacommitowałeś i chcesz wrócić krok, użyj normalnego przepływu git. Sedno: **nic, co CLI robi, nie jest trwałe**, gdy pracujesz w git.

### Krok 5 — Zbuduj nawyk bezpiecznej edycji

- **Nowe zadanie / ryzykowna edycja?** Zacznij od czystego stanu git, by diff był sensowny.
- **Małe commity** po drodze — każdy to punkt przywracania.
- **Przejrzyj diff** po edycji CLI, zanim zaakceptujesz do swojej pracy.

### Krok 6 — Połącz z przepływem zatwierdzania (G3)

Zatwierdzenia zatrzymują złe akcje *zanim* się zdarzą; checkpointy/git cofają je *po*. Razem czynią edycję agenta naprawdę bezpieczną: bramkujesz zmiany i możesz odwrócić każdą, która się prześlizgnie.

---

## 🧩 Twoje dwie siatki cofania

| Siatka | Użyj, by |
|-----|-----------|
| **Checkpointy (`/restore`)** | Szybko cofnąć konkretną akcję narzędzia |
| **Git (`diff`, `restore`, commity)** | Niezawodnie przejrzeć i cofnąć, zawsze |
| **Oba** | Pewna, niskiego ryzyka edycja agenta |

> ⚠️ **Odwracalność to bezpieczeństwo.** Pracuj w git, trzymaj commity małe i przeglądaj diffy. Jeśli kiedyś pozwolisz CLI działać w szybszym trybie auto-zatwierdzania, rób to **tylko** w czystej gałęzi git, by każda zmiana była odzyskiwalna.

---

## ✅ Sprawdzenie

- [ ] Zacząłeś od czystego stanu git przed pozwoleniem CLI na edycję.
- [ ] Przywróciłeś zmianę przez `/restore` (lub cofnąłeś gitem).
- [ ] Przejrzałeś diff po edycji przed akceptacją.
- [ ] Umiesz wyjaśnić, jak zatwierdzenia + cofanie czynią edycję bezpieczną.

---

## 🎯 Zadanie

W folderze roboczym śledzonym gitem pozwól CLI zrobić kilka edycji, potem poćwicz obie drogi cofania: `/restore` i `git restore`. Nabierz wprawy w przeglądaniu diffa po każdej zmianie, by akceptacja lub cofnięcie było szybką, pewną decyzją.

---

## 💡 Najważniejsze wnioski

- **Checkpointy** (`/restore`) robią migawkę projektu przed edycjami, byś mógł cofnąć akcję narzędzia.
- **Git** (czysta gałąź, małe commity, diffy) to Twoje niezawodne, zawsze dostępne cofnięcie.
- Zatwierdzenia zatrzymują złe akcje z góry; **cofanie** odwraca cokolwiek po — razem czynią edycję agenta bezpieczną.

🌐 [English](../../en/track-g/04-checkpointing-and-undo.md) · [← Wstecz](03-narzedzia-i-zatwierdzenia.md) · [Indeks ścieżki](../README.md) · [Dalej: Skryptowanie CLI →](05-skryptowanie-cli.md)
