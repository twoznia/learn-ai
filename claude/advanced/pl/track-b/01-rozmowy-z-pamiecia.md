# B1 — Rozmowy z pamięcią

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `anthropic` + klucz API (kurs podstawowy)

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)

---

## 🧠 Teoria (4 min)

W kursie podstawowym każdy skrypt wysyłał **jedną** wiadomość i dostawał **jedną** odpowiedź. Ale API jest **bezstanowe** — nie pamięta niczego między wywołaniami. Jak więc działa styl ChatGPT „pamięta, co powiedziałem”?

**Ty** trzymasz pamięć. Utrzymujesz **listę wiadomości** i wysyłasz *całą rozmowę* za każdym razem. W każdej turze dołączasz dwie rzeczy:

1. wiadomość **użytkownika**,
2. odpowiedź **asystenta** (Claude).

Kolejne zapytanie zawiera to wszystko, więc Claude „pamięta”. Pamięć to po prostu rosnąca lista `messages`.

```
messages = [ user, assistant, user, assistant, user ]  →  wyślij całość  →  nowa odpowiedź asystenta
```

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Jednorazowe bez pamięci (aby zobaczyć problem)

Utwórz `no_memory.py` w folderze kursu:

```python
import anthropic

client = anthropic.Anthropic()

def ask(text):
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=300,
        messages=[{"role": "user", "content": text}],
    )
    return resp.content[0].text

print(ask("Mam na imię Alex."))
print(ask("Jak mam na imię?"))   # Nie będzie wiedzieć — brak pamięci
```

Uruchom — druga odpowiedź dowodzi, że API zapomniało.

### Krok 2 — Dodaj pamięć listą wiadomości

Utwórz `chat_memory.py`:

```python
import anthropic

client = anthropic.Anthropic()

messages = []  # ta lista TO pamięć

def chat(user_text):
    # 1. dodaj turę użytkownika
    messages.append({"role": "user", "content": user_text})

    # 2. wyślij CAŁĄ rozmowę
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=500,
        messages=messages,
    )
    reply = resp.content[0].text

    # 3. zapisz turę asystenta, by była zapamiętana następnym razem
    messages.append({"role": "assistant", "content": reply})
    return reply

print(chat("Mam na imię Alex i uwielbiam wędrówki."))
print(chat("Jak mam na imię i jeden pomysł na prezent dla mnie?"))  # Teraz pamięta
```

Uruchom — druga odpowiedź zna Twoje imię **i** używa szczegółu o wędrówkach. 🎉

### Krok 3 — Zrób prawdziwą interaktywną pętlę

Utwórz `chat_loop.py`:

```python
import anthropic

client = anthropic.Anthropic()
messages = []

print("Rozmawiaj z Claude. Wpisz 'quit', aby wyjść.\n")

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        break

    messages.append({"role": "user", "content": user_text})
    resp = client.messages.create(
        model="claude-haiku-4-5",
        max_tokens=600,
        messages=messages,
    )
    reply = resp.content[0].text
    messages.append({"role": "assistant", "content": reply})
    print("Claude:", reply, "\n")
```

Masz teraz prawdziwego chatbota, który pamięta całą rozmowę.

---

## 🧩 Czego się nauczyłeś

| Idea | Dlaczego ważna |
|------|----------------|
| API jest **bezstanowe** | Musisz ponownie wysyłać historię przy każdym wywołaniu |
| Lista `messages` **jest** pamięcią | Dołączaj user + assistant w każdej turze |
| Role naprzemiennie `user`/`assistant` | Tak Claude śledzi, kto co powiedział |

> ⚠️ **Uwaga o koszcie:** każda tura ponownie wysyła całą historię, więc długie rozmowy kosztują więcej tokenów. Później możesz przycinać stare tury lub je streszczać — ale do nauki to dokładnie w porządku.

---

## ✅ Sprawdzenie

- [ ] `no_memory.py` pokazuje, jak API zapomina.
- [ ] `chat_memory.py` pamięta między dwiema turami.
- [ ] `chat_loop.py` działa jako interaktywny chatbot.

---

## 🎯 Zadanie

Dodaj **prompt systemowy** do `chat_loop.py` (parametr `system="..."`), aby Twój bot miał spójną osobowość — np. „Jesteś zwięzłym, wspierającym trenerem.” Zauważ, że utrzymuje tę rolę w każdej turze.

---

## 💡 Najważniejsze wnioski

- Pamięć = **Ty** ponownie wysyłający rosnącą listę `messages` przy każdym wywołaniu.
- Dołączaj i turę użytkownika, i odpowiedź Claude w każdej rundzie.
- Długie rozmowy kosztują więcej tokenów (ponownie wysyłana historia) — przycinaj w razie potrzeby.

🌐 [English](../../en/track-b/01-conversations-with-memory.md) · [← Indeks ścieżki](../README.md) · [Dalej: Streaming →](02-streaming.md)
