# C2 — Zbuduj potok

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `anthropic` + klucz API

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wielo-plikowe →](03-projekty-wieloplikowe.md)

---

## 🧠 Teoria (3 min)

**Potok (pipeline)** łączy kroki tak, że dane przepływają przez nie automatycznie:

```
wczytaj wejście  →  zapytaj Claude  →  zapisz wyjście
```

Moc bierze się z robienia tego **wsadowo** — na wielu plikach, wierszach czy elementach — w pętli. Zamiast wklejać do czatu 20 razy, Twój skrypt przetwarza 20 plików, gdy Ty pijesz kawę.

Zbudujemy **wsadowy streszczacz**: wrzucasz pliki `.txt` do folderu, uruchamiasz jedną komendę i dostajesz `.summary.md` dla każdego.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Utwórz folder wejściowy z kilkoma plikami

```powershell
mkdir $HOME\pipeline-in
"Dlugie notatki ze spotkania... zdecydowalismy start w marcu, budzet 5000, Sara odpowiada za design." | Out-File $HOME\pipeline-in\spotkanie1.txt
"Notatki z rozmowy: klient chce odswiezenie logo, termin koniec miesiaca, potrzebne 3 koncepcje." | Out-File $HOME\pipeline-in\rozmowa2.txt
```

### Krok 2 — Napisz potok

W folderze kursu utwórz `summarize_folder.py`:

```python
import anthropic
from pathlib import Path

client = anthropic.Anthropic()

IN_DIR = Path.home() / "pipeline-in"
OUT_DIR = Path.home() / "pipeline-out"
OUT_DIR.mkdir(exist_ok=True)

def summarize(text):
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=400,
        messages=[{
            "role": "user",
            "content": (
                "Streść poniższe notatki w 3 punktach, potem wypisz wszelkie "
                "daty, nazwiska lub kwoty w linii zaczynającej się 'Kluczowe fakty:'.\n\n" + text
            ),
        }],
    )
    return resp.content[0].text

# Potok: pętla po każdym pliku .txt
txt_files = sorted(IN_DIR.glob("*.txt"))
print(f"Znaleziono {len(txt_files)} plik(ów).")

for f in txt_files:
    print(f"Przetwarzam {f.name} ...")
    text = f.read_text(encoding="utf-8")
    summary = summarize(text)
    out_file = OUT_DIR / (f.stem + ".summary.md")
    out_file.write_text(summary, encoding="utf-8")

print(f"Gotowe. Streszczenia są w {OUT_DIR}")
```

### Krok 3 — Uruchom potok

```powershell
cd $HOME\learn-ai-claude
python summarize_folder.py
```

Otwórz `C:\Users\TwojaNazwa\pipeline-out\` — jedno streszczenie na plik wejściowy. Właśnie przetworzyłeś cały folder jedną komendą. 🎉

### Krok 4 — Dodaj krok (łączenie daje moc)

Potoki błyszczą, gdy **łączysz** kroki. Dodajmy drugi etap łączący wszystkie streszczenia w jeden przegląd. Dopisz to do skryptu (lub zrób `digest.py`):

```python
# Drugi etap: połącz wszystkie streszczenia w jeden przegląd
all_summaries = "\n\n---\n\n".join(
    p.read_text(encoding="utf-8") for p in sorted(OUT_DIR.glob("*.summary.md"))
)

resp = client.messages.create(
    model="claude-sonnet-5",
    max_tokens=500,
    messages=[{
        "role": "user",
        "content": "Połącz te streszczenia w jeden krótki przegląd z 3 "
                   "najważniejszymi priorytetami ze wszystkich:\n\n" + all_summaries,
    }],
)
(OUT_DIR / "DIGEST.md").write_text(resp.content[0].text, encoding="utf-8")
print("Zapisano DIGEST.md")
```

Teraz przepływ to: **wczytaj wiele plików → streść każdy → połącz w jeden przegląd**. To prawdziwy wieloetapowy potok.

### Krok 5 — Zautomatyzuj to (połącz z C1)

Zaplanuj `summarize_folder.py` w Harmonogramie zadań (Lekcja C1), aby działał każdego wieczoru. Wrzucaj notatki do `pipeline-in` w ciągu dnia; budź się do streszczeń i przeglądu. Automatyzacja + potok = dźwignia.

---

## 🧩 Wzorzec potoku

| Etap | Kod |
|-------|------|
| Wczytaj wejścia | `Path.glob("*.txt")` + `read_text()` |
| Przetwórz każde | funkcja wywołująca Claude |
| Zapisz wyjścia | `write_text()` do folderu wyjściowego |
| (Opcjonalnie) połącz | jeszcze jedno wywołanie Claude po wszystkich wynikach |

> ⚠️ **Koszt i bezpieczeństwo:** zadania wsadowe wykonują wiele wywołań API — zacznij od kilku plików i taniego modelu (`claude-haiku-4-5`). Nigdy nie kieruj potoku na folder z sekretami lub danymi prywatnymi.

---

## ✅ Sprawdzenie

- [ ] `summarize_folder.py` wyprodukował jedno streszczenie na plik wejściowy.
- [ ] Dodałeś drugi etap zapisujący `DIGEST.md`.
- [ ] Rozumiesz wczytaj → przetwórz → zapisz (→ połącz).

---

## 🎯 Zadanie

Dostosuj potok do własnego folderu — starych notatek, zapisanych artykułów, wyeksportowanych czatów. Streść je wsadowo. Potem zaplanuj to (C1), aby nowe pliki były przetwarzane automatycznie.

---

## 💡 Najważniejsze wnioski

- Potok = **wczytaj → zapytaj Claude → zapisz**, w pętli po wielu elementach.
- Łącz etapy (streść każdy → połącz) dla wieloetapowej automatyzacji.
- Połącz z Harmonogramem zadań (C1) dla przetwarzania wsadowego bez rąk.
- Zaczynaj mało i tanio; nigdy nie przetwarzaj wsadowo danych prywatnych/sekretów.

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wielo-plikowe →](03-projekty-wieloplikowe.md)
