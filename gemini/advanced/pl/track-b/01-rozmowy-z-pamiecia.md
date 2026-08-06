# B1 — Rozmowy z pamięcią

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `google-genai` + klucz API (kurs podstawowy)

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym każdy skrypt wysyłał **jedną** wiadomość przez `generate_content` i dostawał **jedną** odpowiedź — bez pamięci między wywołaniami. Aby zbudować chatbota, który pamięta, potrzebujesz **historii rozmowy**.

Biblioteka `google-genai` daje dwa sposoby:

1. **`client.chats`** (łatwy) — obiekt czatu **trzyma historię za Ciebie**. Po prostu `send_message` w każdej turze.
2. **Ręczna lista `contents`** (pełna kontrola) — budujesz listę tur samodzielnie.

Użyjemy `client.chats` — to czysty sposób na pamięć.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zobacz problem (bez pamięci)

Utwórz `no_memory.py`:

```python
from google import genai

client = genai.Client()

def ask(text):
    return client.models.generate_content(
        model="gemini-2.5-flash", contents=text
    ).text

print(ask("Mam na imię Alex."))
print(ask("Jak mam na imię?"))   # Nie będzie wiedzieć — każde wywołanie niezależne
```

Uruchom — druga odpowiedź dowodzi braku pamięci.

### Krok 2 — Dodaj pamięć obiektem czatu

Utwórz `chat_memory.py`:

```python
from google import genai

client = genai.Client()

# Obiekt czatu pamięta całą rozmowę za Ciebie
chat = client.chats.create(model="gemini-2.5-flash")

print(chat.send_message("Mam na imię Alex i uwielbiam wędrówki.").text)
print(chat.send_message("Jak mam na imię i jeden pomysł na prezent dla mnie?").text)  # Pamięta
```

Uruchom — druga odpowiedź zna Twoje imię **i** używa szczegółu o wędrówkach. 🎉 Obiekt `chat` zapisał każdą turę.

### Krok 3 — Zrób interaktywną pętlę

Utwórz `chat_loop.py`:

```python
from google import genai

client = genai.Client()
chat = client.chats.create(model="gemini-2.5-flash")

print("Rozmawiaj z Gemini. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    reply = chat.send_message(user_text).text
    print("Gemini:", reply, "\n")
```

Prawdziwy chatbot pamiętający całą rozmowę — bez ręcznego zarządzania listą.

### Krok 4 — Zajrzyj do zapisanej historii

Dodaj na końcu:

```python
for message in chat.get_history():
    print(message.role, "→", message.parts[0].text[:60])
```

`chat.get_history()` pokazuje tury, które obiekt trzyma. Ta historia **jest** pamięcią.

---

## 🧩 Czego się nauczyłeś

| Idea | Dlaczego ważna |
|------|----------------|
| `generate_content` jest jednorazowe | Brak pamięci między wywołaniami |
| `client.chats.create(...)` | Obiekt czatu przechowujący historię |
| `chat.send_message(text)` | Wysyła turę *i* ją pamięta |
| `chat.get_history()` | Podejrzyj zapisaną rozmowę |

> ⚠️ **Uwaga o koszcie:** historia rośnie i jest ponownie wysyłana w każdej turze, więc długie czaty zużywają więcej tokenów. Zacznij nowy obiekt czatu dla nowego tematu.

---

## ✅ Sprawdzenie

- [ ] `no_memory.py` pokazuje niezależne wywołania zapominające.
- [ ] `chat_memory.py` pamięta między dwiema turami.
- [ ] `chat_loop.py` działa jako interaktywny chatbot.

---

## 🎯 Zadanie

Dodaj **instrukcję systemową**, aby bot miał osobowość. Utwórz czat z:
```python
from google.genai import types
chat = client.chats.create(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(system_instruction="Jesteś zwięzłym, wspierającym trenerem."),
)
```
Zauważ, że utrzymuje tę rolę w każdej turze.

---

## 💡 Najważniejsze wnioski

- `client.chats` daje pamięć za darmo — obiekt czatu trzyma historię.
- `send_message` wysyła turę i ją pamięta; `get_history()` ją pokazuje.
- Długie czaty kosztują więcej tokenów; nowy czat dla nowego tematu.

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)
