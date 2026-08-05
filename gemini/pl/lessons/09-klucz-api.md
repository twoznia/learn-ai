# Lekcja 09 — Zdobądź klucz API Google AI Studio

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: konto Google

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)

---

## 🧠 Teoria (3 min)

Dotąd *rozmawiałeś* z Gemini. Aby sprawić, że **Twój własny kod** będzie rozmawiał z Gemini, używasz **API** (Application Programming Interface) — drzwi w internecie, do których pukają Twoje programy.

Do korzystania z tych drzwi potrzebujesz **klucza API**: tajnego ciągu, który identyfikuje Twoje konto.

Dwa ważne fakty:

1. **Google AI Studio ma darmowy poziom.** Do nauki zwykle zdobędziesz klucz i wykonasz zapytania **bez dodawania płatności** (z limitami szybkości). Idealne na ten kurs. Płatne użycie jest dostępne, gdy potrzebujesz więcej.
2. **Klucz API to hasło.** Każdy, kto go ma, może zużywać Twój limit (a przy włączonych płatnościach — wydawać pieniądze). **Nigdy** go nie udostępniaj, nie wysyłaj e-mailem, nie publikuj na zrzutach ani w publicznym repozytorium GitHub.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Otwórz Google AI Studio

1. Wejdź na **https://aistudio.google.com**
2. Zaloguj się kontem Google i zaakceptuj warunki, jeśli poprosi.

> ℹ️ **Google AI Studio** (aistudio.google.com) to piaskownica dla programistów i menedżer kluczy. Różni się od aplikacji *czatu* (gemini.google.com).

### Krok 2 — Utwórz klucz API

1. Kliknij **Get API key** (lewy górny róg lub w menu).
2. Kliknij **Create API key**. Jeśli poprosi o wybór lub utworzenie projektu Google Cloud, zaakceptuj domyślny.
3. **Skopiuj klucz teraz** i przechowaj bezpiecznie na chwilę.

> Klucze darmowego poziomu działają od razu. Płatności potrzebujesz tylko, gdy przekroczysz darmowe limity (Lekcja 17).

### Krok 3 — Zapisz klucz bezpiecznie (jako zmienną środowiskową)

Nie wklejaj klucza do kodu. Zapisz go w Windows jako **zmienną środowiskową** o nazwie `GEMINI_API_KEY`. Twoje skrypty odczytają go automatycznie.

Otwórz **PowerShell** i uruchom (zamień na swój prawdziwy klucz):

```powershell
setx GEMINI_API_KEY "WKLEJ-TU-SWOJ-KLUCZ"
```

Zobaczysz `SUCCESS: Specified value was saved.`

> `setx` zapisuje go trwale dla przyszłych terminali. **Zamknij i otwórz ponownie PowerShell**, aby zadziałał.

### Krok 4 — Sprawdź, że zapisany

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:GEMINI_API_KEY
```

Powinieneś zobaczyć klucz. ✅ (Jeśli puste, otwórz ponownie PowerShell — `setx` działa tylko dla *nowych* okien.)

---

## 🔒 Zasady bezpieczeństwa klucza API

| ✅ Rób | ❌ Nie rób |
|------|---------|
| Przechowuj w zmiennej środowiskowej | Nie wpisuj na stałe w udostępniane skrypty |
| Obserwuj użycie/limity w AI Studio | Nie publikuj w czatach, zgłoszeniach ani repozytoriach |
| Usuń/zmień ujawniony klucz natychmiast | Nie wysyłaj e-mailem ani nie publikuj na zrzutach |
| Używaj jednego klucza na projekt | Nie używaj klucza, który mógł wyciec |

Jeśli klucz wycieknie: w AI Studio → **API keys** → **usuń/unieważnij go**, potem zrób nowy.

---

## ✅ Sprawdzenie

- [ ] Masz konto Google AI Studio.
- [ ] Utworzyłeś klucz API i skopiowałeś go.
- [ ] `setx GEMINI_API_KEY "..."` się powiodło.
- [ ] `echo $env:GEMINI_API_KEY` (w nowym oknie) pokazuje klucz.

---

## 🎯 Zadanie

W AI Studio otwórz **piaskownicę promptów** i wyślij jeden testowy prompt w przeglądarce — świetny sposób na wypróbowanie modeli przed pisaniem kodu. Zauważ, który model jest wybrany (np. `gemini-2.5-flash`).

---

## 💡 Najważniejsze wnioski

- **API** pozwala Twojemu kodowi używać Gemini; potrzebuje **klucza API** z Google AI Studio.
- Jest **darmowy poziom** — często bez płatności do nauki.
- Przechowuj klucz jako zmienną środowiskową `GEMINI_API_KEY` — nigdy w udostępnianym kodzie.
- Traktuj klucz jak hasło; rotuj go, jeśli wycieknie.

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)
