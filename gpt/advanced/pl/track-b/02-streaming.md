# B2 — Odpowiedzi strumieniowe (streaming)

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `openai` + klucz API

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)

---

## 🧠 Teoria (4 min)

Domyślnie `chat.completions.create(...)` każe programowi **czekać** na całą odpowiedź, potem wypisać ją naraz. Przy długiej odpowiedzi to niezręczna cisza.

**Streaming** dostarcza odpowiedź **w trakcie generowania**, słowo po słowie — jak aplikacja ChatGPT. Włączasz go przez `stream=True`, potem iterujesz po kawałkach. Każdy kawałek niesie mały fragment tekstu w `chunk.choices[0].delta.content`.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Porównaj bez streamingu vs ze streamingiem

Utwórz `stream_demo.py`:

```python
from openai import OpenAI

client = OpenAI()
prompt = "Napisz krótki, pogodny akapit o nauce programowania."

# --- Bez streamingu: czeka, potem wypisuje naraz ---
print("=== BEZ STREAMINGU ===")
resp = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": prompt}],
)
print(resp.choices[0].message.content)

# --- Ze streamingiem: pojawia się kawałek po kawałku ---
print("\n=== STREAMING ===")
stream = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": prompt}],
    stream=True,
)
for chunk in stream:
    piece = chunk.choices[0].delta.content
    if piece:                      # niektóre kawałki nie mają tekstu — pomiń je
        print(piece, end="", flush=True)
print()
```

Uruchom:

```powershell
python stream_demo.py
```

Zobacz, jak druga wersja sama się „wpisuje”. `flush=True` wymusza natychmiastowe pokazanie każdego kawałka. Strażnik `if piece:` pomija puste kawałki (strumień wysyła kilka).

### Krok 2 — Zbierz pełny tekst podczas streamingu

Streamuj na ekran **i** zachowaj całą odpowiedź (by ją zapisać lub dodać do pamięci):

```python
from openai import OpenAI

client = OpenAI()

pieces = []
stream = client.chat.completions.create(
    model="gpt-5-mini",
    messages=[{"role": "user", "content": "Podaj 3 wskazówki do nauki."}],
    stream=True,
)
for chunk in stream:
    piece = chunk.choices[0].delta.content
    if piece:
        print(piece, end="", flush=True)
        pieces.append(piece)

full_reply = "".join(pieces)
print("\n\n[Zebrano", len(full_reply), "znaków]")
```

### Krok 3 — Streaming + pamięć (połącz B1 i B2)

Utwórz `chat_stream.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []

print("Czat ze streamingiem. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    messages.append({"role": "user", "content": user_text})

    print("GPT: ", end="", flush=True)
    pieces = []
    stream = client.chat.completions.create(
        model="gpt-5-mini", messages=messages, stream=True,
    )
    for chunk in stream:
        piece = chunk.choices[0].delta.content
        if piece:
            print(piece, end="", flush=True)
            pieces.append(piece)

    reply = "".join(pieces)
    messages.append({"role": "assistant", "content": reply})
    print("\n")
```

Teraz działa jak prawdziwa aplikacja ChatGPT: odpowiedzi napływają strumieniem i pamięta.

---

## 🧩 Podstawy streamingu

| Element | Co robi |
|-------|--------------|
| `stream=True` | Włącza streaming |
| `for chunk in stream:` | Zwraca kawałki |
| `chunk.choices[0].delta.content` | Przyrostowy tekst (może być pusty) |
| `if piece:` | Pomiń puste kawałki |
| `"".join(pieces)` | Odbuduj pełną odpowiedź |

---

## ✅ Sprawdzenie

- [ ] Zobaczyłeś obok siebie wersję bez streamingu i ze streamingiem.
- [ ] Przechwyciłeś pełną odpowiedź, sklejając kawałki.
- [ ] `chat_stream.py` streamuje **i** pamięta.

---

## 🎯 Zadanie

Dodaj wiadomość `system` do `chat_stream.py`, aby Twój strumieniowy bot miał rolę. Masz teraz chatbota z osobowością, pamięcią i żywym pisaniem.

---

## 💡 Najważniejsze wnioski

- Streaming pokazuje odpowiedź **w trakcie pisania** — ten sam wynik, lepszy UX.
- Ustaw `stream=True` i czytaj `chunk.choices[0].delta.content` (chroń puste).
- Sklej kawałki, aby zachować pełną odpowiedź do pamięci lub zapisu.

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)
