# Lekcja 14 — Zbuduj mini projekt: asystent notatek AI

⏱️ **10 minut** (plus opcjonalne majsterkowanie) · Poziom: Początkujący · Potrzebne: Python + klucz API

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-codex-cli.md) · [Strona kursu](../README.md) · [Dalej: Wyszukiwanie w sieci →](15-wyszukiwanie-web.md)

---

## 🧠 Teoria (2 min)

Czas zbudować coś, co zachowasz: **asystenta notatek w wierszu poleceń**. Piszesz chaotyczne notatki; GPT je porządkuje, streszcza i wyciąga punkty do działania. Łączy to Lekcje 8–10.

Nowa koncepcja: **prompt systemowy**. To stała instrukcja, która kształtuje zachowanie GPT dla całego zapytania — jak instrukcje własne z Lekcji 7, ale w kodzie (wiadomość `{"role": "system", ...}`).

---

## 🛠️ Zbuduj to (7 min)

### Krok 1 — Utwórz plik

```powershell
cd $HOME\learn-ai-gpt
notepad notes_assistant.py
```

### Krok 2 — Wklej ten kompletny program i zapisz

```python
from openai import OpenAI
import sys

client = OpenAI()

# "Prompt systemowy" ustala rolę i zasady GPT dla całego zapytania.
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

response = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[
        {"role": "system", "content": SYSTEM},
        {"role": "user", "content": notes},
    ],
)

print("\n" + "=" * 50 + "\n")
print(response.choices[0].message.content)
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

GPT zwraca czyste podsumowanie, kluczowe punkty i listę kontrolną. ✅

---

## 🧩 Czego się właśnie nauczyłeś

| Funkcja | Dlaczego ważna |
|---------|----------------|
| **Prompt systemowy** (`role: "system"`) | Ustala rolę i format wyjścia raz, niezawodnie |
| **Ustrukturyzowane wyjście** (trzy sekcje `##`) | Przewidywalny, wielokrotnego użytku format |
| **Odczyt wieloliniowy** (`sys.stdin.read()`) | Obsłuż prawdziwe akapity, nie jedną linię |

---

## 🚀 Uczyń go swoim (opcjonalnie, użyj Codex!)

Otwórz ten projekt w **Codex CLI** (Lekcja 13) i poproś o ulepszenia prostym językiem:

```text
Zmień notes_assistant.py tak, aby czytał notatki z pliku notes.txt zamiast wklejania.
```
```text
Zapisz wynik GPT do pliku summary.md z dzisiejszą datą w nazwie pliku.
```
```text
Dodaj przyjazny komunikat błędu, jeśli brakuje klucza API.
```

Niech AI zbuduje funkcje — Ty przeglądasz i zatwierdzasz.

---

## ✅ Sprawdzenie

- [ ] `notes_assistant.py` działa i zwraca 3 sekcje.
- [ ] Rozumiesz, co robi wiadomość `system`.
- [ ] (Bonus) Dodałeś co najmniej jedną funkcję przez Codex.

---

## 🎯 Zadanie

Użyj swojego asystenta notatek na czymś realnym w tym tygodniu — spotkaniu, wykładzie, wyrzucie myśli. Zauważ, o ile szybciej to idzie niż porządkowanie ręcznie.

---

## 💡 Najważniejsze wnioski

- **Prompt systemowy** niezawodnie kształtuje rolę i format wyjścia GPT.
- Prośba o stałą strukturę (sekcje/listy) czyni wyniki wielokrotnego użytku.
- Mały skrypt możesz rozwinąć w prawdziwe narzędzie, opisując funkcje Codex.

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-codex-cli.md) · [Strona kursu](../README.md) · [Dalej: Wyszukiwanie w sieci →](15-wyszukiwanie-web.md)
