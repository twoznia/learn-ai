# Lekcja 08 — Instalacja Pythona na Windows

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Windows 10/11, internet

🌐 [English](../../en/lessons/08-install-python.md) · [← Wstecz](07-gems-wlasni-asystenci.md) · [Strona kursu](../README.md) · [Dalej: Klucz API →](09-klucz-api.md)

---

## 🧠 Teoria (2 min)

**Python** to język programowania, który czyta się prawie jak angielski. To język nr 1 dla AI, a Google udostępnia oficjalną bibliotekę (`google-genai`), która ułatwia rozmowę z Gemini. Nie musisz „zostać programistą” — będziesz kopiować małe skrypty i je uruchamiać.

Dwa słowa:
- **Python** — program uruchamiający Twój kod.
- **pip** — narzędzie Pythona do instalowania bibliotek. Jest *w zestawie* z Pythonem.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj Pythona

**Najprościej (winget):** otwórz **PowerShell** (Start → wpisz *PowerShell* → Enter) i uruchom:

```powershell
winget install --id Python.Python.3.12 -e
```

**Albo klasycznie:**
1. Wejdź na **https://www.python.org/downloads/**
2. Kliknij duży przycisk **Download Python**.
3. Uruchom instalator i **‼️ ZAZNACZ POLE „Add python.exe to PATH”** na dole przed kliknięciem **Install Now**. To jedno pole zapobiega 90% problemów początkujących.

### Krok 2 — Zamknij i otwórz ponownie PowerShell

Po instalacji **zamknij PowerShell i otwórz nowe okno**, aby wykrył nowego Pythona.

### Krok 3 — Sprawdź, czy działa

```powershell
python --version
```

Powinieneś zobaczyć coś jak `Python 3.12.x`. Potem:

```powershell
pip --version
```

Powinieneś zobaczyć linię `pip 24.x ...`. ✅ Oba działają = gotowe.

> **Jeśli `python` otwiera Sklep Microsoft:** Start → **Zarządzaj aliasami wykonywania aplikacji** → **WYŁĄCZ** przełączniki dla **python.exe** i **python3.exe**. Otwórz ponownie PowerShell i spróbuj. (Albo zainstaluj ponownie z zaznaczonym polem *Add to PATH*.)

### Krok 4 — Uruchom pierwszą linię Pythona

```powershell
python -c "print('Cześć z Pythona! Jesteś gotowy na AI.')"
```

Jeśli widzisz wypisany komunikat, wszystko działa. 🎉

---

## 🗂️ Utwórz folder na kurs

```powershell
mkdir $HOME\learn-ai-gemini
cd $HOME\learn-ai-gemini
```

`$HOME` to Twój folder użytkownika (jak `C:\Users\TwojaNazwa`). Będziesz tu trzymać wszystkie skrypty.

---

## ✅ Sprawdzenie

- [ ] `python --version` pokazuje Python 3.x.
- [ ] `pip --version` działa.
- [ ] Linia „Cześć z Pythona” się wypisała.
- [ ] Utworzyłeś folder `learn-ai-gemini`.

---

## 🎯 Zadanie

Jeśli coś zwróciło błąd, zastosuj sztuczkę z Lekcji 4: wytnij błąd (**Win+Shift+S**), wklej do Gemini i zapytaj *„Jak naprawić ten błąd instalacji Pythona na Windows? Jestem początkujący.”*

---

## 💡 Najważniejsze wnioski

- Zainstaluj Pythona przez `winget install --id Python.Python.3.12 -e` **lub** z python.org (zaznacz **Add to PATH**).
- Zawsze **otwórz ponownie** terminal po instalacji.
- Sprawdź przez `python --version` i `pip --version`.
- `pip` instaluje biblioteki; jest w zestawie z Pythonem.

🌐 [English](../../en/lessons/08-install-python.md) · [← Wstecz](07-gems-wlasni-asystenci.md) · [Strona kursu](../README.md) · [Dalej: Klucz API →](09-klucz-api.md)
