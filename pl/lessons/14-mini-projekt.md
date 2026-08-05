# Lekcja 14 — Zbuduj mini projekt: asystent notatek AI

⏱️ **10 minut** (plus opcjonalne majsterkowanie) · Poziom: Początkujący · Potrzebne: Python + klucz API

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-claude-code-cli.md) · [Strona kursu](../README.md) · [Dalej: MCP →](15-mcp.md)

---

## 🧠 Teoria (2 min)

Czas zbudować coś, co naprawdę zachowasz: **asystenta notatek w wierszu poleceń**. Piszesz chaotyczne notatki; Claude je porządkuje, streszcza i wyciąga punkty do działania. Łączy to wszystko z Lekcji 8–10.

Nowa koncepcja: **prompt systemowy**. To stała instrukcja, która kształtuje zachowanie Claude dla całego zapytania — jak „instrukcje własne” z Lekcji 7, ale w kodzie.

---

## 🛠️ Zbuduj to (7 min)

### Krok 1 — Utwórz plik

```powershell
cd $HOME\learn-ai-claude
notepad notes_assistant.py
```

### Krok 2 — Wklej ten kompletny program i zapisz

```python
import anthropic

client = anthropic.Anthropic()

# "Prompt systemowy" ustala rolę i zasady Claude dla całej rozmowy.
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

# Odczytaj wszystko, co wpisze użytkownik, aż zasygnalizuje koniec wprowadzania
import sys
notes = sys.stdin.read()

if not notes.strip():
    print("Brak notatek. Kończę.")
    raise SystemExit

response = client.messages.create(
    model="claude-sonnet-5",
    max_tokens=800,
    system=SYSTEM,
    messages=[
        {"role": "user", "content": notes}
    ],
)

print("\n" + "=" * 50 + "\n")
for block in response.content:
    if block.type == "text":
        print(block.text)
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

Claude zwraca czyste podsumowanie, kluczowe punkty i listę kontrolną. ✅

---

## 🧩 Czego się właśnie nauczyłeś

| Funkcja | Dlaczego ważna |
|---------|----------------|
| **Prompt systemowy** (`system=`) | Ustala rolę i format wyjścia raz, niezawodnie |
| **Ustrukturyzowane wyjście** (trzy sekcje `##`) | Przewidywalny, wielokrotnego użytku format |
| **Odczyt wieloliniowy** (`sys.stdin.read()`) | Obsłuż prawdziwe akapity, nie jedną linię |

---

## 🚀 Uczyń go swoim (opcjonalnie, użyj Claude Code!)

Otwórz ten projekt w **Claude Code** (Lekcja 13) i poproś o ulepszenia prostym językiem:

```text
Zmień notes_assistant.py tak, aby czytał notatki z pliku notes.txt zamiast wklejania.
```

```text
Zapisz wynik Claude do pliku summary.md z dzisiejszą datą w nazwie pliku.
```

```text
Dodaj przyjazny komunikat błędu, jeśli brakuje klucza API.
```

Niech AI zbuduje funkcje — Ty przeglądasz i zatwierdzasz. Dokładnie tak pracują dziś prawdziwi programiści.

---

## ✅ Sprawdzenie

- [ ] `notes_assistant.py` działa i zwraca 3 sekcje.
- [ ] Rozumiesz, co robi prompt `system`.
- [ ] (Bonus) Dodałeś co najmniej jedną funkcję przez Claude Code.

---

## 🎯 Zadanie

Użyj swojego asystenta notatek na czymś realnym w tym tygodniu — spotkaniu, wykładzie, wyrzucie myśli. Zauważ, o ile szybciej to idzie niż porządkowanie ręcznie.

---

## 💡 Najważniejsze wnioski

- **Prompt systemowy** niezawodnie kształtuje rolę i format wyjścia Claude.
- Prośba o stałą strukturę (sekcje/listy) czyni wyniki wielokrotnego użytku.
- Mały skrypt możesz rozwinąć w prawdziwe narzędzie, opisując funkcje Claude Code.

🌐 [English](../../en/lessons/14-mini-project.md) · [← Wstecz](13-claude-code-cli.md) · [Strona kursu](../README.md) · [Dalej: MCP →](15-mcp.md)
