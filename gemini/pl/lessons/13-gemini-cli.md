# Lekcja 13 — Gemini CLI w terminalu

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: Windows, konto Google lub klucz API

🌐 [English](../../en/lessons/13-gemini-cli.md) · [← Wstecz](12-vscode-gemini-code-assist.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)

---

## 🧠 Teoria (3 min)

**Gemini CLI** to darmowy, otwartoźródłowy asystent AI od Google, który działa w **terminalu**. W odróżnieniu od okna czatu potrafi:

- **czytać pliki Twojego projektu**,
- **pisać i edytować kod**,
- **uruchamiać komendy** (za Twoim pozwoleniem),
- samodzielnie przechodzić przez wieloetapowe zadania.

Wyobraź sobie młodszego programistę przy Twojej klawiaturze — opisujesz, czego chcesz, prostym językiem, a on wykonuje pracę, pytając przed czymś ryzykownym. Jest hojny na **darmowym poziomie**, gdy zalogujesz się kontem Google.

Instaluje się go przez **npm**, dostarczany z **Node.js**. Więc najpierw instalujemy Node.js.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj Node.js

W **PowerShell**:

```powershell
winget install --id OpenJS.NodeJS.LTS -e
```

**Zamknij i otwórz ponownie PowerShell**, potem sprawdź:

```powershell
node --version
npm --version
```

Oba powinny wypisać numery wersji (np. `v22.x` i `10.x`). ✅

### Krok 2 — Zainstaluj Gemini CLI

```powershell
npm install -g @google/gemini-cli
```

`-g` oznacza „zainstaluj globalnie”, dzięki czemu uruchomisz go z każdego folderu.

Sprawdź:

```powershell
gemini --version
```

### Krok 3 — Uruchom w projekcie

```powershell
cd $HOME\learn-ai-gemini
gemini
```

Za pierwszym razem przeprowadzi Cię przez **logowanie** — wybierz **logowanie kontem Google** dla darmowego poziomu (lub użyj `GEMINI_API_KEY`). Postępuj zgodnie z komunikatami.

### Krok 4 — Daj mu zadanie

Gdy Gemini CLI działa, po prostu wpisz, czego chcesz:

```text
Spójrz na pliki w tym folderze i powiedz mi, co robi każdy z nich.
```

Potem coś, co zmienia pliki:

```text
Utwórz plik todo.py, który pozwala dodawać zadania do listy i je wypisywać.
```

Pokaże plik, który chce utworzyć, i poprosi o **zatwierdzenie**. Zgódź się, potem uruchom:

```powershell
python todo.py
```

### Krok 5 — Iteruj

```text
Dodaj możliwość oznaczenia zadania jako wykonanego.
```
```text
Zapisz zadania do pliku, aby były pamiętane następnym razem.
```

Edytuje kod za Ciebie. Rdzeń kodowania wspomaganego AI: **opisz → przejrzyj → zatwierdź → uruchom**.

---

## 🔑 Przydatne rzeczy do zapamiętania

| Chcesz… | Zrób to |
|----------|---------|
| Uruchomić Gemini CLI | `gemini` (w folderze projektu) |
| Wyjść | Wpisz `/quit` lub naciśnij dwa razy Ctrl+C |
| Zobaczyć komendy | Wpisz `/help` |
| Cofnąć zmianę | Poproś: „cofnij ostatnią zmianę” |
| Zachować bezpieczeństwo | Zawsze **czytaj** propozycję przed zatwierdzeniem |

> **Złota zasada bezpieczeństwa:** Gemini CLI pyta przed edycją plików lub uruchomieniem komend. Przeczytaj podgląd. Jeśli nie masz pewności, zapytaj *„wyjaśnij, co robi ta komenda i czy jest bezpieczna”*.

---

## ✅ Sprawdzenie

- [ ] `node --version` i `npm --version` działają.
- [ ] `gemini --version` działa.
- [ ] Gemini CLI utworzył plik, który zatwierdziłeś.
- [ ] Poprosiłeś o ulepszenie i zedytował kod.

---

## 🎯 Zadanie

Zapytaj Gemini CLI: *„Dodaj komentarze do todo.py wyjaśniające każdą część dla początkującego, potem podaj mi jednoakapitowe podsumowanie działania programu.”* Przeczytaj podsumowanie — to świetny sposób nauki programowania.

---

## 💡 Najważniejsze wnioski

- Gemini CLI = darmowy asystent kodowania AI w terminalu; instalowany przez `npm install -g @google/gemini-cli`.
- Potrzebuje **Node.js** (zainstaluj najpierw przez winget).
- Uruchom `gemini` w folderze projektu; zaloguj się kontem Google dla darmowego poziomu.
- **Pyta przed** edycją plików lub uruchamianiem komend — zawsze przeglądaj.

🌐 [English](../../en/lessons/13-gemini-cli.md) · [← Wstecz](12-vscode-gemini-code-assist.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)
