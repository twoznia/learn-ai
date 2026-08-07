# Lekcja 09 — Podstawy Git i GitHub (z Copilotem jako korepetytorem)

⏱️ **13 minut** · Poziom: Początkujący (GitHub) · Wymagania: Windows, konto GitHub

🌐 [English](../../en/lessons/09-git-and-github-fundamentals.md) · [← Poprzednia](08-kontekst-uczestnicy-referencje.md) · [Strona kursu](../README.md) · [Dalej: Gałęzie i pull requesty →](10-galezie-i-pull-requesty.md)

---

## 🧠 Teoria (4 min)

By wycisnąć maksimum z funkcji PR i przeglądu Copilota, potrzebujesz podstaw **Git** i **GitHub**.

- **Git** — narzędzie śledzące zmiany w plikach w czasie. **Commit** to zapisana migawka; **historia** to ślad commitów.
- **GitHub** — strona hostująca repozytoria Git online, byś mógł/mogła robić kopie zapasowe, dzielić się i współpracować.

Codzienna pętla: **zmień pliki → commit (migawka) → push (wyślij na GitHub)**. Na razie tyle. A gdy polecenie Gita Cię zmyli, **zapytaj Copilota** — to cierpliwy korepetytor.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zainstaluj Git

```powershell
winget install --id Git.Git -e
```

Zamknij i otwórz ponownie terminal, potem sprawdź:

```powershell
git --version
```

### Krok 2 — Powiedz Gitowi, kim jesteś

```powershell
git config --global user.name "Twoje Imię"
git config --global user.email "ty@example.com"
```

### Krok 3 — Zamień projekt w repo

W folderze `copilot-course` (terminal VS Code, **Ctrl+`**):

```powershell
git init
git add -A
git commit -m "First commit: my Copilot course project"
```

Właśnie zapisałeś/aś pierwszą migawkę.

### Krok 4 — Utwórz repo na GitHubie i zpushuj

Najłatwiej: widok **Source Control** VS Code (**Ctrl+Shift+G**) ma przycisk **Publish to GitHub** — kliknij, wybierz prywatne lub publiczne, a utworzy repo GitHub i zpushuje za Ciebie.

> Wolisz przeglądarkę? Utwórz puste repo na **github.com/new**, potem wykonaj polecenia „push an existing repository", które pokazuje.

### Krok 5 — Ucz się Gita z Copilotem

Utknąłeś/aś na jakiejś idei Gita? Zapytaj **@terminal**:

```text
@terminal I changed 3 files. Show me the exact commands to commit them with a
good message and push to GitHub, and explain each step.
```

### Krok 6 — Zobacz swoją historię

```powershell
git log --oneline
```

Każdy commit to punkt, do którego możesz wrócić — Twoja siatka bezpieczeństwa na wszystko, co Copilot zrobi dalej.

---

## 🗺️ Codzienny Git (do zakładek)

| Zrób | Polecenie |
|----|---------|
| Zobacz, co się zmieniło | `git status` |
| Dodaj wszystkie zmiany | `git add -A` |
| Zapisz migawkę | `git commit -m "wiadomość"` |
| Wyślij na GitHub | `git push` |
| Pobierz najnowsze z GitHuba | `git pull` |
| Zobacz historię | `git log --oneline` |

> **Wskazówka:** panel Source Control VS Code robi to wszystko przyciskami — a Copilot może napisać Twoje komunikaty commitów (Lekcja 12).

---

## ✅ Sprawdzian

- [ ] Git jest zainstalowany i zna Twoje imię/e-mail.
- [ ] Twój projekt to repo Git z co najmniej jednym commitem.
- [ ] Opublikowałeś/aś go na GitHubie (widać go na koncie).
- [ ] Poprosiłeś/aś Copilota o wyjaśnienie polecenia Gita.

---

## 🎯 Praca domowa

Zrób małą zmianę w pliku, potem zacommituj i zpushuj — używając terminala lub przycisków Source Control VS Code. Odśwież repo na github.com i potwierdź, że zmiana się pojawia. Poproś Copilota o wyjaśnienie czegokolwiek niejasnego.

---

## 💡 Najważniejsze wnioski

- **Git** robi migawki pracy (commity); **GitHub** hostuje je online.
- Pętla to **zmień → commit → push**; `git pull` pobiera zmiany innych.
- Panel **Source Control** VS Code robi to przyciskami, a **Copilot to świetny korepetytor Gita** — po prostu zapytaj.

🌐 [English](../../en/lessons/09-git-and-github-fundamentals.md) · [← Poprzednia](08-kontekst-uczestnicy-referencje.md) · [Strona kursu](../README.md) · [Dalej: Gałęzie i pull requesty →](10-galezie-i-pull-requesty.md)
