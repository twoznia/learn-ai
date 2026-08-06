# C1 — Harmonogram zadań (Task Scheduler)

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `google-genai` + klucz API

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)

---

## 🧠 Teoria (3 min)

Automatyzacja oznacza, że komputer wykonuje pracę **bez uruchamiania jej przez Ciebie**. Windows ma wbudowany **Harmonogram zadań** — uruchamia program według harmonogramu.

Nasz plan: mały skrypt Pythona prosi Gemini o codzienny brief, a Harmonogram zadań uruchamia go **każdego ranka**, zapisując wynik do pliku.

Zaplanowane zadanie działa **jako Twój użytkownik Windows**, więc może odczytać `GEMINI_API_KEY` ustawiony przez `setx`.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Napisz skrypt „codzienny brief”

W folderze kursu utwórz `daily_brief.py`:

```python
from google import genai
from datetime import date
from pathlib import Path

client = genai.Client()

TOPIC = "produktywność i skupienie"

resp = client.models.generate_content(
    model="gemini-2.5-flash",
    contents=(
        f"Napisz mi krótki codzienny brief o: {TOPIC}: "
        "jedna motywująca myśl, jedna praktyczna wskazówka na dziś "
        "i jedno pytanie do refleksji. Zmieść się w 150 słowach."
    ),
)

out_dir = Path.home() / "daily-briefs"
out_dir.mkdir(exist_ok=True)
out_file = out_dir / f"brief-{date.today().isoformat()}.md"
out_file.write_text(resp.text, encoding="utf-8")
print(f"Zapisano: {out_file}")
```

### Krok 2 — Uruchom raz ręcznie

```powershell
cd $HOME\learn-ai-gemini
python daily_brief.py
```

Sprawdź `C:\Users\TwojaNazwa\daily-briefs\`.

### Krok 3 — Znajdź ścieżkę do Pythona

```powershell
(Get-Command python).Source
```

Skopiuj wypisaną ścieżkę.

### Krok 4 — Utwórz zaplanowane zadanie

Zamień obie ścieżki na **swoją** ścieżkę Pythona i ścieżkę skryptu:

```powershell
schtasks /create /tn "GeminiDailyBrief" `
  /tr "'C:\Sciezka\Do\python.exe' 'C:\Users\TwojaNazwa\learn-ai-gemini\daily_brief.py'" `
  /sc daily /st 08:00
```

### Krok 5 — Przetestuj bez czekania

```powershell
schtasks /run /tn "GeminiDailyBrief"
```

Sprawdź folder w poszukiwaniu świeżego pliku. 🎉 Działa bez nadzoru.

> **Wolisz klikać?** **Harmonogram zadań** → **Utwórz zadanie podstawowe** → Codziennie → ustaw godzinę → **Uruchom program** → Program = Twój `python.exe`, argumenty = ścieżka skryptu.

### Krok 6 — Zarządzaj nim

```powershell
schtasks /query /tn "GeminiDailyBrief"
schtasks /delete /tn "GeminiDailyBrief" /f
```

---

## 🧩 Dlaczego to działa

| Element | Rola |
|-------|------|
| Skrypt Pythona | Wykonuje pracę AI, zapisuje plik |
| Harmonogram zadań | Uruchamia go według harmonogramu |
| Działa jako Twój użytkownik | Może odczytać `GEMINI_API_KEY` |
| Zapisuje do pliku | Dostajesz wynik bez patrzenia |

---

## ✅ Sprawdzenie

- [ ] `daily_brief.py` działa ręcznie i zapisuje datowany plik.
- [ ] Utworzyłeś zaplanowane zadanie.
- [ ] `schtasks /run` wyprodukował świeży brief bez rąk.

---

## 🎯 Zadanie

Zmień `TOPIC` na coś, co Cię obchodzi, i ustaw godzinę, którą zauważysz. Pozwól temu działać kilka dni — przedsmak AI na autopilocie.

---

## 💡 Najważniejsze wnioski

- **Harmonogram zadań** uruchamia skrypty automatycznie, bez rąk.
- Podaj **pełną ścieżkę** do `python.exe` i skryptu.
- Zadania działają jako Twój użytkownik, więc czytają klucz API ze środowiska.
- Testuj przez `schtasks /run`.

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)
