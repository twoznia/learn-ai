# Lekcja 17 — Koszty, limity, prywatność i bezpieczeństwo

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: nic do zainstalowania

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)

---

## 🧠 Teoria (5 min)

### Jak działa cennik

**Aplikacja ChatGPT** używa **subskrypcji**: darmowy poziom lub plany płatne (Plus/Pro) dla większego użycia i najlepszych modeli. Prosto i przewidywalnie.

**API** (Twój kod w Pythonie/PowerShell) to **płatność za zużycie**, rozliczana **za token** (token ≈ ¾ słowa), osobno za wejście i wyjście. Doładowujesz małe saldo i maleje ono w miarę użycia.

Orientacyjny relatywny koszt (mini/nano < flagowy):

| Model | Koszt | Charakter |
|-------|------|------|
| **nano / mini** (np. `gpt-5-mini`) | Najtańszy | Szybki, proste zadania |
| **flagowy** (np. `gpt-5`) | Wyższy | Najbardziej zdolny |

> Typowe zapytanie do nauki (kilkaset słów w każdą stronę) kosztuje **drobny ułamek grosza**. Dokładne ceny się zmieniają — sprawdź aktualne na **https://openai.com/api/pricing**.

### Utrzymywanie niskich kosztów (nawyki)

- **Używaj modelu mini** do nauki; przełączaj wyżej tylko w razie potrzeby.
- **Ustaw limit użycia** na Platform (zrobiłeś to w Lekcji 9).
- **Obserwuj stronę Usage** na platform.openai.com.
- Trzymaj prompty skupione — ogromne wejścia zużywają więcej tokenów.

### Limity i okno kontekstu

- **Limity szybkości**: ile możesz wysłać na minutę. Jeśli osiągniesz, poczekaj i spróbuj ponownie (oficjalne biblioteki ponawiają automatycznie).
- **Okno kontekstu**: ile tekstu GPT widzi naraz. Duże wejścia i tak kosztują więcej — wysyłaj tylko to, co istotne.

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
- **Cytaty, źródła, linki** → potwierdź, że są prawdziwe (wyszukiwanie pomaga — Lekcja 15).
- Dodawaj do promptów: *„Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.”*

### Twój klucz API = hasło

- Przechowuj jako zmienną środowiskową `OPENAI_API_KEY` (Lekcja 9), nigdy w udostępnianym kodzie.
- **Nigdy** nie wklejaj go w miejscu publicznym (GitHub, fora, zrzuty ekranu).
- Jeśli wycieknie: Platform → **API keys** → unieważnij go, zrób nowy.

### Używaj AI odpowiedzialnie

- Nie używaj AI do oszukiwania, nękania ani podszywania się.
- Przypisuj autorstwo, gdy trzeba; sprawdzaj zasady szkoły/pracy.
- Traktuj wyjście AI jak pomocny **szkic**, a nie ostateczny autorytet — *Ty* odpowiadasz za to, co publikujesz.

---

## 🧮 Szybkie sprawdzenie kosztu

Chcesz oszacować przed uruchomieniem kodu? Zapytaj samego ChatGPT:

```text
Jeśli wyślę około 500 słów i dostanę z powrotem około 800 słów używając małego modelu GPT,
mniej więcej ile to tokenów? Potem przypomnij mi, żebym sprawdził openai.com/api/pricing dla aktualnej stawki.
```

---

## ✅ Sprawdzenie

- [ ] Potrafisz wyjaśnić subskrypcję vs płatność za zużycie.
- [ ] Wiesz, że mini/nano < flagowy pod względem kosztu.
- [ ] Masz ustawiony limit użycia.
- [ ] Wiesz, czego nigdy nie udostępniać i by weryfikować ważne fakty.

---

## 🎯 Zadanie

Otwórz stronę **Usage** na platform.openai.com i zobacz, ile do tej pory kosztowała Twoja nauka (prawdopodobnie grosze). Potwierdź, że limit użycia jest ustawiony. Spokój ducha odblokowany.

---

## 💡 Najważniejsze wnioski

- Aplikacja = subskrypcja; API = płatność za token (mini najtańszy, flagowy najdroższy).
- Kontroluj koszt przez model mini, skupione prompty i limit użycia.
- Nigdy nie udostępniaj sekretów ani cudzych danych; weryfikuj ważne fakty.
- Twój klucz API to hasło — chroń go i rotuj.

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)
