# C2 — Zbuduj potok

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `google-genai` + klucz API

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wielo-plikowe →](03-projekty-wieloplikowe.md)

---

## 🧠 Teoria (3 min)

**Potok (pipeline)** łączy kroki tak, że dane przepływają automatycznie:

```
wczytaj wejście  →  zapytaj Gemini  →  zapisz wyjście
```

Moc bierze się z robienia tego **wsadowo** — na wielu plikach — w pętli. Zamiast wklejać do aplikacji 20 razy, skrypt przetwarza 20 plików, gdy Ty pijesz kawę.

Zbudujemy **wsadowy streszczacz**: wrzucasz pliki `.txt`, uruchamiasz jedną komendę, dostajesz `.summary.md` dla każdego.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Utwórz folder wejściowy z kilkoma plikami

```powershell
mkdir $HOME\pipeline-in
"Dlugie notatki... start w marcu, budzet 5000, Sara odpowiada za design." | Out-File $HOME\pipeline-in\spotkanie1.txt
"Notatki z rozmowy: klient chce odswiezenie logo, termin koniec miesiaca, 3 koncepcje." | Out-File $HOME\pipeline-in\rozmowa2.txt
```

### Krok 2 — Napisz potok

Utwórz `summarize_folder.py`:

```python
from google import genai
from pathlib import Path

client = genai.Client()

IN_DIR = Path.home() / "pipeline-in"
OUT_DIR = Path.home() / "pipeline-out"
OUT_DIR.mkdir(exist_ok=True)

def summarize(text):
    resp = client.models.generate_content(
        model="gemini-2.5-flash",
        contents=(
            "Streść poniższe notatki w 3 punktach, potem wypisz wszelkie "
            "daty, nazwiska lub kwoty w linii zaczynającej się 'Kluczowe fakty:'.\n\n" + text
        ),
    )
    return resp.text

txt_files = sorted(IN_DIR.glob("*.txt"))
print(f"Znaleziono {len(txt_files)} plik(ów).")

for f in txt_files:
    print(f"Przetwarzam {f.name} ...")
    summary = summarize(f.read_text(encoding="utf-8"))
    (OUT_DIR / (f.stem + ".summary.md")).write_text(summary, encoding="utf-8")

print(f"Gotowe. Streszczenia są w {OUT_DIR}")
```

### Krok 3 — Uruchom potok

```powershell
cd $HOME\learn-ai-gemini
python summarize_folder.py
```

Otwórz `C:\Users\TwojaNazwa\pipeline-out\` — jedno streszczenie na plik. 🎉

### Krok 4 — Dodaj drugi etap (łączenie)

Dopisz to, aby połączyć streszczenia w przegląd:

```python
all_summaries = "\n\n---\n\n".join(
    p.read_text(encoding="utf-8") for p in sorted(OUT_DIR.glob("*.summary.md"))
)

resp = client.models.generate_content(
    model="gemini-2.5-pro",
    contents="Połącz te streszczenia w jeden krótki przegląd z 3 "
             "najważniejszymi priorytetami ze wszystkich:\n\n" + all_summaries,
)
(OUT_DIR / "DIGEST.md").write_text(resp.text, encoding="utf-8")
print("Zapisano DIGEST.md")
```

Teraz przepływ to: **wczytaj wiele plików → streść każdy → połącz w przegląd** — prawdziwy wieloetapowy potok.

### Krok 5 — Zautomatyzuj to (połącz z C1)

Zaplanuj `summarize_folder.py` w Harmonogramie zadań (C1), aby działał każdego wieczoru. Wrzucaj notatki w ciągu dnia; budź się do streszczeń i przeglądu.

---

## 🧩 Wzorzec potoku

| Etap | Kod |
|-------|------|
| Wczytaj wejścia | `Path.glob("*.txt")` + `read_text()` |
| Przetwórz każde | funkcja wywołująca Gemini |
| Zapisz wyjścia | `write_text()` do folderu wyjściowego |
| (Opcjonalnie) połącz | jeszcze jedno wywołanie Gemini po wynikach |

> ⚠️ **Koszt i bezpieczeństwo:** zadania wsadowe wykonują wiele wywołań API — zacznij od kilku plików i `gemini-2.5-flash` (darmowy poziom). Nigdy nie kieruj potoku na folder z sekretami lub danymi prywatnymi.

---

## ✅ Sprawdzenie

- [ ] `summarize_folder.py` wyprodukował jedno streszczenie na plik.
- [ ] Dodałeś drugi etap zapisujący `DIGEST.md`.
- [ ] Rozumiesz wczytaj → przetwórz → zapisz (→ połącz).

---

## 🎯 Zadanie

Dostosuj potok do własnego folderu — starych notatek, artykułów. Streść wsadowo, potem zaplanuj (C1), aby nowe pliki były przetwarzane automatycznie.

---

## 💡 Najważniejsze wnioski

- Potok = **wczytaj → zapytaj Gemini → zapisz**, w pętli po wielu elementach.
- Łącz etapy (streść każdy → połącz) dla wieloetapowej automatyzacji.
- Połącz z Harmonogramem zadań (C1) dla przetwarzania wsadowego bez rąk.
- Zaczynaj mało na darmowym poziomie; nigdy nie przetwarzaj danych prywatnych.

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wielo-plikowe →](03-projekty-wieloplikowe.md)
