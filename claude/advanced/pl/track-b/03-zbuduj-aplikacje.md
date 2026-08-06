# B3 — Zbuduj małą aplikację: Pomocnik do nauki

⏱️ **15 minut** · Ścieżka: 🅱️ Budowniczy · Potrzebne: Python + `anthropic` + klucz API

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (3 min)

Masz teraz dwa klocki: **pamięć** (B1) i **streaming** (B2). Połączmy je z **promptem systemowym** w prawdziwą, użyteczną aplikację: **Pomocnika do nauki**, który odpytuje Cię z dowolnego tematu, pamięta Twoje odpowiedzi i dostosowuje się.

To wzorzec większości prostych aplikacji AI:

```
prompt systemowy (osobowość/zasady aplikacji)
      +
pamięć (bieżąca lista messages)
      +
streaming (ładne wyjście na żywo)
      =
mała aplikacja
```

---

## 🛠️ Zbuduj to (10 min)

### Krok 1 — Utwórz aplikację

W folderze kursu:

```powershell
notepad study_buddy.py
```

### Krok 2 — Wklej ten kompletny program i zapisz

```python
import anthropic

client = anthropic.Anthropic()

SYSTEM = """Jesteś Pomocnikiem do nauki, przyjaznym korepetytorem-quizmasterem.

Zasady:
- Najpierw, jeśli temat nie jest ustalony, zapytaj użytkownika, czego się uczyć.
- Potem zadawaj JEDNO pytanie naraz i czekaj na odpowiedź.
- Po każdej odpowiedzi: powiedz, czy jest poprawna, daj jednoliniowe wyjaśnienie,
  potem zadaj następne pytanie, nieco trudniejsze, jeśli odpowiedział poprawnie.
- Bądź zachęcający i zwięzły. Śledź, ile odpowiedzi jest poprawnych.
- Jeśli użytkownik wpisze 'wynik', podaj, ile do tej pory poprawnych.
"""

messages = []

print("📚 Pomocnik do nauki — wpisz 'quit', aby przerwać, 'wynik' po wynik.\n")

# Zacznij, aby korepetytor zapytał o temat
messages.append({"role": "user", "content": "Zacznijmy."})

def stream_reply():
    print("Pomocnik: ", end="", flush=True)
    with client.messages.stream(
        model="claude-sonnet-5",
        max_tokens=500,
        system=SYSTEM,
        messages=messages,
    ) as stream:
        for text in stream.text_stream:
            print(text, end="", flush=True)
        reply = stream.get_final_message().content[0].text
    messages.append({"role": "assistant", "content": reply})
    print("\n")

stream_reply()  # pierwszy prompt: pyta o temat

while True:
    user_text = input("Ty: ")
    if user_text.strip().lower() in ("quit", "exit"):
        print("Dobra robota — do zobaczenia następnym razem! 👋")
        break
    messages.append({"role": "user", "content": user_text})
    stream_reply()
```

### Krok 3 — Uruchom i naucz się czegoś

```powershell
python study_buddy.py
```

Podaj mu temat („układ słoneczny”, „czasowniki hiszpańskie”, „podstawy Pythona”) i odpowiadaj na pytania. Zauważ, że:
- **pamięta** Twoje poprzednie odpowiedzi (pamięć),
- **streamuje** pytania (ładny UX),
- **pozostaje w roli** korepetytora (prompt systemowy).

Zbudowałeś prawdziwą aplikację AI. 🎉

---

## 🚀 Rozszerz ją (opcjonalnie, użyj Claude Code)

Otwórz plik w Claude Code (podstawowa Lekcja 13) i poproś:

```text
Dodaj komendę 'zapisz', która zapisuje całą rozmowę do pliku study-log.txt z dzisiejszą datą.
```
```text
Pozwól przekazać temat jako argument wiersza poleceń, abym mógł uruchomić: python study_buddy.py "słownictwo francuskie o jedzeniu".
```
```text
Zmień model na claude-haiku-4-5, aby oszczędzać koszt, i dodaj jednoliniową notatkę wyjaśniającą kompromis.
```

Opisujesz funkcje; AI je pisze; Ty przeglądasz i uruchamiasz.

---

## 🧩 Szkielet aplikacji wielokrotnego użytku

Każda mała aplikacja czatu, którą zbudujesz, używa tego kształtu:

```text
1. SYSTEM = "...zasady aplikacji..."
2. messages = []                     # pamięć
3. pętla:
     odczytaj wejście użytkownika
     dołącz do messages
     streamuj odpowiedź (z system=SYSTEM)
     dołącz odpowiedź do messages
```

Zmień prompt systemowy i masz inną aplikację: redaktor e-maili, pomocnik przepisów, objaśniacz kodu…

---

## ✅ Sprawdzenie

- [ ] `study_buddy.py` działa i Cię odpytuje.
- [ ] Pamięta wcześniejsze odpowiedzi i streamuje pytania.
- [ ] Potrafisz wyjaśnić szkielet system + pamięć + streaming.

---

## 🎯 Zadanie

Skopiuj `study_buddy.py` do nowego pliku i zmień **tylko prompt SYSTEM**, aby zrobić inną aplikację — np. „Redaktor e-maili” lub „Pomocnik przepisów”. Ten sam szkielet, nowy cel. Tak szybko możesz teraz wypuszczać małe narzędzia AI.

---

## 💡 Najważniejsze wnioski

- Mała aplikacja = **prompt systemowy + pamięć + streaming**.
- Zmień prompt systemowy → masz zupełnie inną aplikację z tego samego szkieletu.
- Rozwijaj funkcje, opisując je Claude Code.

🌐 [English](../../en/track-b/03-build-an-app.md) · [← Wstecz](02-streaming.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
