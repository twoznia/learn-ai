# Lekcja 10 — Twój pierwszy skrypt w Pythonie z GPT

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: Python (L8), ustawiony klucz API (L9)

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)

---

## 🧠 Teoria (2 min)

Teraz zrobisz **własny program**, który rozmawia z GPT. Kroki są zawsze te same:

1. **Zainstaluj** oficjalną bibliotekę (`openai`).
2. **Utwórz klienta** (odczytuje Twój `OPENAI_API_KEY` automatycznie).
3. **Wyślij wiadomości** i wypisz odpowiedź.

Użyjemy modelu **mini** — szybkiego i taniego — więc nauka kosztuje ułamek grosza. Identyfikatory modeli (aktualną listę sprawdź na **platform.openai.com/docs/models**):

| Model | ID (skopiuj dokładnie) | Dobry do |
|-------|-------------------|----------|
| Mini (najtańszy) | `gpt-5-mini` | Nauka, proste zadania |
| Flagowy (najmądrzejszy) | `gpt-5` | Trudne rozumowanie/kodowanie |

> Jeśli `gpt-5-mini` nie jest dostępny na Twoim koncie, `gpt-4o-mini` to szeroko dostępna tania alternatywa — po prostu zmień ciąg.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zainstaluj bibliotekę

Otwórz **PowerShell** i przejdź do folderu kursu:

```powershell
cd $HOME\learn-ai-gpt
pip install openai
```

Zajmuje ~30 sekund.

### Krok 2 — Utwórz skrypt

```powershell
notepad first_gpt.py
```

Kliknij **Tak**, potem **wklej to** i zapisz (Ctrl+S):

```python
from openai import OpenAI

# Klient automatycznie odczytuje zmienną środowiskową OPENAI_API_KEY
client = OpenAI()

# Wyślij jedną wiadomość do GPT
response = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[
        {"role": "user", "content": "Przywitaj się i podaj jeden ciekawy fakt o Księżycu."}
    ],
)

# Wypisz odpowiedź tekstową
print(response.choices[0].message.content)
```

### Krok 3 — Uruchom go

```powershell
python first_gpt.py
```

🎉 Powinieneś zobaczyć powitanie GPT i fakt o Księżycu. **Właśnie zbudowałeś aplikację AI.**

### Krok 4 — Zrób go interaktywnym

Utwórz `chat_once.py`:

```powershell
notepad chat_once.py
```

Wklej i zapisz:

```python
from openai import OpenAI

client = OpenAI()

# Zapytaj użytkownika o wpis
question = input("Zapytaj GPT o cokolwiek: ")

response = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[
        {"role": "user", "content": question}
    ],
)

print("\nGPT mówi:\n" + response.choices[0].message.content)
```

Uruchom:

```powershell
python chat_once.py
```

Wpisz pytanie, naciśnij Enter, a GPT odpowie. 🙌

---

## 🧩 Zrozumienie kodu (1 min)

| Linia | Co robi |
|------|--------------|
| `from openai import OpenAI` | Ładuje bibliotekę |
| `OpenAI()` | Łączy się przy użyciu Twojego klucza |
| `model="gpt-5-mini"` | Wybiera, którego GPT użyć |
| `messages=[{"role": "user", ...}]` | Twój prompt |
| `response.choices[0].message.content` | Odpowiedź tekstowa, gotowa do wypisania |

> 💡 Chcesz „rolę”/prompt systemowy? Dodaj najpierw wiadomość systemową:
> ```python
> messages=[
>     {"role": "system", "content": "Jesteś przyjaznym korepetytorem. Wyjaśniaj prosto."},
>     {"role": "user", "content": "Czym jest API?"},
> ]
> ```

---

## ✅ Sprawdzenie

- [ ] `pip install openai` się powiodło.
- [ ] `first_gpt.py` wypisał odpowiedź.
- [ ] `chat_once.py` odpowiedział na pytanie, które wpisałeś.

---

## 🎯 Zadanie

Zmień model w `first_gpt.py` z `gpt-5-mini` na `gpt-5`, uruchom ponownie i zauważ (zwykle bogatszą) odpowiedź. Potem przełącz z powrotem na mini, aby koszty były minimalne.

---

## 💡 Najważniejsze wnioski

- Trzy kroki: instalacja → klient → `chat.completions.create`.
- Tekst odpowiedzi to `response.choices[0].message.content`.
- Używaj modelu **mini** podczas nauki; zmieniasz go, zmieniając jeden ciąg.
- Dodaj wiadomość `{"role": "system", ...}`, aby ustawić rolę.

🌐 [English](../../en/lessons/10-python-first-script.md) · [← Wstecz](09-klucz-api.md) · [Strona kursu](../README.md) · [Dalej: PowerShell →](11-powershell.md)
