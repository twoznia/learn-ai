# A3 — Zaawansowane MCP

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: Claude Desktop + Node.js (z kursu podstawowego)

🌐 [English](../../en/track-a/03-advanced-mcp.md) · [← Wstecz](02-biblioteka-promptow.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym podłączyłeś **jeden** serwer MCP (filesystem) do Claude Desktop. Teraz idziemy dalej: **wiele serwerów działających razem** oraz nawyki bezpieczeństwa ważne, gdy Claude może dotykać prawdziwych rzeczy.

Kluczowe idee:

- **Komponowanie serwerów.** Mając serwer filesystem *i* serwer fetch/wyszukiwania, Claude może czytać Twoje notatki **i** sprawdzać informacje, potem je łączyć.
- **Najmniejsze uprawnienia.** Daj każdemu serwerowi najwęższy dostęp, który wciąż wykonuje zadanie. Serwer filesystem powinien wskazywać jeden folder projektu, nigdy cały `C:`.
- **Wiedz, co się uruchamia.** Każdy serwer MCP to mały program uruchamiany na Twoim PC. Dodawaj tylko serwery, które rozumiesz i którym ufasz.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Skieruj serwer filesystem na prawdziwy folder roboczy

Utwórz folder, z którym faktycznie chcesz pomocy Claude, np. projekt badawczy lub pisarski:

```powershell
mkdir $HOME\mcp-workspace
"Szkic: powody, by zmienic narzedzie do newslettera" | Out-File $HOME\mcp-workspace\szkic.md
```

### Krok 2 — Skonfiguruj dwa serwery razem

Otwórz konfigurację Claude Desktop:

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Wklej to (zamień `TwojaNazwa`), co rejestruje **dwa** serwery — filesystem i fetch:

```json
{
  "mcpServers": {
    "workspace": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:\\Users\\TwojaNazwa\\mcp-workspace"
      ]
    },
    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    }
  }
}
```

> Serwer **fetch** pozwala Claude pobrać wskazaną stronę WWW. Jeśli konkretny pakiet serwera nie jest dostępny na Twoim komputerze — to w porządku, liczy się *wzorzec* rejestrowania wielu serwerów. Zostaw tylko te, które instalują się bez błędów.

### Krok 3 — Uruchom ponownie Claude Desktop

Całkowicie zamknij (prawy klik na ikonę → Quit) i otwórz ponownie. Poszukaj wskaźnika narzędzi/wtyczki pokazującego, że serwery są połączone.

### Krok 4 — Skomponuj je w jednym zadaniu

Zapytaj Claude Desktop o coś, co wymaga **zarówno** czytania Twojego pliku, jak i pobrania informacji:

```text
Przeczytaj szkic.md z mojego workspace. Potem pobierz ten artykuł <wklej URL> i
zaproponuj 3 konkretne ulepszenia mojego szkicu na jego podstawie. Zacytuj, czego użyłeś.
```

Claude czyta lokalnie *i* pobiera stronę — przepływ, którego żaden serwer nie zrobiłby sam.

### Krok 5 — Ćwicz najmniejsze uprawnienia

Zapytaj się przy każdym serwerze: *jaki jest najmniejszy zakres, który wciąż działa?*

- Filesystem → **jeden** folder, nie katalog użytkownika.
- Wszystko, co może zmieniać lub wysyłać dane → szczególna ostrożność; podczas nauki preferuj serwery tylko do odczytu.
- Usuń z konfiguracji serwery, których aktywnie nie używasz.

---

## 🔒 Lista kontrolna bezpieczeństwa MCP

| Sprawdź | Dlaczego |
|-------|-----|
| Czy ufam źródłu tego serwera? | Uruchamia się jako program na Twoim PC |
| Czy dostęp filesystem jest ograniczony do jednego folderu? | Kontrola zasięgu skutków |
| Czy zaraz pozwolę Claude *zmieniać* lub *wysyłać* rzeczy? | Tylko odczyt jest bezpieczniejszy przy nauce |
| Czy usunąłem serwery, których nie używam? | Mniej ruchomych części, mniej ryzyka |
| Czy przeglądam, co Claude robi z narzędziami? | Wciąż jesteś człowiekiem w pętli |

---

## ✅ Sprawdzenie

- [ ] Skonfigurowałeś **dwa** serwery w jednym pliku konfiguracji.
- [ ] Claude połączył lokalny plik z pobraną/wyszukaną informacją w jednej odpowiedzi.
- [ ] Potrafisz podać *najmniejsze uprawnienia* dla każdego dodanego serwera.

---

## 🎯 Zadanie

Zaprojektuj (na papierze) konfigurację MCP dla realnego, powtarzalnego zadania — które serwery, o jakim zakresie, tylko do odczytu czy nie. Potem wdroż tylko części tylko do odczytu i wypróbuj jeden skomponowany przepływ.

---

## 💡 Najważniejsze wnioski

- Wiele serwerów MCP potrafi się **komponować** — czytać lokalne pliki *i* pobierać/wyszukiwać, razem.
- Stosuj **najmniejsze uprawnienia**: najwęższy zakres, preferuj tylko odczyt przy nauce.
- Dodawaj tylko zaufane serwery; pozostajesz człowiekiem przeglądającym, co się dzieje.

🌐 [English](../../en/track-a/03-advanced-mcp.md) · [← Wstecz](02-biblioteka-promptow.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
