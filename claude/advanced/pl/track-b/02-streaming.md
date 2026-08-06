# B2 — Odpowiedzi strumieniowe (streaming)

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `anthropic` + klucz API

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)

---

## 🧠 Teoria (4 min)

Gdy wywołujesz `messages.create(...)`, program **czeka** na całą odpowiedź, potem wypisuje ją naraz. Przy długiej odpowiedzi to niezręczna cisza.

**Streaming** dostarcza odpowiedź **w trakcie generowania**, słowo po słowie — dokładnie jak w aplikacji Claude. Ten sam wynik, znacznie lepsze odczucie. Pozwala też pokazać postęp i zacząć czytać wcześniej.

Biblioteka `anthropic` ułatwia to przez `client.messages.stream(...)` i pętlę `for` po `stream.text_stream`.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Porównaj: bez streamingu vs ze streamingiem

Utwórz `stream_demo.py`:

```python
import anthropic

client = anthropic.Anthropic()

prompt = "Napisz krótki, pogodny akapit o nauce programowania."

# --- Bez streamingu: jedno duże oczekiwanie, potem wszystko naraz ---
print("=== BEZ STREAMINGU (czeka, potem wypisuje) ===")
resp = client.messages.create(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": prompt}],
)
print(resp.content[0].text)

# --- Ze streamingiem: pojawia się słowo po słowie ---
print("\n=== STREAMING (pojawia się w trakcie pisania) ===")
with client.messages.stream(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": prompt}],
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
print()
```

Uruchom:

```powershell
python stream_demo.py
```

Zobacz różnicę — druga wersja sama się „wpisuje”. `flush=True` wymusza natychmiastowe pokazanie każdego kawałka.

### Krok 2 — Pobierz pełny tekst po streamingu

Czasem chcesz streamować na ekran **i** zachować całą odpowiedź (np. by ją zapisać lub dodać do pamięci):

```python
import anthropic

client = anthropic.Anthropic()

with client.messages.stream(
    model="claude-haiku-4-5",
    max_tokens=400,
    messages=[{"role": "user", "content": "Podaj 3 wskazówki do nauki."}],
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)

    final = stream.get_final_message()   # kompletny obiekt wiadomości

print("\n\n[Użyto tokenów:", final.usage.output_tokens, "]")
```

`get_final_message()` daje złożoną odpowiedź plus informacje o użyciu — przydatne do logowania kosztu.

### Krok 3 — Streaming + pamięć (połącz B1 i B2)

Utwórz `chat_stream.py` — chatbot, który streamuje *i* pamięta:

```python
import anthropic

client = anthropic.Anthropic()
messages = []

print("Czat ze streamingiem. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    messages.append({"role": "user", "content": user_text})

    print("Claude: ", end="", flush=True)
    with client.messages.stream(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=messages,
    ) as stream:
        for text in stream.text_stream:
            print(text, end="", flush=True)
        reply = stream.get_final_message().content[0].text

    messages.append({"role": "assistant", "content": reply})
    print("\n")
```

Teraz działa jak prawdziwa aplikacja Claude: odpowiedzi napływają strumieniem i pamięta.

---

## 🧩 Podstawy streamingu

| Element | Co robi |
|-------|--------------|
| `with client.messages.stream(...) as stream:` | Otwiera strumień |
| `for text in stream.text_stream:` | Zwraca kawałki tekstu |
| `print(text, end="", flush=True)` | Wypisuje każdy kawałek natychmiast |
| `stream.get_final_message()` | Pełna wiadomość + użycie po streamingu |

---

## ✅ Sprawdzenie

- [ ] Zobaczyłeś obok siebie wersję bez streamingu i ze streamingiem.
- [ ] Przechwyciłeś pełną odpowiedź przez `get_final_message()`.
- [ ] `chat_stream.py` streamuje **i** pamięta rozmowę.

---

## 🎯 Zadanie

Dodaj prompt `system` do `chat_stream.py`, aby Twój strumieniowy bot miał rolę, i wypisuj bieżącą sumę tokenów po każdej turze (z `get_final_message().usage`). Masz teraz chatbota z osobowością, żywym pisaniem i świadomością kosztu.

---

## 💡 Najważniejsze wnioski

- Streaming pokazuje odpowiedź **w trakcie pisania** — ten sam wynik, lepszy UX.
- Używaj `messages.stream(...)` + `for text in stream.text_stream`.
- `get_final_message()` daje pełny tekst i użycie do zapisu lub logowania.

🌐 [English](../../en/track-b/02-streaming.md) · [← Wstecz](01-rozmowy-z-pamiecia.md) · [Indeks ścieżki](../README.md) · [Dalej: Zbuduj aplikację →](03-zbuduj-aplikacje.md)
