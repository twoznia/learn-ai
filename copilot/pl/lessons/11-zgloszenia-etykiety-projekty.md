# Lekcja 11 — Zgłoszenia, etykiety i tablice projektów

⏱️ **11 minut** · Poziom: Początkujący (GitHub) · Wymagania: repo GitHub

🌐 [English](../../en/lessons/11-issues-labels-projects.md) · [← Poprzednia](10-galezie-i-pull-requesty.md) · [Strona kursu](../README.md) · [Dalej: Świetne pull requesty →](12-swietne-pull-requesty.md)

---

## 🧠 Teoria (3 min)

GitHub to nie tylko kod — to sposób **śledzenia** pracy. Trzy narzędzia:

- **Zgłoszenia (Issues)** — zadanie do zrobienia lub raport błędu z tytułem, opisem i dyskusją. Każde ma numer (#12), do którego odwołasz się z commitów i PR-ów.
- **Etykiety (Labels)** — tagi jak `bug`, `enhancement`, `good first issue` do kategoryzacji i filtrowania.
- **Projekty** — tablica (jak karteczki w kolumnach: Do zrobienia / W toku / Zrobione) organizująca zgłoszenia i PR-y.

Dlaczego to ważne tutaj: w Lekcji 16 **przypiszesz zgłoszenie agentowi kodującemu Copilota** i otworzy PR, by je rozwiązać. Dobre zgłoszenia to umożliwiają.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Otwórz zgłoszenie

Na repo przejdź do karty **Issues** → **New issue**. Napisz jasne, wykonalne:

```text
Title: Add a --language flag to the CLI

Body:
The app should accept --language en|pl and pass it to get_greeting.
Acceptance:
- `python app.py --language pl` prints a Polish greeting
- Defaults to English when omitted
```

Dobre zgłoszenie mówi **co** i **jak poznasz, że jest gotowe** (akceptacja).

### Krok 2 — Dodaj etykiety

Do zgłoszenia dodaj etykietę jak **enhancement**. Utwórz własne etykiety na stronie **Labels**, jeśli chcesz (np. `copilot-task`).

### Krok 3 — Odwołuj się do zgłoszeń z commitów

Gdy nad nim pracujesz, wspomnij numer, by GitHub je połączył:

```powershell
git commit -m "Add --language flag (part of #1)"
```

Napisanie **„Closes #1"** w opisie PR auto-zamyka zgłoszenie po scaleniu.

### Krok 4 — Zrób prostą tablicę projektu

Przejdź do **Projects** (na profilu lub repo) → **New project** → wybierz szablon **Board**. Dodaj kolumny **Do zrobienia / W toku / Zrobione** i wrzuć zgłoszenie do **Do zrobienia**.

### Krok 5 — Pozwól Copilotowi szkicować zgłoszenia

W Copilot Chat (VS Code lub github.com):

```text
@workspace Read the TODO comments in this project and draft GitHub issues for
them — clear titles and acceptance criteria. I'll create the good ones.
```

### Krok 6 — Pisz zgłoszenia, na których Copilot może działać

Do Lekcji 16 najlepsze zgłoszenia są **konkretne i samodzielne**: jeden jasny wynik, kryteria akceptacji i wskazówki do plików.

---

## 🧩 Klocki śledzenia

| Narzędzie | Cel |
|------|---------|
| **Zgłoszenie** | Śledzone zadanie/błąd z dyskusją (#numer) |
| **Etykieta** | Kategoryzuj i filtruj (bug, enhancement…) |
| **Tablica projektu** | Wizualizuj pracę: Do zrobienia / W toku / Zrobione |
| **„Closes #N"** | Auto-zamyka zgłoszenie, gdy PR się scali |

---

## ✅ Sprawdzian

- [ ] Utworzyłeś/aś jasne zgłoszenie z kryteriami akceptacji.
- [ ] Dodałeś/aś etykietę.
- [ ] Odwołałeś/aś się do numeru zgłoszenia z commita lub PR.
- [ ] Zrobiłeś/aś prostą tablicę projektu (lub naszkicowałeś/aś zgłoszenia z Copilotem).

---

## 🎯 Praca domowa

Napisz dwa dobrze sformułowane zgłoszenia dla projektu — każde z konkretnym wynikiem i kryteriami akceptacji — i dodaj je do tablicy. Trzymaj co najmniej jedno małe i samodzielne; przekażesz je agentowi kodującemu Copilota w Lekcji 16.

---

## 💡 Najważniejsze wnioski

- **Zgłoszenia** śledzą zadania/błędy; **etykiety** kategoryzują; **tablice projektów** wizualizują przepływ.
- Odwołuj się do zgłoszeń przez **#numer**, a **„Closes #N"** auto-zamyka je po scaleniu.
- Jasne, samodzielne zgłoszenia z **kryteriami akceptacji** to, czego agent Copilota potrzebuje, by pomóc.

🌐 [English](../../en/lessons/11-issues-labels-projects.md) · [← Poprzednia](10-galezie-i-pull-requesty.md) · [Strona kursu](../README.md) · [Dalej: Świetne pull requesty →](12-swietne-pull-requesty.md)
