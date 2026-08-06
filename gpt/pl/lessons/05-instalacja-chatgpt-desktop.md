# Lekcja 05 — Instalacja aplikacji ChatGPT

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows 10/11, konto ChatGPT

🌐 [English](../../en/lessons/05-install-chatgpt-desktop.md) · [← Wstecz](04-pliki-i-obrazy.md) · [Strona kursu](../README.md) · [Dalej: Codzienne zadania →](06-codzienne-zadania.md)

---

## 🧠 Teoria (2 min)

**ChatGPT dla Windows** to darmowa aplikacja desktopowa — ten sam ChatGPT, ale jako dedykowany program zamiast karty przeglądarki. Po co?

- **Zawsze pod ręką** — przypnij do paska zadań, uruchamiaj skrótem.
- **Skupienie** — brak kart przeglądarki i rozpraszaczy.
- **Przydatne dodatki** — skrót do szybkiego uruchamiania i „praca z aplikacjami”, która potrafi odczytać, co jest na ekranie (np. edytor kodu), aby pomóc w kontekście.

---

## 🛠️ Praktyka (7 min)

### Opcja A — Sklep Microsoft (najprościej)

1. Otwórz **Sklep Microsoft** (Start → wpisz *Sklep*).
2. Wyszukaj **ChatGPT** (wydawca **OpenAI**).
3. Kliknij **Pobierz / Zainstaluj**.
4. Uruchom i **zaloguj się** kontem założonym w Lekcji 2.

### Opcja B — Pobierz z OpenAI

1. Wejdź na **https://openai.com/chatgpt/download**
2. Pobierz aplikację **Windows** i uruchom instalator.
3. Jeśli Windows pokaże niebieskie okno **„Windows ochronił Twój komputer”** (SmartScreen): kliknij **Więcej informacji → Uruchom mimo to** (normalne dla świeżo pobranych aplikacji z legalnych stron).
4. Zaloguj się po otwarciu.

### Opcja C — winget (sposób pro)

W PowerShell najpierw wyszukaj pakiet, potem zainstaluj to, co znajdzie:

```powershell
winget search ChatGPT
```

Jeśli pojawi się oficjalny wpis **OpenAI ChatGPT**, zainstaluj (zamień id na ten pokazany):

```powershell
winget install --id OpenAI.ChatGPT -e
```

> Jeśli winget nie znajdzie — po prostu użyj Opcji A (Sklep Microsoft), to najłatwiejsza droga.

### Krok — Przypnij dla szybkiego dostępu

1. Gdy aplikacja jest otwarta, **kliknij prawym na jej ikonę** na pasku zadań.
2. Kliknij **Przypnij do paska zadań**.
3. Teraz jest o jedno kliknięcie stąd, na zawsze.

### Krok — Przetestuj

Wpisz do aplikacji:
```text
Podaj 3-punktową listę kontrolną na produktywny początek dnia pracy.
```

Ten sam mózg co na stronie — teraz w zgrabnej aplikacji. ✅

---

## 🆚 Sieć vs Desktop — czego używać?

| Sytuacja | Użyj |
|-----------|-----|
| Szybkie pytanie, dowolne urządzenie | **Sieć** (chatgpt.com) |
| Codzienna praca na komputerze | **Desktop** |
| Pomoc z tym, co na ekranie | **Desktop** („praca z aplikacjami”) |
| Publiczny/wspólny komputer | **Sieć**, potem wyloguj się |

Możesz używać obu na jednym koncie — rozmowy się synchronizują.

---

## ✅ Sprawdzenie

- [ ] Aplikacja ChatGPT jest zainstalowana i jesteś zalogowany.
- [ ] Jest przypięta do paska zadań.
- [ ] Wysłałeś jedną wiadomość z aplikacji.

---

## 🎯 Zadanie

Wyrób nawyk uruchamiania: naciśnij **klawisz Windows**, wpisz **ChatGPT**, naciśnij **Enter**. Zrób to 3 razy, aż wejdzie w pamięć mięśniową.

---

## 💡 Najważniejsze wnioski

- ChatGPT dla Windows = ten sam ChatGPT w skupionej aplikacji.
- Instaluj przez **Sklep Microsoft**, **openai.com/chatgpt/download** lub winget.
- „Uruchom mimo to” w SmartScreen jest normalne dla nowych plików.
- Przypnij do paska zadań dla dostępu jednym kliknięciem.

🌐 [English](../../en/lessons/05-install-chatgpt-desktop.md) · [← Wstecz](04-pliki-i-obrazy.md) · [Strona kursu](../README.md) · [Dalej: Codzienne zadania →](06-codzienne-zadania.md)
