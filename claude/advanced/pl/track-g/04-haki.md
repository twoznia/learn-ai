# G4 — Haki (hooks)

⏱️ **15 minut** · Ścieżka: 🅶 Claude Code w głąb · Potrzebne: Claude Code zainstalowany i zalogowany

🌐 [English](../../en/track-g/04-hooks.md) · [← Wstecz](03-podagenci.md) · [Indeks ścieżki](../README.md) · [Dalej: MCP w Claude Code →](05-mcp-w-claude-code.md)

---

## 🧠 Teoria (5 min)

**Haki** pozwalają uruchamiać **własne polecenia automatycznie** w konkretnych momentach sesji Claude Code — uruchamia je narzędzie, nie Claude. Tak egzekwujesz zasady i automatyzujesz roboty, które powinny dziać się *za każdym razem*, bez pytania.

Częste zdarzenia do podpięcia:

| Zdarzenie | Uruchamia się… | Świetne do |
|-------|--------|-----------|
| **PreToolUse** | Przed użyciem narzędzia przez Claude | Blokowania ryzykownych akcji, barierek |
| **PostToolUse** | Po uruchomieniu narzędzia | Auto-formatowania pliku po edycji |
| **UserPromptSubmit** | Gdy wysyłasz wiadomość | Wstrzykiwania kontekstu, logowania |
| **Stop** | Gdy Claude kończy odpowiedź | Powiadomień, uruchamiania testów |

Różnica względem CLAUDE.md czy komend: te *proszą* Claude o zrobienie rzeczy (może, ale nie musi). **Hak zawsze się uruchamia** — jest deterministyczny. Używaj haków do czegokolwiek, co musi się dziać bez zawodu (format przy zapisie, blokada edycji chronionych plików, uruchomienie sprawdzenia).

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Znajdź plik ustawień

Haki mieszkają w **ustawieniach** Claude Code (`.claude/settings.json` w projekcie lub ustawienia użytkownika). Utwórz/otwórz ten projektowy:

```powershell
mkdir .claude
notepad .claude\settings.json
```

### Krok 2 — Dodaj prosty hak „powiadom, gdy gotowe”

Wklej minimalny blok haków (to uruchamia polecenie, gdy Claude kończy):

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          { "type": "command", "command": "echo Claude finished a turn >> claude-activity.log" }
        ]
      }
    ]
  }
}
```

Zapisz, zrestartuj sesję i zrób cokolwiek. Sprawdź `claude-activity.log` — linia została dopisana **automatycznie**, gdy Claude skończył. To hak.

### Krok 3 — Auto-formatowanie po edycjach (PostToolUse)

Klasyczne użycie: po edycji pliku przez Claude uruchom formater, by kod był zawsze schludny. Kształt (dostosuj polecenie do narzędzi):

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          { "type": "command", "command": "echo formatted >> claude-activity.log" }
        ]
      }
    ]
  }
}
```

Zamień `echo` na prawdziwe polecenie formatera (np. wywołanie Prettier/Black). Teraz każda edycja jest auto-formatowana — nigdy nie prosisz.

### Krok 4 — Dodaj barierkę (PreToolUse)

Hak **PreToolUse** może zbadać akcję *przed* jej uruchomieniem i zablokować ją — np. odmówić edycji chronionego pliku. Koncepcyjnie:

- Dopasuj do narzędzia (edycja).
- Uruchom małe polecenie sprawdzające.
- Jeśli sygnalizuje „blokuj”, akcja jest zatrzymana.

Tak egzekwujesz „nigdy nie dotykaj `secrets.env`” jako twardą zasadę, nie uprzejmą prośbę. (Trzymaj pierwsze barierki proste; testuj je przed zaufaniem.)

### Krok 5 — Trzymaj haki bezpieczne i proste

- Haki uruchamiają **prawdziwe polecenia na Twojej maszynie** — dodawaj tylko te, które rozumiesz.
- Zacznij od nieszkodliwych haków (logowanie) i sprawdź, że się uruchamiają, zanim dodasz blokujące lub zmieniające.
- Trzymaj polecenia szybkie; wolny hak spowalnia każdą turę.

### Krok 6 — Zdecyduj, co zasługuje na hak

Zapytaj: *czy to musi się dziać za każdym razem, gwarantowanie?* Jeśli tak → hak. Jeśli okazjonalne lub oparte na osądzie → komenda ukośnik lub zwykłe poproszenie Claude jest lepsze.

---

## 🧩 Hak czy nie?

| Potrzeba | Użyj |
|------|-----|
| Formatuj każdy plik po edycji | **Hak PostToolUse** |
| Blokuj edycje chronionego pliku | **Hak PreToolUse** |
| Loguj/powiadamiaj przy końcu tury | **Hak Stop** |
| Recenzja, którą robisz czasem | Komenda ukośnik (G2) |
| Zadanie jednorazowe | Po prostu poproś Claude |

> ⚠️ **Haki wykonują polecenia automatycznie.** Traktuj plik ustawień jak kod, któremu ufasz: żadnych niezaufanych poleceń, testuj przed poleganiem na haku blokującym i trzymaj plik z dala od miejsc publicznych, jeśli odwołuje się do czegoś wrażliwego.

---

## ✅ Sprawdzenie

- [ ] Dodałeś hak `Stop` i potwierdziłeś, że się uruchomił (pojawiła się linia w logu).
- [ ] Rozumiesz PreToolUse / PostToolUse / UserPromptSubmit / Stop.
- [ ] Umiesz wyjaśnić, czemu hak jest deterministyczny vs proszenie Claude.
- [ ] Znasz zasadę bezpieczeństwa: haki uruchamiają prawdziwe polecenia — tylko zaufane.

---

## 🎯 Zadanie

Dodaj jeden naprawdę przydatny hak: auto-format po edycjach lub log/powiadomienie na Stop. Sprawdź, że uruchamia się niezawodnie. Potem zapisz jedną barierkę, którą chciałbyś jako hak PreToolUse (np. ochrona pliku) — wdroż ją dopiero, gdy jesteś pewny.

---

## 💡 Najważniejsze wnioski

- **Haki** uruchamiają **Twoje polecenia automatycznie** na zdarzeniach sesji (PreToolUse, PostToolUse, UserPromptSubmit, Stop) — deterministyczne, inaczej niż proszenie Claude.
- Świetne do **formatowania przy edycji**, **barierek** i **powiadomień**, które muszą dziać się za każdym razem.
- Wykonują **prawdziwe polecenia** — dodawaj tylko zaufane, zaczynaj prosto i testuj przed poleganiem na hakach blokujących.

🌐 [English](../../en/track-g/04-hooks.md) · [← Wstecz](03-podagenci.md) · [Indeks ścieżki](../README.md) · [Dalej: MCP w Claude Code →](05-mcp-w-claude-code.md)
