# B3 — Zbuduj małą aplikację: Kompan do nauki

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `openai` + klucz API

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (3 min)

Masz już dwa klocki: **pamięć** (B1) i **streaming** (B2). Połącz je z **wiadomością systemową**, a powstanie prawdziwa aplikacja: **Kompan do nauki**, który odpytuje Cię z dowolnego tematu, pamięta odpowiedzi i się dostosowuje.

To wzorzec większości prostych aplikacji AI:

```
wiadomość systemowa (osobowość/zasady aplikacji)
      +
pamięć (rosnąca lista messages)
      +
streaming (ładne wyjście na żywo)
      =
mała aplikacja
```

---

## 🛠️ Zbuduj to (10 min)

### Krok 1 — Utwórz aplikację

```powershell
cd $HOME\learn-ai-gpt
notepad study_buddy.py
```

### Krok 2 — Wklej cały program i zapisz

```python
from openai import OpenAI

client = OpenAI()

SYSTEM = """Jesteś Kompanem do nauki, przyjaznym korepetytorem-quizmasterem.

Zasady:
- Najpierw, jeśli temat nie jest ustalony, zapytaj użytkownika, czego się uczyć.
- Potem zadawaj JEDNO pytanie naraz i czekaj na odpowiedź.
- Po każdej odpowiedzi: powiedz, czy jest poprawna, daj jednolinijkowe wyjaśnienie,
  potem zadaj kolejne pytanie, nieco trudniejsze, jeśli trafił.
- Bądź zachęcający i zwięzły. Licz, ile odpowiedzi było poprawnych.
- Jeśli użytkownik wpisze 'score', podaj ile poprawnych do tej pory.
"""

messages = [{"role": "system", "content": SYSTEM}]

print("📚 Kompan do nauki — wpisz 'quit', by zakończyć, 'score' po wynik.\n")

def stream_reply():
    print("Kompan: ", end="", flush=True)
    pieces = []
    stream = client.chat.completions.create(
        model="gpt-5-mini", messages=messages, stream=True,
    )
    for chunk in stream:
        piece = chunk.choices[0].delta.content
        if piece:
            print(piece, end="", flush=True)
            pieces.append(piece)
    messages.append({"role": "assistant", "content": "".join(pieces)})
    print("\n")

# Rozpocznij, aby korepetytor zapytał o temat
messages.append({"role": "user", "content": "Zacznijmy."})
stream_reply()

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        print("Dobra robota — do zobaczenia następnym razem! 👋")
        break
    messages.append({"role": "user", "content": user_text})
    stream_reply()
```

### Krok 3 — Uruchom i ucz się czegoś

```powershell
python study_buddy.py
```

Podaj temat („układ słoneczny”, „hiszpańskie czasowniki”, „podstawy Pythona”) i odpowiadaj na pytania. Zauważ, że:
- **pamięta** Twoje wcześniejsze odpowiedzi (pamięć),
- **streamuje** pytania (ładny UX),
- **trzyma się roli** korepetytora (wiadomość systemowa).

Zbudowałeś prawdziwą aplikację AI. 🎉

---

## 🚀 Rozbuduj (opcjonalnie, użyj Codex CLI)

Otwórz plik w Codex CLI (podstawowa lekcja 13) i poproś:

```text
Dodaj komendę 'save', która zapisuje całą rozmowę do pliku study-log.txt z dzisiejszą datą.
```
```text
Pozwól przekazać temat jako argument wiersza poleceń, bym mógł uruchomić: python study_buddy.py "słownictwo o francuskim jedzeniu".
```

Ty opisujesz funkcje; AI je pisze; Ty sprawdzasz i uruchamiasz.

---

## 🧩 Szkielet aplikacji wielokrotnego użytku

```text
1. messages = [{"role": "system", "content": "...zasady..."}]   # rola
2. pętla:
     wczytaj wejście użytkownika, dołącz do messages
     streamuj odpowiedź (stream=True), zbierz kawałki
     dołącz odpowiedź do messages                               # pamięć
```

Zmień wiadomość systemową, a masz inną aplikację: kreator e-maili, pomocnik przepisów, tłumacz kodu…

---

## ✅ Sprawdzenie

- [ ] `study_buddy.py` działa i odpytuje Cię.
- [ ] Pamięta wcześniejsze odpowiedzi i streamuje pytania.
- [ ] Umiesz wyjaśnić szkielet: system + pamięć + streaming.

---

## 🎯 Zadanie

Skopiuj `study_buddy.py` do nowego pliku i zmień **tylko wiadomość SYSTEM**, aby zrobić inną aplikację — „Kreator e-maili” lub „Pomocnik przepisów”. Ten sam szkielet, nowy cel.

---

## 💡 Najważniejsze wnioski

- Mała aplikacja = **wiadomość systemowa + pamięć + streaming**.
- Zmień wiadomość systemową → zupełnie inna aplikacja z tego samego szkieletu.
- Rozwijaj funkcje, opisując je Codex CLI.

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
