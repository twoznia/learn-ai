# B3 — Zbuduj małą aplikację: Pomocnik do nauki

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `google-genai` + klucz API

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (3 min)

Masz dwa klocki: **pamięć** (B1, przez `client.chats`) i **streaming** (B2). Dodaj **instrukcję systemową** i masz prawdziwą aplikację: **Pomocnika do nauki**, który odpytuje z dowolnego tematu, pamięta odpowiedzi i dostosowuje się.

To wzorzec większości prostych aplikacji AI:

```
instrukcja systemowa (osobowość/zasady aplikacji)
      +
pamięć czatu (client.chats trzyma historię)
      +
streaming (ładne wyjście na żywo)
      =
mała aplikacja
```

---

## 🛠️ Zbuduj to (10 min)

### Krok 1 — Utwórz aplikację

```powershell
cd $HOME\learn-ai-gemini
notepad study_buddy.py
```

### Krok 2 — Wklej ten kompletny program i zapisz

```python
from google import genai
from google.genai import types

client = genai.Client()

SYSTEM = """Jesteś Pomocnikiem do nauki, przyjaznym korepetytorem-quizmasterem.

Zasady:
- Najpierw, jeśli temat nie jest ustalony, zapytaj użytkownika, czego się uczyć.
- Potem zadawaj JEDNO pytanie naraz i czekaj na odpowiedź.
- Po każdej odpowiedzi: powiedz, czy jest poprawna, daj jednoliniowe wyjaśnienie,
  potem zadaj następne pytanie, nieco trudniejsze, jeśli odpowiedział poprawnie.
- Bądź zachęcający i zwięzły. Śledź, ile odpowiedzi jest poprawnych.
- Jeśli użytkownik wpisze 'wynik', podaj, ile do tej pory poprawnych.
"""

chat = client.chats.create(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(system_instruction=SYSTEM),
)

print("📚 Pomocnik do nauki — wpisz 'quit', aby przerwać, 'wynik' po wynik.\n")

def stream_reply(message):
    print("Pomocnik: ", end="", flush=True)
    for chunk in chat.send_message_stream(message):
        print(chunk.text, end="", flush=True)
    print("\n")

stream_reply("Zacznijmy.")  # pierwszy prompt: pyta o temat

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        print("Dobra robota — do zobaczenia następnym razem! 👋")
        break
    stream_reply(user_text)
```

### Krok 3 — Uruchom i naucz się czegoś

```powershell
python study_buddy.py
```

Podaj mu temat („układ słoneczny”, „czasowniki hiszpańskie”, „podstawy Pythona”) i odpowiadaj. Zauważ, że:
- **pamięta** poprzednie odpowiedzi (pamięć czatu),
- **streamuje** pytania (ładny UX),
- **pozostaje w roli** korepetytora (instrukcja systemowa).

Zbudowałeś prawdziwą aplikację AI. 🎉

---

## 🚀 Rozszerz ją (opcjonalnie, użyj Gemini CLI)

Otwórz plik w Gemini CLI (podstawowa Lekcja 13) i poproś:

```text
Dodaj komendę 'zapisz', która zapisuje całą rozmowę do pliku study-log.txt z dzisiejszą datą.
```
```text
Pozwól przekazać temat jako argument wiersza poleceń: python study_buddy.py "słownictwo francuskie o jedzeniu".
```

Opisujesz funkcje; AI je pisze; Ty przeglądasz i uruchamiasz.

---

## 🧩 Szkielet aplikacji wielokrotnego użytku

```text
1. SYSTEM = "...zasady aplikacji..."
2. chat = client.chats.create(model=..., config=system_instruction)   # pamięć
3. pętla:
     odczytaj wejście użytkownika
     streamuj odpowiedź przez chat.send_message_stream(...)
```

Zmień instrukcję systemową i masz inną aplikację: redaktor e-maili, pomocnik przepisów, objaśniacz kodu…

---

## ✅ Sprawdzenie

- [ ] `study_buddy.py` działa i Cię odpytuje.
- [ ] Pamięta wcześniejsze odpowiedzi i streamuje pytania.
- [ ] Potrafisz wyjaśnić szkielet system + pamięć + streaming.

---

## 🎯 Zadanie

Skopiuj `study_buddy.py` do nowego pliku i zmień **tylko instrukcję SYSTEM**, aby zrobić inną aplikację — „Redaktor e-maili” lub „Pomocnik przepisów”. Ten sam szkielet, nowy cel.

---

## 💡 Najważniejsze wnioski

- Mała aplikacja = **instrukcja systemowa + pamięć czatu + streaming**.
- Zmień instrukcję systemową → zupełnie inna aplikacja z tego samego szkieletu.
- Rozwijaj funkcje, opisując je Gemini CLI.

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
