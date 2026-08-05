# Lekcja 10 — Twój pierwszy skrypt w Pythonie z Gemini

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Python (L8), ustawiony klucz API (L9)

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)

---

## 🧠 Teoria (2 min)

Teraz zrobisz **własny program**, który rozmawia z Gemini. Kroki są zawsze te same:

1. **Zainstaluj** oficjalną bibliotekę (`google-genai`).
2. **Utwórz klienta** (odczytuje Twój `GEMINI_API_KEY` automatycznie).
3. **Wygeneruj treść** i wypisz odpowiedź.

Użyjemy **Gemini Flash** — szybkiego i objętego darmowym poziomem — więc nauka jest praktycznie darmowa. Identyfikatory modeli:

| Model | ID (skopiuj dokładnie) | Dobry do |
|-------|-------------------|----------|
| Flash-Lite (najtańszy) | `gemini-2.5-flash-lite` | Masowe, proste zadania |
| Flash (zrównoważony) | `gemini-2.5-flash` | Nauka, codzienna praca |
| Pro (najmądrzejszy) | `gemini-2.5-pro` | Trudne rozumowanie/kodowanie |

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj bibliotekę

Otwórz **PowerShell** i przejdź do folderu kursu:

```powershell
cd $HOME\learn-ai-gemini
pip install google-genai
```

Zajmuje ~30 sekund.

### Krok 2 — Utwórz skrypt

```powershell
notepad first_gemini.py
```

Kliknij **Tak**, potem **wklej to** i zapisz (Ctrl+S):

```python
from google import genai

# Klient automatycznie odczytuje zmienną środowiskową GEMINI_API_KEY
client = genai.Client()

# Wyślij jedną wiadomość do Gemini
response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents="Przywitaj się i podaj jeden ciekawy fakt o Księżycu.",
)

# Wypisz odpowiedź tekstową
print(response.text)
```

### Krok 3 — Uruchom go

```powershell
python first_gemini.py
```

🎉 Powinieneś zobaczyć powitanie Gemini i fakt o Księżycu. **Właśnie zbudowałeś aplikację AI.**

### Krok 4 — Zrób go interaktywnym

Utwórz `chat_once.py`:

```powershell
notepad chat_once.py
```

Wklej i zapisz:

```python
from google import genai

client = genai.Client()

# Zapytaj użytkownika o wpis
question = input("Zapytaj Gemini o cokolwiek: ")

response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents=question,
)

print("\nGemini mówi:\n" + response.text)
```

Uruchom:

```powershell
python chat_once.py
```

Wpisz pytanie, naciśnij Enter, a Gemini odpowie. 🙌

---

## 🧩 Zrozumienie kodu (1 min)

| Linia | Co robi |
|------|--------------|
| `from google import genai` | Ładuje bibliotekę |
| `genai.Client()` | Łączy się przy użyciu Twojego klucza |
| `model="gemini-2.5-flash"` | Wybiera, którego Gemini użyć |
| `contents="..."` | Twój prompt |
| `response.text` | Odpowiedź tekstowa, gotowa do wypisania |

> 💡 Chcesz „rolę”/instrukcję systemową? Dodaj konfigurację:
> ```python
> from google.genai import types
> response = client.models.generate_content(
>     model="gemini-2.5-flash",
>     config=types.GenerateContentConfig(
>         system_instruction="Jesteś przyjaznym korepetytorem. Wyjaśniaj prosto."
>     ),
>     contents="Czym jest API?",
> )
> ```

---

## ✅ Sprawdzenie

- [ ] `pip install google-genai` się powiodło.
- [ ] `first_gemini.py` wypisał odpowiedź.
- [ ] `chat_once.py` odpowiedział na pytanie, które wpisałeś.

---

## 🎯 Zadanie

Zmień model w `first_gemini.py` z `gemini-2.5-flash` na `gemini-2.5-pro`, uruchom ponownie i zauważ (zwykle bogatszą) odpowiedź. Potem przełącz z powrotem na Flash, aby zostać na darmowym poziomie.

---

## 💡 Najważniejsze wnioski

- Trzy kroki: instalacja → klient → `generate_content`.
- Tekst odpowiedzi to po prostu `response.text`.
- Używaj **Flash** podczas nauki; zmieniasz model, zmieniając jeden ciąg.
- Dodaj `system_instruction` przez `GenerateContentConfig`, aby ustawić rolę.

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)
