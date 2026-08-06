# B1 — Rozmowy z pamięcią

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `openai` + klucz API (kurs podstawowy)

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym każdy skrypt wysyłał **jedną** wiadomość i dostawał **jedną** odpowiedź. Ale API jest **bezstanowe** — nie pamięta niczego między wywołaniami. Jak więc działa styl ChatGPT „pamięta, co powiedziałem”?

**Ty** trzymasz pamięć. Utrzymujesz **listę wiadomości** i wysyłasz *całą rozmowę* za każdym razem. W każdej turze dołączasz dwie rzeczy:

1. wiadomość **użytkownika**,
2. odpowiedź **asystenta** GPT.

Kolejne zapytanie zawiera to wszystko, więc GPT „pamięta”. Pamięć to rosnąca lista `messages`.

```
messages = [ user, assistant, user, assistant, user ]  →  wyślij całość  →  nowa odpowiedź
```

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zobacz problem (bez pamięci)

Utwórz `no_memory.py`:

```python
from openai import OpenAI

client = OpenAI()

def ask(text):
    resp = client.chat.completions.create(
        model="gpt-5-mini",
        messages=[{"role": "user", "content": text}],
    )
    return resp.choices[0].message.content

print(ask("Mam na imię Alex."))
print(ask("Jak mam na imię?"))   # Nie będzie wiedzieć — brak pamięci
```

Uruchom — druga odpowiedź dowodzi, że API zapomniało.

### Krok 2 — Dodaj pamięć listą wiadomości

Utwórz `chat_memory.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []  # ta lista TO pamięć

def chat(user_text):
    messages.append({"role": "user", "content": user_text})     # 1. tura użytkownika
    resp = client.chat.completions.create(                       # 2. wyślij CAŁĄ historię
        model="gpt-5-mini",
        messages=messages,
    )
    reply = resp.choices[0].message.content
    messages.append({"role": "assistant", "content": reply})    # 3. zapamiętaj odpowiedź
    return reply

print(chat("Mam na imię Alex i uwielbiam wędrówki."))
print(chat("Jak mam na imię i jeden pomysł na prezent dla mnie?"))  # Teraz pamięta
```

Uruchom — druga odpowiedź zna Twoje imię **i** używa szczegółu o wędrówkach. 🎉

### Krok 3 — Zrób interaktywną pętlę

Utwórz `chat_loop.py`:

```python
from openai import OpenAI

client = OpenAI()
messages = []

print("Rozmawiaj z GPT. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break
    messages.append({"role": "user", "content": user_text})
    resp = client.chat.completions.create(model="gpt-5-mini", messages=messages)
    reply = resp.choices[0].message.content
    messages.append({"role": "assistant", "content": reply})
    print("GPT:", reply, "\n")
```

Prawdziwy chatbot pamiętający całą rozmowę.

---

## 🧩 Czego się nauczyłeś

| Idea | Dlaczego ważna |
|------|----------------|
| API jest **bezstanowe** | Musisz ponownie wysyłać historię przy każdym wywołaniu |
| Lista `messages` **jest** pamięcią | Dołączaj user + assistant w każdej turze |
| Role `user`/`assistant`/`system` | Jak GPT śledzi, kto co powiedział |

> ⚠️ **Uwaga o koszcie:** każda tura ponownie wysyła całą historię, więc długie rozmowy kosztują więcej tokenów. Przycinaj stare tury w razie potrzeby.

---

## ✅ Sprawdzenie

- [ ] `no_memory.py` pokazuje, jak API zapomina.
- [ ] `chat_memory.py` pamięta między dwiema turami.
- [ ] `chat_loop.py` działa jako interaktywny chatbot.

---

## 🎯 Zadanie

Dodaj **wiadomość systemową** jako pierwszy element `messages`, aby bot miał spójną osobowość:
```python
messages = [{"role": "system", "content": "Jesteś zwięzłym, wspierającym trenerem."}]
```
Zauważ, że utrzymuje tę rolę w każdej turze.

---

## 💡 Najważniejsze wnioski

- Pamięć = **Ty** ponownie wysyłający rosnącą listę `messages` przy każdym wywołaniu.
- Dołączaj i turę użytkownika, i odpowiedź GPT w każdej rundzie.
- Wiadomość `system` na początku ustawia trwałą rolę.

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)
