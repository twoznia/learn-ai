# Lekcja 17 — Koszty, limity, prywatność i bezpieczeństwo

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: nic do zainstalowania

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)

---

## 🧠 Teoria (5 min)

### Jak działa cennik Gemini

**Aplikacja Gemini** (gemini.google.com) używa **subskrypcji**: darmowy poziom lub plany płatne (Google AI Pro/Ultra, często przez Google One) dla większego użycia i najlepszych modeli. Prosto i przewidywalnie.

**API** (Twój kod w Pythonie/PowerShell) ma **darmowy poziom** *i* płatność za zużycie:

- **Darmowy poziom (Google AI Studio):** wykonuj zapytania **bez płatności**, z limitami szybkości. Świetne do nauki — spora część kursu nic nie kosztuje.
- **Poziom płatny:** gdy przekroczysz darmowe limity, płacisz **za token** (token ≈ ¾ słowa), osobno za wejście i wyjście.

Orientacyjny relatywny koszt (Flash-Lite < Flash < Pro):

| Model | Koszt | Charakter |
|-------|------|------|
| **Flash-Lite** (`gemini-2.5-flash-lite`) | Najtańszy | Najszybszy, proste zadania |
| **Flash** (`gemini-2.5-flash`) | Niski | Zrównoważony, codzienny |
| **Pro** (`gemini-2.5-pro`) | Najwyższy | Najbardziej zdolny |

> Dokładne ceny i limity darmowego poziomu zmieniają się. Sprawdź aktualne na **https://ai.google.dev/pricing**.

### Utrzymywanie niskich kosztów (nawyki)

- **Zacznij na darmowym poziomie** i używaj **Flash** do nauki.
- **Nie dodawaj płatności**, dopóki naprawdę nie osiągniesz darmowych limitów.
- Obserwuj użycie w **Google AI Studio**.
- Trzymaj prompty skupione — ogromne wejścia zużywają więcej tokenów.

### Limity i okno kontekstu

- **Limity szybkości**: ile zapytań na minutę pozwala darmowy poziom. Jeśli osiągniesz, poczekaj i spróbuj ponownie.
- **Okno kontekstu**: ile tekstu Gemini widzi naraz — u Gemini jest bardzo duże, ale większe wejścia i tak kosztują więcej na poziomie płatnym.

---

## 🔒 Prywatność i bezpieczeństwo (5 min)

### Czego NIE udostępniać AI

| ❌ Nie udostępniaj | Dlaczego |
|---------------|-----|
| Haseł, kluczy API, sekretów | Mogą zostać ujawnione lub nadużyte |
| Cudzych danych prywatnych | Możesz nie mieć pozwolenia |
| Informacji poufnych/służbowych | Najpierw sprawdź zasady pracodawcy |
| Pełnych danych finansowych/medycznych | Udostępniaj tylko to, co konieczne |

### Ufaj, ale weryfikuj

AI może **halucynować**. Zawsze weryfikuj:
- **Liczby, daty, przepisy, porady medyczne/finansowe** → sprawdź dwukrotnie.
- **Cytaty, źródła, linki** → potwierdź, że są prawdziwe (ugruntowanie pomaga — Lekcja 15).
- Dodawaj do promptów: *„Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.”*

### Twój klucz API = hasło

- Przechowuj jako zmienną środowiskową `GEMINI_API_KEY` (Lekcja 9), nigdy w udostępnianym kodzie.
- **Nigdy** nie wklejaj go w miejscu publicznym (GitHub, fora, zrzuty ekranu).
- Jeśli wycieknie: Google AI Studio → **API keys** → usuń go, zrób nowy.

### Używaj AI odpowiedzialnie

- Nie używaj AI do oszukiwania, nękania ani podszywania się.
- Przypisuj autorstwo, gdy trzeba; sprawdzaj zasady szkoły/pracy.
- Traktuj wyjście AI jak pomocny **szkic**, a nie ostateczny autorytet — *Ty* odpowiadasz za to, co publikujesz.

---

## 🧮 Szybkie sprawdzenie kosztu

Chcesz oszacować przed uruchomieniem kodu? Zapytaj samego Gemini:

```text
Jeśli wyślę około 500 słów i dostanę z powrotem około 800 słów używając Gemini 2.5 Flash,
mniej więcej ile to tokenów? Potem przypomnij mi, żebym sprawdził ai.google.dev/pricing dla aktualnej stawki.
```

---

## ✅ Sprawdzenie

- [ ] Potrafisz wyjaśnić darmowy poziom vs płatność za zużycie.
- [ ] Wiesz, że Flash-Lite < Flash < Pro pod względem kosztu.
- [ ] Wiesz, gdzie sprawdzić ceny (ai.google.dev/pricing).
- [ ] Wiesz, czego nigdy nie udostępniać i by weryfikować ważne fakty.

---

## 🎯 Zadanie

Otwórz **Google AI Studio** i znajdź, gdzie pokazane jest użycie/limity. Potwierdź, że jesteś na darmowym poziomie i nie włączyłeś przypadkiem płatności, których nie potrzebujesz.

---

## 💡 Najważniejsze wnioski

- Aplikacja = subskrypcja; API = **darmowy poziom** + płatność za token (Flash-Lite najtańszy, Pro najdroższy).
- Ucz się na darmowym poziomie z Flash; dodawaj płatności tylko w razie potrzeby.
- Nigdy nie udostępniaj sekretów ani cudzych danych; weryfikuj ważne fakty.
- Twój klucz API to hasło — chroń go i rotuj.

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)
