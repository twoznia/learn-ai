# Lekcja 10 — Gałęzie i przepływ pull requestów

⏱️ **13 minut** · Poziom: Początkujący → Średni (GitHub) · Wymagania: repo GitHub (Lekcja 9)

🌐 [English](../../en/lessons/10-branches-and-pull-requests.md) · [← Poprzednia](09-podstawy-git-i-github.md) · [Strona kursu](../README.md) · [Dalej: Zgłoszenia, etykiety i projekty →](11-zgloszenia-etykiety-projekty.md)

---

## 🧠 Teoria (4 min)

**Pull request (PR)** to serce pracy na GitHubie — i tam błyszczą funkcje przeglądu i podsumowań Copilota (kolejne lekcje). Najpierw przepływ.

- **Gałąź** to równoległa kopia kodu, gdzie robisz zmiany bezpiecznie, bez ruszania `main`.
- Commitujesz pracę na gałęzi, **pushujesz** ją, potem otwierasz **pull request** — propozycję scalenia gałęzi do `main`.
- PR to miejsce **przeglądu** zmian (zobacz diff, komentuj, uruchom kontrole) przed scaleniem.

Pętla: **gałąź → commit → push → otwórz PR → przegląd → scal.** Nawet solo utrzymuje to `main` w czystości i daje krok przeglądu.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Utwórz gałąź

W repo (terminal VS Code):

```powershell
git switch -c add-farewell
```

Jesteś teraz na gałęzi `add-farewell`; `main` nietknięty.

### Krok 2 — Zrób zmianę z Copilotem

Poproś Copilota o dodanie małej funkcji, np. `get_farewell(name)`. Zaakceptuj.

### Krok 3 — Zacommituj i zpushuj gałąź

```powershell
git add -A
git commit -m "Add get_farewell function"
git push -u origin add-farewell
```

### Krok 4 — Otwórz pull request

GitHub drukuje link po pushu, lub wejdź na repo na github.com — pokazuje **„Compare & pull request"**. Kliknij. Zobaczysz:
- Pola **tytułu** i **opisu**.
- **Diff** (zmienione pliki).

Nadaj jasny tytuł i otwórz PR.

> W VS Code rozszerzenie **GitHub Pull Requests** pozwala tworzyć i przeglądać PR-y bez opuszczania edytora. Zainstaluj je, jeśli chcesz — to ten sam przepływ.

### Krok 5 — Przejrzyj własny PR

Na karcie **Files changed** PR-a przeczytaj diff, jakbyś recenzował/a kogoś innego. Ten nawyk łapie błędy, zanim wylądują.

### Krok 6 — Scal go

Gdy jesteś zadowolony/a, kliknij **Merge pull request** → **Confirm**. Potem lokalnie:

```powershell
git switch main
git pull
```

Twoja zmiana jest teraz w `main`, a historia pozostaje schludna.

---

## 🧩 Przepływ PR

| Krok | Polecenie / akcja |
|------|------------------|
| Nowa gałąź | `git switch -c moja-funkcja` |
| Zacommituj pracę | `git commit -m "..."` |
| Zpushuj gałąź | `git push -u origin moja-funkcja` |
| Otwórz PR | „Compare & pull request" na GitHubie |
| Przegląd | Przeczytaj diff **Files changed** |
| Scal | **Merge pull request** → Confirm |

> Nazwy gałęzi powinny opisywać zmianę (`fix-login-bug`, `add-dark-mode`) — Copilot podpowie jedną, jeśli poprosisz.

---

## ✅ Sprawdzian

- [ ] Utworzyłeś/aś gałąź i zrobiłeś/aś na niej zmianę.
- [ ] Zpushowałeś/aś gałąź i otworzyłeś/aś pull request.
- [ ] Przejrzałeś/aś diff na karcie Files changed.
- [ ] Scaliłeś/aś PR i pobrałeś/aś `main` lokalnie.

---

## 🎯 Praca domowa

Zrób drugą pełną pętlę: gałąź, zmiana wspierana Copilotem, push, otwórz PR z jasnym tytułem, przejrzyj diff i scal. Przepływ powinien zaczynać być rutyną — bo kolejne lekcje na nim budują.

---

## 💡 Najważniejsze wnioski

- Pracuj na **gałęzi**, potem otwórz **pull request**, by scalić do `main`.
- PR to **powierzchnia przeglądu** — zawsze czytaj diff **Files changed** przed scaleniem.
- Pętla to **gałąź → commit → push → PR → przegląd → scal**, i to fundament funkcji PR Copilota.

🌐 [English](../../en/lessons/10-branches-and-pull-requests.md) · [← Poprzednia](09-podstawy-git-i-github.md) · [Strona kursu](../README.md) · [Dalej: Zgłoszenia, etykiety i projekty →](11-zgloszenia-etykiety-projekty.md)
