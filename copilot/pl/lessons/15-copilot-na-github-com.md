# Lekcja 15 — Copilot na github.com

⏱️ **11 minut** · Poziom: Średni · Wymagania: repo GitHub + Copilot

🌐 [English](../../en/lessons/15-copilot-on-github-com.md) · [← Poprzednia](14-readme-i-dokumentacja.md) · [Strona kursu](../README.md) · [Dalej: Agent kodujący Copilot →](16-agent-kodujacy-copilot.md)

---

## 🧠 Teoria (3 min)

Copilot nie jest tylko w VS Code — jest wbudowany też w **github.com**. Wprost w przeglądarce możesz:

- **Czatować o repozytorium** — pytać, jak działa, gdzie coś jest, jak wykonać zadanie.
- **Podsumować pull requesta** — złapać sedno dużego diffa przed przeglądem.
- **Pytać o zgłoszenia, kod i dokumentację** — bez klonowania czegokolwiek.

To idealne, gdy jesteś **z dala od edytora** — przeglądasz na telefonie czy tablecie, segregujesz na cudzej maszynie lub badasz nieznany projekt, którego nie sklonowałeś/aś.

> Dokładne funkcje Copilota na github.com zależą od planu i są wdrażane z czasem. Szukaj ikony **Copilot** w górnym pasku i na pull requestach.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Otwórz Copilot Chat w przeglądarce

Na github.com kliknij ikonę **Copilot** (górny pasek). Otworzy się czat, który może odwoływać się do kontekstu GitHuba.

### Krok 2 — Zapytaj o repozytorium

Przejdź do repo, potem zapytaj:

```text
What does this repository do, and where is the command-line entry point?
```

Świetne do szybkiej orientacji w **dowolnym** repo.

### Krok 3 — Podsumuj pull requesta

Otwórz PR z nietrywialnym diffem i użyj **podsumowania Copilota** (na PR poszukaj opcji Copilota w polu opisu lub ikony Copilota):

```text
Summarize what this PR changes, the risk areas, and what a reviewer should focus on.
```

Dostajesz briefing przeglądu przed czytaniem każdej linii.

### Krok 4 — Eksploruj kod bez klonowania

Przeglądasz nieznany projekt na GitHubie? Zapytaj Copilota:

```text
Explain how authentication works in this repo and which files are involved.
```

### Krok 5 — Zapytaj o zgłoszenie

Na zgłoszeniu poproś Copilota o zaproponowanie podejścia lub naszkicowanie kryteriów akceptacji — przydatne przy segregacji.

### Krok 6 — Wiedz, kiedy której powierzchni użyć

| Jesteś… | Użyj |
|---------|-----|
| Piszesz/edytujesz kod | **VS Code** Copilot |
| Przeglądasz PR w przeglądarce | **github.com** podsumowanie Copilota |
| Badasz repo, którego nie sklonowałeś/aś | **github.com** czat |
| Na telefonie / cudzym PC | **github.com** Copilot |

---

## 🧩 Powierzchnie Copilota — podsumowanie

| Powierzchnia | Mocne strony |
|---------|-----------|
| **VS Code** | Uzupełnienia, edycje, agent, głęboka praca z kodem |
| **github.com** | Czat o repo, podsumowania PR, segregacja, bez klonowania |
| **Terminal / CLI** | Skryptowalna pomoc (Lekcja 17) |

---

## ✅ Sprawdzian

- [ ] Otworzyłeś/aś Copilot Chat na github.com.
- [ ] Zapytałeś/aś o repozytorium i zorientowałeś/aś się.
- [ ] Podsumowałeś/aś pull requesta w przeglądarce.
- [ ] Umiesz wybrać właściwą powierzchnię Copilota do sytuacji.

---

## 🎯 Praca domowa

Znajdź publiczne repo open-source, którego nie znasz. Na github.com użyj Copilota, by wyjaśnić, co robi, gdzie jest punkt wejścia i jak go uruchomić — bez klonowania. Potem podsumuj jeden z jego niedawno scalonych PR-ów.

---

## 💡 Najważniejsze wnioski

- Copilot żyje na **github.com**: czat o repo, **podsumowania PR** i eksploracja zgłoszeń/kodu.
- Idealny, gdy jesteś **z dala od edytora** lub badasz repo, którego nie sklonowałeś/aś.
- Dopasuj **powierzchnię do zadania** — VS Code do budowania, github.com do przeglądu i eksploracji.

🌐 [English](../../en/lessons/15-copilot-on-github-com.md) · [← Poprzednia](14-readme-i-dokumentacja.md) · [Strona kursu](../README.md) · [Dalej: Agent kodujący Copilot →](16-agent-kodujacy-copilot.md)
