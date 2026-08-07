# Lekcja 17 — Copilot w terminalu + GitHub Actions

⏱️ **13 minut** · Poziom: Zaawansowany · Wymagania: repo GitHub, Node.js lub GitHub CLI

🌐 [English](../../en/lessons/17-copilot-cli-and-actions.md) · [← Poprzednia](16-agent-kodujacy-copilot.md) · [Strona kursu](../README.md) · [Dalej: Koszty, limity i kolejne kroki →](18-koszty-limity-i-kolejne-kroki.md)

---

## 🧠 Teoria (4 min)

Dwa potężne narzędzia spinają wszystko:

- **Copilot w terminalu (Copilot CLI)** — proś o polecenia powłoki i pomoc z kodem wprost w terminalu oraz skryptuj to do automatyzacji. Świetne do „jakie jest polecenie do…?" i zadań bezobsługowych.
- **GitHub Actions** — automatyzacja GitHuba uruchamiana na zdarzeniach (jak otwarcie PR). Klasyczne zastosowanie to **CI (Continuous Integration)**: automatyczne uruchamianie testów na każdym PR, by zepsuty kod nie mógł scalić się niezauważony. Przegląd Copilota może dołożyć się na wierzchu, a **Copilot Autofix** może nawet zaproponować poprawki znalezionych problemów bezpieczeństwa.

Razem: testy uruchamiają się automatycznie, Copilot przegląda, a Ty scalasz z pewnością.

> Nazwy narzędzi, polecenia instalacji i dostępność Autofix zmieniają się z czasem. Sprawdź bieżącą dokumentację GitHuba dla Copilot CLI i GitHub Actions; *koncepcje* — skryptowalny Copilot + automatyczne kontrole — są stabilne.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zdobądź Copilot CLI

Częsta droga to **GitHub CLI** z rozszerzeniem Copilota:

```powershell
winget install --id GitHub.cli -e
gh auth login
gh extension install github/gh-copilot
```

(Lub zainstaluj samodzielny Copilot CLI zgodnie z bieżącą dokumentacją.)

### Krok 2 — Poproś o polecenie

```powershell
gh copilot suggest "find the 5 largest files in this folder tree on Windows"
```

Proponuje polecenie i je wyjaśnia. Zapytaj przed uruchomieniem czegoś, czego nie rozumiesz.

### Krok 3 — Wyjaśnij straszne polecenie

```powershell
gh copilot explain "git reset --hard origin/main"
```

Idealne do zrozumienia polecenia przed uruchomieniem.

### Krok 4 — Dodaj CI: uruchamiaj testy na każdym PR

Utwórz `.github/workflows/ci.yml`. Pozwól Copilotowi je naszkicować:

```text
@workspace Create a GitHub Actions workflow that runs on pull requests: set up
Python, install pytest, and run the tests. Keep it minimal.
```

Minimalny przykład:

```yaml
name: CI
on: [pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.x"
      - run: pip install pytest
      - run: pytest
```

Zacommituj na gałęzi i otwórz PR — obserwuj, jak uruchamiają się **Checks**.

### Krok 5 — Przeczytaj wyniki kontroli

Na PR karta **Checks** pokazuje sukces/porażkę. Jeśli testy zawiodą, PR to sygnalizuje — a Ty możesz poprosić Copilota o naprawę.

### Krok 6 — Poznaj Copilot Autofix (bezpieczeństwo)

Jeśli repo ma włączone skanowanie kodu, **Copilot Autofix** może proponować poprawki alertów bezpieczeństwa na PR-ach. Przejrzyj proponowaną poprawkę jak każdą inną — potem zastosuj, jeśli poprawna.

---

## 🧩 Stos automatyzacji

| Warstwa | Co robi |
|-------|--------------|
| **Copilot CLI** | Podpowiedzi poleceń + skryptowalna pomoc |
| **GitHub Actions (CI)** | Uruchamia Twoje testy na każdym PR automatycznie |
| **Przegląd Copilota** | Komentarze przeglądu AI na PR |
| **Copilot Autofix** | Proponuje poprawki alertów bezpieczeństwa |
| **Ty** | Zatwierdzasz scalenie |

> ⚠️ CI uruchamia kod z PR-ów — uważaj z włączaniem go na niezaufanych wkładach. I zawsze przeglądaj sugestie Autofix; proponowana poprawka wciąż może być błędna.

---

## ✅ Sprawdzian

- [ ] Użyłeś/aś Copilot CLI, by zaproponować i wyjaśnić polecenie.
- [ ] Dodałeś/aś workflow GitHub Actions uruchamiający testy na PR-ach.
- [ ] Otworzyłeś/aś PR i obserwowałeś/aś uruchomienie kontroli.
- [ ] Wiesz, gdzie przegląd Copilota i Autofix pasują w stosie.

---

## 🎯 Praca domowa

Dodaj workflow CI do repo, potem otwórz PR celowo psujący test. Potwierdź, że CI to łapie (czerwona kontrola), napraw z Copilotem i obserwuj, jak kontrola robi się zielona. Masz teraz automatyczne testy strzegące `main`.

---

## 💡 Najważniejsze wnioski

- **Copilot CLI** proponuje i wyjaśnia polecenia powłoki i można go skryptować.
- **GitHub Actions (CI)** uruchamia Twoje **testy automatycznie na każdym PR** — zepsuty kod zostaje oznaczony.
- **Przegląd Copilota + Autofix** dokładają kontrole AI na wierzchu; Ty wciąż **zatwierdzasz scalenie**.

🌐 [English](../../en/lessons/17-copilot-cli-and-actions.md) · [← Poprzednia](16-agent-kodujacy-copilot.md) · [Strona kursu](../README.md) · [Dalej: Koszty, limity i kolejne kroki →](18-koszty-limity-i-kolejne-kroki.md)
