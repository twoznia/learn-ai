# Lekcja 05 — Instalacja Claude Desktop na Windows

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows 10/11, konto Claude

🌐 [English](../../en/lessons/05-install-claude-desktop.md) · [← Wstecz](04-pliki-i-obrazy.md) · [Strona kursu](../README.md) · [Dalej: Codzienne zadania →](06-codzienne-zadania.md)

---

## 🧠 Teoria (2 min)

**Claude Desktop** to darmowa aplikacja dla Windows — ten sam Claude, ale jako dedykowany program zamiast karty przeglądarki. Po co?

- **Zawsze pod ręką** — przypnij do paska zadań, uruchamiaj skrótem.
- **Skupienie** — brak kart przeglądarki, powiadomień i rozpraszaczy.
- **Odblokowuje MCP** później — Claude Desktop może bezpiecznie łączyć się z narzędziami na Twoim komputerze (Lekcja 15). To główny powód instalacji.

---

## 🛠️ Praktyka (7 min)

### Opcja A — Pobierz ze strony (najprościej)

1. Otwórz przeglądarkę i wejdź na **https://claude.ai/download**
2. Kliknij przycisk pobierania dla **Windows**. Otrzymasz plik w rodzaju `Claude-Setup.exe` w folderze **Pobrane**.
3. Kliknij dwukrotnie plik.
4. Jeśli Windows pokaże niebieskie okno **„Windows ochronił Twój komputer”** (SmartScreen): kliknij **Więcej informacji → Uruchom mimo to** (to normalne dla świeżo pobranych aplikacji z legalnych stron).
5. Postępuj zgodnie z instalatorem. To szybkie — bez skomplikowanych opcji.
6. Po otwarciu **zaloguj się** kontem założonym w Lekcji 2.

### Opcja B — Instalacja przez `winget` (sposób pro)

Windows ma wbudowany menedżer pakietów **winget**. Instaluje aplikacje jedną komendą — będziesz go w tym kursie używać często.

1. Kliknij **Start**, wpisz **PowerShell**, otwórz **Windows PowerShell**.
2. Wklej to i naciśnij Enter:

```powershell
winget install --id Anthropic.Claude -e
```

3. Jeśli poprosi o akceptację warunków, wpisz **Y** i Enter.

> Jeśli `winget` nie zostanie znaleziony, zainstaluj **Instalator aplikacji** ze Sklepu Microsoft i spróbuj ponownie. Albo po prostu użyj Opcji A.

### Krok — Przypnij dla szybkiego dostępu

1. Gdy Claude Desktop jest otwarty, **kliknij prawym na jego ikonę** na pasku zadań.
2. Kliknij **Przypnij do paska zadań**.
3. Teraz jest o jedno kliknięcie stąd, na zawsze.

### Krok — Przetestuj

Wpisz do Claude Desktop:
```text
Podaj 3-punktową listę kontrolną na produktywny początek dnia pracy.
```

Ten sam mózg co na stronie — teraz w zgrabnej aplikacji. ✅

---

## 🆚 Sieć vs Desktop — czego używać?

| Sytuacja | Użyj |
|-----------|-----|
| Szybkie pytanie, dowolne urządzenie | **Sieć** (claude.ai) |
| Codzienna praca na komputerze | **Desktop** |
| Łączenie Claude z plikami/narzędziami (MCP) | **Desktop** (Lekcja 15) |
| Publiczny/wspólny komputer | **Sieć**, potem wyloguj się |

Możesz używać obu na jednym koncie — rozmowy się synchronizują.

---

## ✅ Sprawdzenie

- [ ] Claude Desktop jest zainstalowany i jesteś zalogowany.
- [ ] Jest przypięty do paska zadań.
- [ ] Wysłałeś jedną wiadomość z aplikacji.

---

## 🎯 Zadanie

Wyrób nawyk uruchamiania: naciśnij **klawisz Windows**, wpisz **Claude**, naciśnij **Enter**. Zrób to 3 razy, aż wejdzie w pamięć mięśniową. Szybki dostęp = faktycznie będziesz używać.

---

## 💡 Najważniejsze wnioski

- Claude Desktop = ten sam Claude w skupionej aplikacji Windows.
- Instaluj przez **claude.ai/download** lub `winget install --id Anthropic.Claude -e`.
- „Uruchom mimo to” w SmartScreen jest normalne dla nowych plików.
- Desktop jest potrzebny później do **MCP** (łączenia Claude z narzędziami).

🌐 [English](../../en/lessons/05-install-claude-desktop.md) · [← Wstecz](04-pliki-i-obrazy.md) · [Strona kursu](../README.md) · [Dalej: Codzienne zadania →](06-codzienne-zadania.md)
