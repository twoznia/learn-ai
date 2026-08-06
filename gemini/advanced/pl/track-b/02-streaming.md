# B2 — Odpowiedzi strumieniowe (streaming)

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `google-genai` + klucz API

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)

---

## 🧠 Teoria (4 min)

`generate_content(...)` każe programowi **czekać** na całą odpowiedź, potem wypisać ją naraz. Przy długich odpowiedziach to niezręczna cisza.

**Streaming** dostarcza odpowiedź **w trakcie generowania**, słowo po słowie — jak aplikacja Gemini. Biblioteka `google-genai` ma warianty strumieniowe:

- `client.models.generate_content_stream(...)` — strumień jednorazowy.
- `chat.send_message_stream(...)` — strumień w czacie z pamięcią.

Oba zwracają **kawałki**; każdy ma `.text`, który wypisujesz od razu.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Porównaj bez streamingu vs ze streamingiem

Utwórz `stream_demo.py`:

```python
from google import genai

client = genai.Client()
prompt = "Napisz krótki, pogodny akapit o nauce programowania."

# --- Bez streamingu: czeka, potem wypisuje naraz ---
print("=== BEZ STREAMINGU ===")
print(client.models.generate_content(model="gemini-2.5-flash", contents=prompt).text)

# --- Ze streamingiem: pojawia się kawałek po kawałku ---
print("\n=== STREAMING ===")
for chunk in client.models.generate_content_stream(
    model="gemini-2.5-flash", contents=prompt
):
    print(chunk.text, end="", flush=True)
print()
```

Uruchom:

```powershell
python stream_demo.py
```

Zobacz, jak druga wersja sama się „wpisuje”. `flush=True` wymusza natychmiastowe pokazanie każdego kawałka.

### Krok 2 — Streaming w czacie (pamięć + streaming)

Utwórz `chat_stream.py`:

```python
from google import genai

client = genai.Client()
chat = client.chats.create(model="gemini-2.5-flash")

print("Czat ze streamingiem. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    print("Gemini: ", end="", flush=True)
    for chunk in chat.send_message_stream(user_text):
        print(chunk.text, end="", flush=True)
    print("\n")
```

`send_message_stream` streamuje odpowiedź **i** obiekt czatu wciąż ją pamięta — żywe pisanie *i* pamięć w jednym wywołaniu.

### Krok 3 — Zbierz pełny tekst podczas streamingu

Czasem chcesz streamować na ekran **i** zachować całą odpowiedź (by ją zapisać):

```python
from google import genai

client = genai.Client()

pieces = []
for chunk in client.models.generate_content_stream(
    model="gemini-2.5-flash", contents="Podaj 3 wskazówki do nauki."
):
    print(chunk.text, end="", flush=True)
    pieces.append(chunk.text)

full_reply = "".join(pieces)
print("\n\n[Zebrano", len(full_reply), "znaków]")
```

Sklejenie kawałków daje pełny tekst do zapisu lub logowania.

---

## 🧩 Podstawy streamingu

| Element | Co robi |
|-------|--------------|
| `generate_content_stream(...)` | Strumień jednorazowy |
| `chat.send_message_stream(...)` | Strumień z pamięcią |
| `for chunk in ...: chunk.text` | Każdy przyrostowy kawałek |
| `print(text, end="", flush=True)` | Pokaż każdy kawałek od razu |
| `"".join(pieces)` | Odbuduj pełną odpowiedź |

---

## ✅ Sprawdzenie

- [ ] Zobaczyłeś obok siebie wersję bez streamingu i ze streamingiem.
- [ ] `chat_stream.py` streamuje **i** pamięta.
- [ ] Przechwyciłeś pełną odpowiedź, sklejając kawałki.

---

## 🎯 Zadanie

Dodaj `system_instruction` (przez `config=`) do `chat_stream.py`, aby Twój strumieniowy bot miał rolę. Masz teraz chatbota z osobowością, pamięcią i żywym pisaniem.

---

## 💡 Najważniejsze wnioski

- Streaming pokazuje odpowiedź **w trakcie pisania** — ten sam wynik, lepszy UX.
- Używaj `generate_content_stream` (jednorazowo) lub `send_message_stream` (z pamięcią).
- Sklej `.text` kawałków, aby zachować pełną odpowiedź.

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)
