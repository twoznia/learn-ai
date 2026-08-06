# C2 — Zbuduj potok (pipeline)

⏱️ **15 minut** · Ścieżka: 🅲 Automatyzator · Potrzebne: Python + `openai` + klucz API

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wieloplikowe →](03-projekty-wieloplikowe.md)

---

## 🧠 Teoria (3 min)

**Potok** łączy kroki tak, by dane płynęły automatycznie:

```
wczytaj wejście  →  zapytaj GPT  →  zapisz wyjście
```

Moc bierze się z robienia tego **wsadowo** — na wielu plikach — w pętli. Zamiast wklejać do aplikacji 20 razy, skrypt przetwarza 20 plików, gdy Ty robisz kawę.

Zbudujemy **wsadowy streszczacz**: wrzucasz pliki `.txt` do folderu, uruchamiasz jedno polecenie, dostajesz `.summary.md` dla każdego.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zrób folder wejściowy z kilkoma plikami

```powershell
mkdir $HOME\pipeline-in
"Długie notatki ze spotkania... start w marcu, budżet 5000, Sara odpowiada za projekt." | Out-File $HOME\pipeline-in\meeting1.txt
"Notatki z rozmowy: klient chce odświeżenia logo, termin koniec miesiąca, potrzebne 3 koncepcje." | Out-File $HOME\pipeline-in\call2.txt
```

### Krok 2 — Napisz potok

Utwórz `summarize_folder.py`:

```python
from openai import OpenAI
from pathlib import Path

client = OpenAI()

IN_DIR = Path.home() / "pipeline-in"
OUT_DIR = Path.home() / "pipeline-out"
OUT_DIR.mkdir(exist_ok=True)

def summarize(text):
    resp = client.chat.completions.create(
        model="gpt-5-mini",
        messages=[{
            "role": "user",
            "content": (
                "Streść poniższe notatki w 3 punktach, potem wypisz wszelkie "
                "daty, nazwiska lub kwoty w linii zaczynającej się 'Kluczowe fakty:'.\n\n" + text
            ),
        }],
    )
    return resp.choices[0].message.content

txt_files = sorted(IN_DIR.glob("*.txt"))
print(f"Znaleziono {len(txt_files)} plik(ów).")

for f in txt_files:
    print(f"Przetwarzam {f.name} ...")
    summary = summarize(f.read_text(encoding="utf-8"))
    (OUT_DIR / (f.stem + ".summary.md")).write_text(summary, encoding="utf-8")

print(f"Gotowe. Streszczenia są w {OUT_DIR}")
```

### Krok 3 — Uruchom

```powershell
cd $HOME\learn-ai-gpt
python summarize_folder.py
```

Otwórz `C:\Users\TwojaNazwa\pipeline-out\` — jedno streszczenie na plik wejściowy. 🎉

### Krok 4 — Dodaj drugi etap (łańcuch)

Dopisz to, aby połączyć wszystkie streszczenia w jeden przegląd:

```python
all_summaries = "\n\n---\n\n".join(
    p.read_text(encoding="utf-8") for p in sorted(OUT_DIR.glob("*.summary.md"))
)

resp = client.chat.completions.create(
    model="gpt-5",
    messages=[{
        "role": "user",
        "content": "Połącz te streszczenia w jeden krótki przegląd z 3 "
                   "najważniejszymi priorytetami ze wszystkich:\n\n" + all_summaries,
    }],
)
(OUT_DIR / "DIGEST.md").write_text(resp.choices[0].message.content, encoding="utf-8")
print("Zapisano DIGEST.md")
```

Teraz przepływ to: **wczytaj wiele plików → streść każdy → połącz w jeden przegląd** — prawdziwy wieloetapowy potok.

### Krok 5 — Zautomatyzuj (połącz z C1)

Zaplanuj `summarize_folder.py` w Harmonogramie zadań (C1), by działał każdego wieczoru. Wrzucaj notatki do `pipeline-in` w ciągu dnia; budź się do streszczeń i przeglądu.

---

## 🧩 Wzorzec potoku

| Etap | Kod |
|-------|------|
| Wczytaj wejścia | `Path.glob("*.txt")` + `read_text()` |
| Przetwórz każde | funkcja wywołująca GPT |
| Zapisz wyjścia | `write_text()` do folderu wyjściowego |
| (Opcjonalnie) połącz | jeszcze jedno wywołanie GPT po wszystkich wynikach |

> ⚠️ **Koszt i bezpieczeństwo:** zadania wsadowe robią wiele wywołań API — zacznij od kilku plików i `gpt-5-mini`. Nigdy nie kieruj potoku na folder z sekretami lub prywatnymi danymi.

---

## ✅ Sprawdzenie

- [ ] `summarize_folder.py` wygenerował jedno streszczenie na plik.
- [ ] Dodałeś drugi etap, który zapisał `DIGEST.md`.
- [ ] Rozumiesz: wczytaj → przetwórz → zapisz (→ połącz).

---

## 🎯 Zadanie

Dostosuj potok do prawdziwego folderu — stare notatki, zapisane artykuły. Streść wsadowo, potem zaplanuj (C1), aby nowe pliki były przetwarzane automatycznie.

---

## 💡 Najważniejsze wnioski

- Potok = **wczytaj → zapytaj GPT → zapisz**, w pętli po wielu elementach.
- Łącz etapy (streść każdy → połącz) dla wieloetapowej automatyzacji.
- Połącz z Harmonogramem zadań (C1) dla wsadowego przetwarzania bez rąk.
- Zaczynaj mało i tanio; nigdy nie przetwarzaj wsadowo prywatnych danych.

🌐 [English](../../en/track-c/02-pipelines.md) · [← Wstecz](01-harmonogram-zadan.md) · [Indeks ścieżki](../README.md) · [Dalej: Projekty wieloplikowe →](03-projekty-wieloplikowe.md)
