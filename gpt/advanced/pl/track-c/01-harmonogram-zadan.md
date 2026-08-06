# C1 — Harmonogram skryptów w Harmonogramie zadań

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `openai` + klucz API

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)

---

## 🧠 Teoria (3 min)

Automatyzacja oznacza, że komputer wykonuje pracę **bez Twojego uruchamiania**. Windows ma wbudowany **Harmonogram zadań** — uruchamia program według harmonogramu.

Nasz plan: mały skrypt Pythona prosi GPT o dzienny brief, a Harmonogram zadań uruchamia go **każdego ranka**, zapisując wynik do pliku. Budzisz się, a brief już czeka.

Zaplanowane zadanie działa **jako Twój użytkownik Windows**, więc może odczytać `OPENAI_API_KEY` ustawiony przez `setx`.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Napisz skrypt „dziennego briefu”

W folderze kursu utwórz `daily_brief.py`:

```python
from openai import OpenAI
from datetime import date
from pathlib import Path

client = OpenAI()

TOPIC = "produktywność i skupienie"

resp = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{
        "role": "user",
        "content": (
            f"Napisz mi krótki dzienny brief o temacie {TOPIC}: "
            "jedna motywująca myśl, jedna praktyczna wskazówka na dziś "
            "i jedno pytanie do refleksji. Zmieść się w 150 słowach."
        ),
    }],
)
text = resp.choices[0].message.content

out_dir = Path.home() / "daily-briefs"
out_dir.mkdir(exist_ok=True)
out_file = out_dir / f"brief-{date.today().isoformat()}.md"
out_file.write_text(text, encoding="utf-8")
print(f"Zapisano: {out_file}")
```

### Krok 2 — Uruchom raz ręcznie

```powershell
cd $HOME\learn-ai-gpt
python daily_brief.py
```

Sprawdź `C:\Users\TwojaNazwa\daily-briefs\` i znajdź plik.

### Krok 3 — Znajdź ścieżkę do Pythona

```powershell
(Get-Command python).Source
```

Skopiuj wypisaną ścieżkę.

### Krok 4 — Utwórz zaplanowane zadanie

Zamień obie ścieżki na **swoją** ścieżkę do Pythona i do skryptu:

```powershell
schtasks /create /tn "GptDailyBrief" `
  /tr "'C:\Sciezka\Do\python.exe' 'C:\Users\TwojaNazwa\learn-ai-gpt\daily_brief.py'" `
  /sc daily /st 08:00
```

### Krok 5 — Przetestuj bez czekania

```powershell
schtasks /run /tn "GptDailyBrief"
```

Sprawdź folder — powinien pojawić się świeży plik. 🎉 Działa bez nadzoru.

> **Wolisz klikać?** Otwórz **Harmonogram zadań** → **Utwórz zadanie podstawowe** → Codziennie → ustaw godzinę → **Uruchom program** → Program = Twój `python.exe`, argumenty = ścieżka do skryptu.

### Krok 6 — Zarządzaj nim

```powershell
schtasks /query /tn "GptDailyBrief"
schtasks /delete /tn "GptDailyBrief" /f
```

---

## 🧩 Dlaczego to działa

| Element | Rola |
|-------|------|
| Skrypt Pythona | Wykonuje pracę AI, zapisuje plik |
| Harmonogram zadań | Uruchamia go według harmonogramu |
| Działa jako Twój użytkownik | Może odczytać `OPENAI_API_KEY` |
| Zapisuje do pliku | Dostajesz wynik bez patrzenia |

---

## ✅ Sprawdzenie

- [ ] `daily_brief.py` działa ręcznie i zapisuje datowany plik.
- [ ] Utworzyłeś zaplanowane zadanie.
- [ ] `schtasks /run` wygenerował świeży brief bez rąk.

---

## 🎯 Zadanie

Zmień `TOPIC` na coś, co Cię obchodzi, i ustaw godzinę, którą zauważysz. Pozwól działać kilka dni — przedsmak AI pracującej dla Ciebie na autopilocie.

---

## 💡 Najważniejsze wnioski

- **Harmonogram zadań** uruchamia skrypty automatycznie, bez rąk.
- Podaj **pełną ścieżkę** do `python.exe` i do skryptu.
- Zadania działają jako Twój użytkownik, więc odczytują klucz API ze środowiska.
- Testuj przez `schtasks /run`.

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)
