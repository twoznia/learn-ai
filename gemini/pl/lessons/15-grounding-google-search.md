# Lekcja 15 — Ugruntowanie w Wyszukiwarce Google

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: Python + klucz API (lub aplikacja Gemini)

🌐 [English](../../en/lessons/15-grounding-google-search.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Teoria (4 min)

LLM „zna” tylko to, czego nauczył się podczas treningu, więc może być nieaktualny lub coś zmyślić. **Ugruntowanie (grounding)** to naprawia, łącząc odpowiedź Gemini z **żywymi źródłami** — najsilniej z **Wyszukiwarką Google**.

Gdy ugruntowanie jest włączone, Gemini może **szukać w sieci podczas odpowiadania**, potem opiera odpowiedź na tym, co znalazł, i pokazuje źródła. To sztandarowa funkcja Gemini i odpowiedź Google na pytanie „jak zaufać odpowiedzi?”.

Dlaczego to ważne dla początkujących:
- Pytaj o **niedawne wydarzenia, ceny, wersje** — rzeczy, których dane treningowe nie znają.
- Otrzymuj odpowiedzi **z linkami**, które możesz zweryfikować.
- Ograniczaj halucynacje przy pytaniach faktycznych.

> ⚠️ Ugruntowanie to nadal nie magia — źródła też bywają błędne. Czytaj cytowane linki przy wszystkim, co ważne.

---

## 🛠️ Praktyka (5 min)

### Ścieżka A — W aplikacji Gemini (bez kodu)

1. Otwórz **gemini.google.com**.
2. Zadaj pytanie wymagające świeżych informacji, np.:

```text
Jakie są 3 niedawne, warte uwagi wydarzenia w świecie samochodów elektrycznych w tym miesiącu? Podaj źródła.
```

3. Poszukaj **linków/cytowań źródeł** w odpowiedzi i kliknij jedno, aby zweryfikować. Wiele odpowiedzi już używa Google pod maską.

### Ścieżka B — W Pythonie (włącz ugruntowanie Search)

Biblioteka Google pozwala podłączyć Wyszukiwarkę Google jako **narzędzie**. Utwórz `grounded.py`:

```powershell
cd $HOME\learn-ai-gemini
notepad grounded.py
```

Wklej i zapisz:

```python
from google import genai
from google.genai import types

client = genai.Client()

# Włącz narzędzie Wyszukiwarki Google, aby Gemini mógł szukać na żywo
grounding_tool = types.Tool(google_search=types.GoogleSearch())

response = client.models.generate_content(
    model="gemini-2.5-flash",
    config=types.GenerateContentConfig(tools=[grounding_tool]),
    contents="Kto wygrał ostatni wyścig Formuły 1 i kiedy się odbył? Odpowiedz krótko.",
)

print(response.text)
```

Uruchom:

```powershell
python grounded.py
```

Gemini szuka, potem odpowiada aktualnymi informacjami. 🎉 Porównaj to z pytaniem **bez** narzędzia — nieugruntowana odpowiedź może być nieaktualna lub asekuracyjna.

### Wypróbuj oba

Uruchom to samo pytanie z `tools=[grounding_tool]` i bez. Zobaczenie różnicy to cały sens: ugruntowanie = świeższe, poparte źródłami odpowiedzi.

---

## 🧭 Kiedy używać ugruntowania

| Używaj ugruntowania do… | Pomiń przy… |
|--------------------|--------------|
| Niedawnych wiadomości, cen, premier | Ponadczasowych wyjaśnień („czym jest ułamek”) |
| Pytań „na dziś…” | Twórczego pisania / burzy mózgów |
| Faktów, na których podstawie działasz | Przeredagowywania własnego tekstu |

---

## ✅ Sprawdzenie

- [ ] Zadałeś pytanie o „świeże info” w aplikacji i sprawdziłeś źródło.
- [ ] Uruchomiłeś `grounded.py` z narzędziem Wyszukiwarki Google.
- [ ] Porównałeś odpowiedzi ugruntowane i nieugruntowane.

---

## 🎯 Zadanie

Wybierz pytanie, którego odpowiedź niedawno się zmieniła (najnowsza wersja produktu, aktualna cena). Zapytaj Gemini z ugruntowaniem, potem kliknij źródło, aby potwierdzić. Ten krok weryfikacji odróżnia mądrych użytkowników AI od reszty.

---

## 💡 Najważniejsze wnioski

- **Ugruntowanie** łączy odpowiedzi Gemini z żywymi źródłami jak Wyszukiwarka Google.
- W kodzie dodaj `types.Tool(google_search=types.GoogleSearch())` do konfiguracji.
- Używaj do świeżych/faktycznych pytań; nadal klikaj źródła przy wszystkim, co ważne.

🌐 [English](../../en/lessons/15-grounding-google-search.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)
