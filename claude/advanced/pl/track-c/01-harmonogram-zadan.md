# C1 — Harmonogram zadań (Task Scheduler)

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `anthropic` + klucz API (kurs podstawowy)

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)

---

## 🧠 Teoria (3 min)

Automatyzacja oznacza, że komputer wykonuje pracę **bez uruchamiania jej przez Ciebie**. Windows ma do tego wbudowane narzędzie: **Harmonogram zadań (Task Scheduler)**. Potrafi uruchamiać program według harmonogramu — co rano, co godzinę, przy logowaniu.

Nasz plan: napisać mały skrypt Pythona, który prosi Claude o coś użytecznego (codzienny brief), a potem sprawić, by Harmonogram zadań uruchamiał go **automatycznie każdego ranka** i zapisywał wynik do pliku. Budzisz się, a brief już jest.

Ważny szczegół: zaplanowane zadanie działa **jako Twój użytkownik Windows**, więc może odczytać `ANTHROPIC_API_KEY` ustawiony przez `setx`. Dlatego w kursie podstawowym zapisaliśmy klucz jako zmienną środowiskową użytkownika.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Napisz skrypt „codzienny brief”

W folderze kursu utwórz `daily_brief.py`:

```python
import anthropic
from datetime import date
from pathlib import Path

client = anthropic.Anthropic()

# O czym chcesz brief. Edytuj swobodnie.
TOPIC = "produktywność i skupienie"

resp = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{
        "role": "user",
        "content": (
            f"Napisz mi krótki codzienny brief o: {TOPIC}: "
            "jedna motywująca myśl, jedna praktyczna wskazówka na dziś "
            "i jedno pytanie do refleksji. Zmieść się w 150 słowach."
        ),
    }],
)
text = resp.content[0].text

# Zapisz do datowanego pliku w folderze 'daily-briefs'
out_dir = Path.home() / "daily-briefs"
out_dir.mkdir(exist_ok=True)
out_file = out_dir / f"brief-{date.today().isoformat()}.md"
out_file.write_text(text, encoding="utf-8")

print(f"Zapisano: {out_file}")
```

### Krok 2 — Uruchom raz ręcznie

```powershell
cd $HOME\learn-ai-claude
python daily_brief.py
```

Sprawdź, czy pojawił się plik w `C:\Users\TwojaNazwa\daily-briefs\`. Jeśli tak, gotowe do automatyzacji.

### Krok 3 — Znajdź ścieżkę do Pythona

Harmonogram zadań potrzebuje **pełnej ścieżki** do Pythona. Pobierz ją:

```powershell
(Get-Command python).Source
```

Skopiuj wypisaną ścieżkę (np. `C:\Users\TwojaNazwa\AppData\Local\Programs\Python\Python312\python.exe`).

### Krok 4 — Utwórz zaplanowane zadanie (szybko: `schtasks`)

W PowerShell uruchom to — zamień dwie ścieżki na **swoją** ścieżkę Pythona i ścieżkę skryptu:

```powershell
schtasks /create /tn "DailyBrief" `
  /tr "'C:\Sciezka\Do\python.exe' 'C:\Users\TwojaNazwa\learn-ai-claude\daily_brief.py'" `
  /sc daily /st 08:00
```

- `/tn` = nazwa zadania, `/tr` = co uruchomić, `/sc daily` = harmonogram, `/st 08:00` = godzina 8:00.

### Krok 5 — Przetestuj zadanie bez czekania do rana

```powershell
schtasks /run /tn "DailyBrief"
```

Sprawdź folder `daily-briefs` w poszukiwaniu świeżego pliku. 🎉 Działa bez nadzoru.

> **Wolisz klikać?** Otwórz **Harmonogram zadań** (Start → wpisz) → **Utwórz zadanie podstawowe** → nazwij → **Codziennie** → ustaw godzinę → **Uruchom program** → Program = Twój `python.exe`, Dodaj argumenty = ścieżka skryptu. Ten sam efekt, z kreatorem.

### Krok 6 — Zarządzaj nim

```powershell
schtasks /query /tn "DailyBrief"     # zobacz status
schtasks /delete /tn "DailyBrief" /f  # usuń, gdy skończysz eksperymenty
```

---

## 🧩 Dlaczego to działa

| Element | Rola |
|-------|------|
| Skrypt Pythona | Wykonuje pracę AI i zapisuje plik |
| Harmonogram zadań | Uruchamia skrypt według harmonogramu |
| Działa jako Twój użytkownik | Może odczytać Twój `ANTHROPIC_API_KEY` |
| Zapisuje do pliku | Dostajesz wynik bez patrzenia |

---

## ✅ Sprawdzenie

- [ ] `daily_brief.py` działa ręcznie i zapisuje datowany plik.
- [ ] Utworzyłeś zaplanowane zadanie (schtasks lub kreator).
- [ ] `schtasks /run` wyprodukował świeży brief bez wpisywania czegokolwiek.

---

## 🎯 Zadanie

Zmień `TOPIC` na coś, co naprawdę Cię obchodzi, i ustaw harmonogram na godzinę, którą zauważysz (np. tuż przed rozpoczęciem pracy). Pozwól temu działać kilka dni — mały przedsmak AI pracującego dla Ciebie na autopilocie.

---

## 💡 Najważniejsze wnioski

- **Harmonogram zadań** uruchamia skrypty automatycznie, bez udziału rąk.
- Podaj mu **pełną ścieżkę** do `python.exe` i do skryptu.
- Zadania działają jako Twój użytkownik, więc mogą odczytać klucz API ze środowiska.
- Testuj przez `schtasks /run` zamiast czekać na zaplanowaną godzinę.

🌐 [English](../../en/track-c/01-schedule-with-task-scheduler.md) · [← Indeks ścieżki](../README.md) · [Dalej: Zbuduj potok →](02-potoki.md)
