# Lekcja 10 — Twój pierwszy skrypt w Pythonie z Claude

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Python (L8), ustawiony klucz API (L9)

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)

---

## 🧠 Teoria (2 min)

Teraz zrobisz **własny program**, który rozmawia z Claude. Kroki są zawsze te same:

1. **Zainstaluj** oficjalną bibliotekę (`anthropic`).
2. **Utwórz klienta** (odczytuje Twój `ANTHROPIC_API_KEY` automatycznie).
3. **Wyślij wiadomość** i wypisz odpowiedź.

Użyjemy **Claude Haiku** — najszybszego, najtańszego modelu — więc nauka kosztuje ułamek grosza. Identyfikatory modeli, których możesz użyć:

| Model | ID (skopiuj dokładnie) | Dobry do |
|-------|-------------------|----------|
| Haiku (najtańszy) | `claude-haiku-4-5` | Nauka, proste zadania |
| Sonnet (zrównoważony) | `claude-sonnet-5` | Codzienna praca |
| Opus (najmądrzejszy) | `claude-opus-5` | Trudne rozumowanie/kodowanie |

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj bibliotekę

Otwórz **PowerShell** i przejdź do folderu kursu:

```powershell
cd $HOME\learn-ai-claude
pip install anthropic
```

Zobaczysz pobieranie i instalację. Zajmuje ~30 sekund.

### Krok 2 — Utwórz skrypt

Utworzymy plik `first_claude.py`. Uruchom to, aby stworzyć go w Notatniku:

```powershell
notepad first_claude.py
```

Kliknij **Tak**, aby go utworzyć, potem **wklej to** i zapisz (Ctrl+S):

```python
import anthropic

# Klient automatycznie odczytuje zmienną środowiskową ANTHROPIC_API_KEY
client = anthropic.Anthropic()

# Wyślij jedną wiadomość do Claude
response = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=300,
    messages=[
        {"role": "user", "content": "Przywitaj się i podaj jeden ciekawy fakt o Księżycu."}
    ],
)

# Odpowiedź wraca w "blokach treści" — wypisz tekst
for block in response.content:
    if block.type == "text":
        print(block.text)
```

### Krok 3 — Uruchom go

Z powrotem w PowerShell:

```powershell
python first_claude.py
```

🎉 Powinieneś zobaczyć powitanie Claude i fakt o Księżycu. **Właśnie zbudowałeś aplikację AI.**

### Krok 4 — Zrób go interaktywnym

Sprawmy, by pytał *Ciebie*. Utwórz `chat_once.py`:

```powershell
notepad chat_once.py
```

Wklej i zapisz:

```python
import anthropic

client = anthropic.Anthropic()

# Zapytaj użytkownika o wpis
question = input("Zapytaj Claude o cokolwiek: ")

response = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=500,
    messages=[
        {"role": "user", "content": question}
    ],
)

for block in response.content:
    if block.type == "text":
        print("\nClaude mówi:\n" + block.text)
```

Uruchom:

```powershell
python chat_once.py
```

Wpisz pytanie, naciśnij Enter, a Claude odpowie. 🙌

---

## 🧩 Zrozumienie kodu (1 min)

| Linia | Co robi |
|------|--------------|
| `import anthropic` | Ładuje bibliotekę |
| `anthropic.Anthropic()` | Łączy się przy użyciu Twojego klucza |
| `model="claude-haiku-4-5"` | Wybiera, którego Claude użyć |
| `max_tokens=300` | Ogranicza długość odpowiedzi (kontrola kosztów) |
| `messages=[{"role": "user", ...}]` | Twój prompt |
| `for block in response.content` | Odczytuje odpowiedź (to lista bloków) |

---

## ✅ Sprawdzenie

- [ ] `pip install anthropic` się powiodło.
- [ ] `first_claude.py` wypisał odpowiedź.
- [ ] `chat_once.py` odpowiedział na pytanie, które wpisałeś.

---

## 🎯 Zadanie

Zmień model w `first_claude.py` z `claude-haiku-4-5` na `claude-sonnet-5`, uruchom ponownie i zauważ (zwykle bogatszą) odpowiedź. Potem przełącz z powrotem na Haiku, aby koszty były minimalne.

---

## 💡 Najważniejsze wnioski

- Trzy kroki: instalacja → klient → `messages.create`.
- Odpowiedzi żyją w `response.content`; iteruj i wypisuj `block.text`.
- Używaj **Haiku** podczas nauki; zmieniasz model, zmieniając jeden ciąg.
- `max_tokens` ogranicza długość odpowiedzi i koszt.

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)
