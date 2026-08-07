# Projekt końcowy 08 — Testuj, utwardź i wydaj

⏱️ **16 minut** · Poziom: Projekt końcowy · Wymagania: działający agent Drugiego Mózgu (Lekcja 7)

🌐 [English](../../en/lessons/08-test-harden-and-ship.md) · [← Poprzednia](07-uruchom-agenta.md) · [Strona projektu](../README.md) · [↩ Wszystkie kursy](../../../README.md)

---

## 🧠 Teoria (3 min)

Zbudowałeś/aś działającego agenta. By uczynić go czymś, czemu **ufasz i co zachowasz**, zakończ jak inżynier: **przetestuj** go, **utwardź** przeciw pomyłkom i **wydaj** na GitHub z dokumentacją — by przetrwał, ulepszał się i mógł nawet pomóc innym.

Trzy fronty:

- **Testuj** — czy każde narzędzie zachowuje się na przypadkach brzegowych? Czy przypominanie pozostaje osadzone?
- **Utwardź** — bezpieczeństwo (zakres, zatwierdzenia, sekrety) i niezawodność (lepsze docstringi/opisy).
- **Wydaj** — README, historia git i repo GitHub; potem rozwiń.

---

## 🛠️ Praktyka (12 min)

### Krok 1 — Testuj narzędzia na przypadkach brzegowych

Poproś agenta, by sam sondował swoje narzędzia:

```text
Przetestuj moje narzędzia: zapisz notatkę z pustym tytułem, przeszukaj coś, co
nie istnieje, i pobierz notatkę, której nie ma. Zaraportuj, co się stało.
```

Napraw cokolwiek brzydkiego (np. nieprzydatny komunikat) w `brain_server.py`. To nastawienie ewaluacyjne z kursu Inżynierii promptów, zastosowane do Twoich narzędzi.

### Krok 2 — Utwardź granicę bezpieczeństwa

Potwierdź, że bariery trzymają:
- **Zakres:** serwer dotyka tylko `notes\` (zweryfikuj w kodzie).
- **Zatwierdzenia:** agent wciąż pyta przed zapisem — trzymaj to włączone.
- **Sekrety:** nie umieszczaj haseł ani prywatnych danych w notatkach, które zpushujesz publicznie. Dodaj `.gitignore`, jeśli notatki są prywatne:

```powershell
notepad .gitignore
```

```text
# Trzymaj prywatne notatki poza git (usuń tę linię, by je wersjonować)
notes/
.claude/settings.local.json
```

> Zdecyduj rozważnie: **commituj notatki** (wersjonowane, backup) *lub* **gitignoruj je** (prywatne). Jedno i drugie w porządku — po prostu wybierz świadomie.

### Krok 3 — Popraw niezawodność, gdzie się poślizgnęła

Jeśli podczas Lekcji 7 agent kiedyś wybrał złe narzędzie lub Skill się nie odpalił, dociśnij teraz **docstring** lub **opis** Skilla. Precyzyjny tekst „use when…" to Twoje pokrętło niezawodności.

### Krok 4 — Napisz README

Poproś agenta (to Skill Copilota/README w akcji):

```text
Napisz README.md dla tego projektu: czym jest, architektura (agent + narzędzia
MCP + Skille + notatki), jak skonfigurować na Windows i jak używać. Zweryfikuj
kroki konfiguracji wobec rzeczywistych plików.
```

Przejrzyj, uruchom kroki, by potwierdzić trafność, i zapisz.

### Krok 5 — Wydaj na GitHub

```powershell
git add -A
git commit -m "Second Brain agent: MCP tools + Skills + docs"
```

Potem opublikuj (przycisk **Publish to GitHub** w VS Code lub utwórz repo na github.com i zpushuj). Zdecyduj **prywatne czy publiczne** — prywatne, jeśli notatki są zacommitowane.

### Krok 6 — Rozwiń (wybierz jedno)

Twój Drugi Mózg to teraz platforma. Dodaj jedną rzecz:

- **Nowe narzędzie** — `delete_note`, `edit_note` lub `notes_by_date(range)`.
- **Nowy Skill** — rytuał „dziennego przechwytywania" lub styl „zapisywacza linków".
- **Automatyzacja** — zaplanuj przegląd tygodniowy Harmonogramem zadań Windows (Ścieżka C kursu zaawansowanego), używając `claude` w trybie bezobsługowym.
- **Więcej zasięgu** — dodaj drugi serwer MCP (np. kalendarz) i niech przegląd go uwzględnia.

---

## 🧩 Lista kontrolna wydania

| Front | Gotowe, gdy |
|-------|-----------|
| **Przetestowane** | Przypadki brzegowe obsłużone; przypominanie osadzone |
| **Ograniczone** | Serwer dotyka tylko `notes\`; zatwierdzenia włączone |
| **Prywatne** | Sekrety poza; commit/ignore notatek wybrany |
| **Udokumentowane** | Trafne README (zweryfikowane kroki) |
| **Wydane** | Zacommitowane i zpushowane na GitHub |
| **Rozwinięte** | Jedno nowe narzędzie / Skill / automatyzacja |

---

## ✅ Sprawdzian

- [ ] Przetestowałeś/aś narzędzia na przypadkach brzegowych i naprawiłeś/aś szorstkie miejsca.
- [ ] Bezpieczeństwo potwierdzone: ograniczony serwer, zatwierdzenia włączone, sekrety obsłużone.
- [ ] Napisałeś/aś i zweryfikowałeś/aś README.
- [ ] Projekt jest na GitHubie, a Ty dodałeś/aś jedno rozszerzenie.

---

## 🎯 Praca domowa

Wydaj Drugi Mózg na GitHub z solidnym README, potem używaj go codziennie przez tydzień. Za każdym razem, gdy zrobi coś niezręcznego, napraw docstring/Skill/narzędzie, które to spowodowało. Ta pętla prawdziwe-użycie → dopracowanie to dokładnie, jak profesjonaliści utwardzają produkt AI.

---

## 💡 Najważniejsze wnioski

- Zakończ jak inżynier: **testuj** przypadki brzegowe, **utwardzaj** (zakres, zatwierdzenia, sekrety, ciaśniejsze docstringi/opisy) i **wydawaj** z dokumentacją.
- Wybierz rozważnie, czy **commitować czy gitignorować** notatki, i trzymaj sekrety poza publicznym repo.
- Twój Drugi Mózg to **platforma** — rozwijaj go nowymi narzędziami, Skillami lub zaplanowaną automatyzacją. Zbudowałeś/aś prawdziwego agenta. 🎉

🌐 [English](../../en/lessons/08-test-harden-and-ship.md) · [← Poprzednia](07-uruchom-agenta.md) · [Strona projektu](../README.md) · [↩ Wszystkie kursy](../../../README.md)
