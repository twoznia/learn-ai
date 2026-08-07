# Lekcja 02 — Konfiguracja VS Code + Copilot (pierwsze uzupełnienia)

⏱️ **12 minut** · Poziom: Początkujący · Wymagania: Windows, konto GitHub (Lekcja 1)

🌐 [English](../../en/lessons/02-setup-vscode-and-copilot.md) · [← Poprzednia](01-czym-jest-github-copilot.md) · [Strona kursu](../README.md) · [Dalej: Podstawy Copilot Chat →](03-podstawy-copilot-chat.md)

---

## 🧠 Teoria (3 min)

**VS Code** (Visual Studio Code) to darmowy, ogromnie popularny edytor kodu Microsoftu — i najlepsze miejsce do używania Copilota. Zainstalujemy VS Code, dodamy rozszerzenia Copilota, zalogujemy się i zobaczymy, jak Copilot podpowiada kod jako szary **„ghost text"** (tekst-widmo), który akceptujesz jednym klawiszem.

Dwa rozszerzenia współpracują:
- **GitHub Copilot** — uzupełnienia kodu w linii.
- **GitHub Copilot Chat** — panel czatu i czat w linii (następna lekcja).

Instalacja jednego zwykle proponuje drugie; weź oba.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Zainstaluj VS Code

W **PowerShell**:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

Lub pobierz z **https://code.visualstudio.com** → **Download for Windows** → uruchom instalator (zaznacz **„Add to PATH"**).

### Krok 2 — Utwórz folder ćwiczeniowy i otwórz go

```powershell
mkdir $HOME\copilot-course
```

W VS Code: **File → Open Folder…** → wybierz `C:\Users\TwojaNazwa\copilot-course`.

### Krok 3 — Zainstaluj rozszerzenia Copilota

1. Kliknij ikonę **Extensions** (**Ctrl+Shift+X**).
2. Wyszukaj **GitHub Copilot** i zainstaluj (wydawca **GitHub**).
3. Zainstaluj też **GitHub Copilot Chat**, jeśli nie dodano automatycznie.

### Krok 4 — Zaloguj się

Gdy zostaniesz poproszony/a (lub przez ikonę **Copilot** / menu konta, lewy dół), **zaloguj się do GitHuba** i autoryzuj Copilota. Okno przeglądarki to potwierdzi. Gdy ikona statusu Copilota pokaże, że jest aktywny, jesteś gotowy/a.

### Krok 5 — Twoje pierwsze uzupełnienie

1. Utwórz nowy plik: **File → New File** → zapisz jako `demo.py`.
2. Wpisz to i **poczekaj**:

```python
# A function that returns the first n Fibonacci numbers
def fibonacci(n):
```

3. Copilot pokazuje szary **ghost text** proponujący ciało funkcji.
4. Naciśnij **Tab**, by zaakceptować, lub **Esc**, by odrzucić.

Właśnie napisałeś/aś kod z AI. 🎉

### Krok 6 — Steruj podpowiedziami

- Napisz **komentarz** opisujący, czego chcesz, potem zacznij linię — Copilot go użyje.
- Zobacz alternatywy: najedź na podpowiedź lub użyj **Alt+]** / **Alt+[**, by przełączać (skróty mogą się różnić).
- Akceptuj **słowo po słowie** przez **Ctrl+→**, jeśli chcesz tylko część.

---

## 🗺️ Skróty uzupełnień Copilota (do zakładek)

| Akcja | Skrót |
|--------|-------|
| Zaakceptuj podpowiedź | Tab |
| Odrzuć | Esc |
| Następna / poprzednia podpowiedź | Alt+] / Alt+[ |
| Zaakceptuj jedno słowo | Ctrl+→ |
| Uruchom czat w linii | Ctrl+I |

> Skróty mogą się różnić zależnie od wersji/układu — sprawdź **File → Preferences → Keyboard Shortcuts** i wyszukaj „Copilot".

---

## ✅ Sprawdzian

- [ ] VS Code jest zainstalowany i otworzył folder `copilot-course`.
- [ ] Rozszerzenia GitHub Copilot (i Chat) są zainstalowane.
- [ ] Zalogowałeś/aś się i Copilot jest aktywny.
- [ ] Zaakceptowałeś/aś co najmniej jedno uzupełnienie ghost-text.

---

## 🎯 Praca domowa

W `demo.py` napisz komentarz `# A function that checks if a word is a palindrome` i pozwól Copilotowi go napisać. Zaakceptuj, potem napisz drugi komentarz proszący o test i zaakceptuj też. Zauważ, jak jasny komentarz daje lepszy kod.

---

## 💡 Najważniejsze wnioski

- Zainstaluj **VS Code** + rozszerzenia **GitHub Copilot** i **Copilot Chat**, potem zaloguj się.
- Copilot podpowiada szary **ghost text**; **Tab** akceptuje, **Esc** odrzuca.
- Krótki **komentarz opisujący intencję** dramatycznie poprawia podpowiedź.

🌐 [English](../../en/lessons/02-setup-vscode-and-copilot.md) · [← Poprzednia](01-czym-jest-github-copilot.md) · [Strona kursu](../README.md) · [Dalej: Podstawy Copilot Chat →](03-podstawy-copilot-chat.md)
