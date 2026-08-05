# Lekcja 14 — Zbuduj mini projekt: asystent notatek AI

⏱️ **10 minut** (plus opcjonalne majsterkowanie) · Poziom: Początkujący · Potrzebne: Python + klucz API

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-gemini-cli.md) · [Strona kursu](../README.md) · [Dalej: Grounding →](15-grounding-google-search.md)

---

## 🧠 Teoria (2 min)

Czas zbudować coś, co zachowasz: **asystenta notatek w wierszu poleceń**. Piszesz chaotyczne notatki; Gemini je porządkuje, streszcza i wyciąga punkty do działania. Łączy to Lekcje 8–10.

Nowa koncepcja: **instrukcja systemowa**. To stała zasada, która kształtuje zachowanie Gemini dla całego zapytania — jak Gemy z Lekcji 7, ale w kodzie.

---

## 🛠️ Zbuduj to (7 min)

### Krok 1 — Utwórz plik

```powershell
cd $HOME\learn-ai-gemini
notepad notes_assistant.py
```

### Krok 2 — Wklej ten kompletny program i zapisz

```python
from google import genai
from google.genai import types
import sys

client = genai.Client()

# "Instrukcja systemowa" ustala rolę i zasady Gemini dla całego zapytania.
SYSTEM = """Jesteś schludnym asystentem notatek.
Na podstawie chaotycznych notatek zawsze odpowiadasz dokładnie trzema sekcjami:

## Czyste podsumowanie
(2-4 jasne zdania)

## Kluczowe punkty
(lista najważniejszych faktów)

## Zadania do zrobienia
(lista kontrolna zadań; napisz 'Brak', jeśli nie ma zadań)

Bądź zwięzły i przyjazny. Jeśli coś jest niejasne, zaznacz to krótko."""

print("Wklej poniżej swoje chaotyczne notatki. Naciśnij Enter, potem Ctrl+Z i Enter, aby zakończyć:\n")

notes = sys.stdin.read()

if not notes.strip():
    print("Brak notatek. Kończę.")
    raise SystemExit

response = client.models.generate_content(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(system_instruction=SYSTEM),
    contents=notes,
)

print("\n" + "=" * 50 + "\n")
print(response.text)
```

### Krok 3 — Uruchom go

```powershell
python notes_assistant.py
```

Potem wklej chaotyczne notatki, na przykład:

```text
spotkanie z sam we wtorek. rozmawialismy o nowej stronie. sam przysle pliki logo do piatku. musimy wybrac kolory. budzet moze 2000. start miejmy nadzieje w przyszlym miesiacu. powinienem napisac do drukarni w sprawie wizytowek
```

Aby zakończyć wprowadzanie na Windows: naciśnij **Enter**, potem **Ctrl+Z**, potem **Enter**.

Gemini zwraca czyste podsumowanie, kluczowe punkty i listę kontrolną. ✅

---

## 🧩 Czego się właśnie nauczyłeś

| Funkcja | Dlaczego ważna |
|---------|----------------|
| **Instrukcja systemowa** (`system_instruction`) | Ustala rolę i format wyjścia raz, niezawodnie |
| **Ustrukturyzowane wyjście** (trzy sekcje `##`) | Przewidywalny, wielokrotnego użytku format |
| **Odczyt wieloliniowy** (`sys.stdin.read()`) | Obsłuż prawdziwe akapity, nie jedną linię |

---

## 🚀 Uczyń go swoim (opcjonalnie, użyj Gemini CLI!)

Otwórz ten projekt w **Gemini CLI** (Lekcja 13) i poproś o ulepszenia prostym językiem:

```text
Zmień notes_assistant.py tak, aby czytał notatki z pliku notes.txt zamiast wklejania.
```
```text
Zapisz wynik Gemini do pliku summary.md z dzisiejszą datą w nazwie pliku.
```
```text
Dodaj przyjazny komunikat błędu, jeśli brakuje klucza API.
```

Niech AI zbuduje funkcje — Ty przeglądasz i zatwierdzasz.

---

## ✅ Sprawdzenie

- [ ] `notes_assistant.py` działa i zwraca 3 sekcje.
- [ ] Rozumiesz, co robi `system_instruction`.
- [ ] (Bonus) Dodałeś co najmniej jedną funkcję przez Gemini CLI.

---

## 🎯 Zadanie

Użyj swojego asystenta notatek na czymś realnym w tym tygodniu — spotkaniu, wykładzie, wyrzucie myśli. Zauważ, o ile szybciej to idzie niż porządkowanie ręcznie.

---

## 💡 Najważniejsze wnioski

- **Instrukcja systemowa** niezawodnie kształtuje rolę i format wyjścia Gemini.
- Prośba o stałą strukturę (sekcje/listy) czyni wyniki wielokrotnego użytku.
- Mały skrypt możesz rozwinąć w prawdziwe narzędzie, opisując funkcje Gemini CLI.

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-gemini-cli.md) · [Strona kursu](../README.md) · [Dalej: Grounding →](15-grounding-google-search.md)
