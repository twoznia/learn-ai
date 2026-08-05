# Lekcja 15 — MCP: połącz Claude z Twoimi narzędziami

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: Claude Desktop (L5)

🌐 [English](../../en/lessons/15-mcp-intro.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Teoria (4 min)

Dotąd Claude znał tylko to, co wpiszesz lub wyślesz. **MCP (Model Context Protocol)** to zmienia: to standardowy sposób bezpiecznego dawania Claude dostępu do **narzędzi i danych** — jak Twoje pliki, baza danych, kalendarz czy usługa sieciowa.

Analogia: MCP jest jak danie asystentowi **zestawu kluczy** do konkretnych pomieszczeń. Ty decydujesz, które klucze. **Serwer MCP** to mały program udostępniający jedną zdolność (np. „czytaj pliki w tym folderze”). Claude Desktop łączy się z tymi serwerami i może z nich korzystać, gdy to pomocne.

Dlaczego to ważne:
- Pytaj Claude o **swoje faktyczne pliki** bez wysyłania każdego z osobna.
- Pozwól Claude **wyszukiwać** lub podejmować działania w narzędziach, których już używasz.
- Zachowujesz kontrolę — serwery MCP udostępniają tylko to, na co pozwolisz.

> ⚠️ **Najpierw bezpieczeństwo:** łącz tylko serwery MCP, którym ufasz, i dawaj dostęp tylko do folderów/danych, z którymi jesteś komfortowy. Zacznij od nieszkodliwego folderu testowego.

---

## 🛠️ Praktyka (5 min)

Podłączymy oficjalny serwer MCP **Filesystem**, aby Claude Desktop mógł czytać pliki w jednym wybranym folderze. (Potrzebujesz Node.js z Lekcji 13.)

### Krok 1 — Utwórz bezpieczny folder testowy

W PowerShell:

```powershell
mkdir $HOME\claude-mcp-test
"Lista zakupów: mleko, jajka, chleb" | Out-File $HOME\claude-mcp-test\lista.txt
"Pomysl na projekt: aplikacja pogodowa dla ogrodnikow" | Out-File $HOME\claude-mcp-test\pomysly.txt
```

### Krok 2 — Otwórz plik konfiguracji Claude Desktop

1. W **Claude Desktop**: menu → **Settings** → **Developer** → **Edit Config** (otwiera `claude_desktop_config.json`).
2. Jeśli jest pusty, to w porządku — zaraz go wypełnimy.

> Plik znajduje się w `%APPDATA%\Claude\claude_desktop_config.json`. Możesz go też otworzyć bezpośrednio:
> ```powershell
> notepad $env:APPDATA\Claude\claude_desktop_config.json
> ```

### Krok 3 — Dodaj serwer Filesystem

Wklej to, zamieniając `TwojaNazwa` na swoją prawdziwą nazwę użytkownika Windows, i zapisz:

```json
{
  "mcpServers": {
    "my-files": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:\\Users\\TwojaNazwa\\claude-mcp-test"
      ]
    }
  }
}
```

> To mówi Claude Desktop: „uruchom serwer filesystem, który widzi tylko folder `claude-mcp-test`”. Ten jeden folder to *jedyna* rzecz, którą może czytać.

### Krok 4 — Uruchom ponownie Claude Desktop

**Całkowicie zamknij** Claude Desktop (prawy klik na ikonę na pasku zadań → Quit) i otwórz ponownie. Poszukaj małej ikony narzędzi/wtyczki wskazującej, że MCP jest połączony.

### Krok 5 — Wypróbuj

Zapytaj Claude Desktop:

```text
Jakie pliki są w moim połączonym folderze i co zawierają?
```

```text
Streść mój plik pomysly.txt i zaproponuj jedno ulepszenie.
```

Claude czyta prawdziwe pliki — bez wysyłania. 🎉 Aby później połączyć inny folder, zmień ścieżkę w konfiguracji.

---

## 🧭 Co jeszcze potrafi MCP

Istnieją serwery MCP do wielu rzeczy (bazy danych, GitHub, wyszukiwanie w sieci, kalendarze i więcej). Wzorzec jest zawsze taki sam:

1. Dodaj serwer do `claude_desktop_config.json`.
2. Uruchom ponownie Claude Desktop.
3. Poproś Claude, aby z niego skorzystał.

Poznaj oficjalne serwery na **https://modelcontextprotocol.io** i w dokumentacji Anthropic. Dodawaj tylko te, które rozumiesz i którym ufasz.

---

## ✅ Sprawdzenie

- [ ] Utworzyłeś bezpieczny folder testowy z kilkoma plikami.
- [ ] Dodałeś serwer filesystem do konfiguracji i uruchomiłeś ponownie.
- [ ] Claude przeczytał i streścił plik z tego folderu.

---

## 🎯 Zadanie

Dodaj drugi plik do `claude-mcp-test` (np. luźną listę zadań) i poproś Claude, aby zamienił go w czystą listę kontrolną. Zauważ, że niczego nie wysłałeś — MCP wykonało czytanie.

---

## 💡 Najważniejsze wnioski

- **MCP** bezpiecznie łączy Claude z narzędziami i danymi, które wybierasz.
- **Serwer MCP** udostępnia jedną zdolność (np. czytanie jednego folderu).
- Konfiguruj serwery w `claude_desktop_config.json`, potem uruchom ponownie Claude Desktop.
- Łącz tylko zaufane serwery i ograniczaj ich dostęp.

🌐 [English](../../en/lessons/15-mcp-intro.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)
