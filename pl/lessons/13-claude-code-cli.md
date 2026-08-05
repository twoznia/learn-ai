# Lekcja 13 — Claude Code CLI w terminalu

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: Windows, konto lub klucz API

🌐 [English](../../en/lessons/13-claude-code-cli.md) · [← Wstecz](12-vscode.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)

---

## 🧠 Teoria (3 min)

**Claude Code** to asystent kodowania AI od Anthropic, który działa w **terminalu**. W odróżnieniu od okna czatu potrafi:

- **czytać pliki Twojego projektu**,
- **pisać i edytować kod**,
- **uruchamiać komendy** (za Twoim pozwoleniem),
- samodzielnie przechodzić przez wieloetapowe zadania.

Wyobraź sobie młodszego programistę siedzącego przy Twojej klawiaturze — opisujesz, czego chcesz, prostym językiem, a on wykonuje pracę, pytając przed czymś ryzykownym.

Instaluje się go przez **npm**, menedżer pakietów dostarczany z **Node.js**. Więc najpierw instalujemy Node.js.

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

### Krok 2 — Zainstaluj Claude Code

```powershell
npm install -g @anthropic-ai/claude-code
```

`-g` oznacza „zainstaluj globalnie”, dzięki czemu uruchomisz go z każdego folderu. Zajmuje minutę.

Sprawdź:

```powershell
claude --version
```

### Krok 3 — Uruchom w projekcie

```powershell
cd $HOME\learn-ai-claude
claude
```

Za pierwszym razem przeprowadzi Cię przez **logowanie** (konto Claude lub klucz API). Postępuj zgodnie z komunikatami.

### Krok 4 — Daj mu zadanie

Gdy Claude Code działa, po prostu wpisz, czego chcesz. Wypróbuj:

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

Poproś o ulepszenia prostym językiem:

```text
Dodaj możliwość oznaczenia zadania jako wykonanego.
```

```text
Zapisz zadania do pliku, aby były pamiętane następnym razem.
```

Edytuje kod za Ciebie. To rdzeń kodowania wspomaganego AI: **opisz → przejrzyj → zatwierdź → uruchom**.

---

## 🔑 Przydatne rzeczy do zapamiętania

| Chcesz… | Zrób to |
|----------|---------|
| Uruchomić Claude Code | `claude` (w folderze projektu) |
| Wyjść | Wpisz `/exit` lub naciśnij dwa razy Ctrl+C |
| Zobaczyć komendy | Wpisz `/help` |
| Cofnąć zmianę | Poproś: „cofnij ostatnią zmianę” |
| Zachować bezpieczeństwo | Zawsze **czytaj** propozycję przed zatwierdzeniem |

> **Złota zasada bezpieczeństwa:** Claude Code pyta przed edycją plików lub uruchomieniem komend. Przeczytaj podgląd. Jeśli nie rozumiesz kroku, zapytaj *„wyjaśnij, co robi ta komenda i czy jest bezpieczna”*.

---

## ✅ Sprawdzenie

- [ ] `node --version` i `npm --version` działają.
- [ ] `claude --version` działa.
- [ ] Claude Code utworzył plik, który zatwierdziłeś.
- [ ] Poprosiłeś o ulepszenie i zedytował kod.

---

## 🎯 Zadanie

Zapytaj Claude Code: *„Dodaj komentarze do todo.py wyjaśniające każdą część dla początkującego, potem podaj mi jednoakapitowe podsumowanie działania programu.”* Przeczytaj podsumowanie — to świetny sposób nauki programowania.

---

## 💡 Najważniejsze wnioski

- Claude Code = asystent kodowania AI w terminalu; instalowany przez `npm install -g @anthropic-ai/claude-code`.
- Potrzebuje **Node.js** (zainstaluj najpierw przez winget).
- Uruchom `claude` w folderze projektu, potem opisuj zadania prostym językiem.
- **Pyta przed** edycją plików lub uruchamianiem komend — zawsze przeglądaj.

🌐 [English](../../en/lessons/13-claude-code-cli.md) · [← Wstecz](12-vscode.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)
