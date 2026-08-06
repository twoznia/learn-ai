# Lekcja 13 — Codex CLI w terminalu

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: Windows, konto ChatGPT lub klucz API

🌐 [English](../../en/lessons/13-codex-cli.md) · [← Wstecz](12-vscode-ai.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)

---

## 🧠 Teoria (3 min)

**Codex CLI** to otwartoźródłowy asystent kodowania AI od OpenAI, który działa w **terminalu**. W odróżnieniu od okna czatu potrafi:

- **czytać pliki Twojego projektu**,
- **pisać i edytować kod**,
- **uruchamiać komendy** (za Twoim pozwoleniem),
- samodzielnie przechodzić przez wieloetapowe zadania.

Wyobraź sobie młodszego programistę przy Twojej klawiaturze — opisujesz, czego chcesz, prostym językiem, a on wykonuje pracę, pytając przed czymś ryzykownym.

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

### Krok 2 — Zainstaluj Codex CLI

```powershell
npm install -g @openai/codex
```

`-g` oznacza „zainstaluj globalnie”, dzięki czemu uruchomisz go z każdego folderu.

Sprawdź:

```powershell
codex --version
```

### Krok 3 — Uruchom w projekcie

```powershell
cd $HOME\learn-ai-gpt
codex
```

Za pierwszym razem przeprowadzi Cię przez **logowanie** — możesz zalogować się **kontem ChatGPT** lub użyć `OPENAI_API_KEY`. Postępuj zgodnie z komunikatami.

### Krok 4 — Daj mu zadanie

Gdy Codex działa, po prostu wpisz, czego chcesz:

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
| Uruchomić Codex | `codex` (w folderze projektu) |
| Wyjść | Naciśnij dwa razy Ctrl+C (lub wpisz pokazaną komendę wyjścia) |
| Zobaczyć pomoc | Wpisz `/help` |
| Cofnąć zmianę | Poproś: „cofnij ostatnią zmianę” |
| Zachować bezpieczeństwo | Zawsze **czytaj** propozycję przed zatwierdzeniem |

> **Złota zasada bezpieczeństwa:** Codex pyta przed edycją plików lub uruchomieniem komend. Przeczytaj podgląd. Jeśli nie masz pewności, zapytaj *„wyjaśnij, co robi ta komenda i czy jest bezpieczna”*.

---

## ✅ Sprawdzenie

- [ ] `node --version` i `npm --version` działają.
- [ ] `codex --version` działa.
- [ ] Codex utworzył plik, który zatwierdziłeś.
- [ ] Poprosiłeś o ulepszenie i zedytował kod.

---

## 🎯 Zadanie

Zapytaj Codex: *„Dodaj komentarze do todo.py wyjaśniające każdą część dla początkującego, potem podaj mi jednoakapitowe podsumowanie działania programu.”* Przeczytaj podsumowanie — to świetny sposób nauki programowania.

---

## 💡 Najważniejsze wnioski

- Codex CLI = asystent kodowania AI od OpenAI w terminalu; instalowany przez `npm install -g @openai/codex`.
- Potrzebuje **Node.js** (zainstaluj najpierw przez winget).
- Uruchom `codex` w folderze projektu; zaloguj się kontem ChatGPT lub kluczem API.
- **Pyta przed** edycją plików lub uruchamianiem komend — zawsze przeglądaj.

🌐 [English](../../en/lessons/13-codex-cli.md) · [← Wstecz](12-vscode-ai.md) · [Strona kursu](../README.md) · [Dalej: Mini projekt →](14-mini-projekt.md)
