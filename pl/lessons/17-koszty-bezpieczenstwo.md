# Lekcja 17 — Koszty, limity, prywatność i bezpieczeństwo

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: nic do zainstalowania

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)

---

## 🧠 Teoria (5 min)

### Jak działa cennik AI

Aplikacje czatu (claude.ai, Claude Desktop) używają **subskrypcji**: darmowy poziom lub płatny plan **Pro** dla większego użycia. Prosto i przewidywalnie.

**API** (Twój kod w Pythonie/PowerShell) to **płatność za zużycie**, rozliczana **za token**. Pamiętaj: token ≈ ¾ słowa. Płacisz osobno za **wejście** (co wysyłasz) i **wyjście** (co Claude odpisuje).

Orientacyjne ceny API (za **milion** tokenów — zwykle użyjesz tylko tysięcy):

| Model | Wejście / 1M tokenów | Wyjście / 1M tokenów | Charakter |
|-------|-------------------|--------------------|------|
| **Haiku** (`claude-haiku-4-5`) | ~1 $ | ~5 $ | Najtańszy, szybki |
| **Sonnet** (`claude-sonnet-5`) | ~3 $ | ~15 $ | Zrównoważony |
| **Opus** (`claude-opus-5`) | ~5 $ | ~25 $ | Najbardziej zdolny |

> Milion tokenów to *dużo* — mniej więcej 750 000 słów. Typowe zapytanie do nauki (kilkaset słów w każdą stronę) kosztuje **drobny ułamek grosza**. Ceny zmieniają się z czasem; sprawdź aktualne na **console.anthropic.com**.

### Utrzymywanie niskich kosztów (nawyki)

- **Używaj Haiku do nauki i prostych zadań.** Przełączaj wyżej tylko w razie potrzeby.
- **Ustawiaj `max_tokens` rozsądnie** — ogranicza długość wyjścia (i koszt).
- **Ustaw miesięczny limit wydatków** w Console (zrobiłeś to w Lekcji 9).
- **Obserwuj stronę Usage** w Console, by widzieć realne wydatki.

### Limity i okno kontekstu

- **Limity szybkości (rate limits)**: ile możesz wysłać na minutę. Jeśli je osiągniesz, poczekaj chwilę i spróbuj ponownie. Oficjalne biblioteki ponawiają automatycznie.
- **Okno kontekstu**: ile tekstu Claude widzi naraz. Współczesne modele Claude mają bardzo duże okna, ale ogromne wejścia i tak kosztują więcej — wysyłaj tylko to, co istotne.

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

AI może **halucynować** — pewnie podawać rzeczy błędne. Zawsze weryfikuj:
- **Liczby, daty, przepisy, porady medyczne/finansowe** → sprawdź dwukrotnie.
- **Cytaty, źródła, linki** → potwierdź, że są prawdziwe.
- Dodawaj do promptów: *„Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.”*

### Twój klucz API = hasło

- Przechowuj jako zmienną środowiskową `ANTHROPIC_API_KEY` (Lekcja 9), nigdy w kodzie, który udostępniasz.
- **Nigdy** nie wklejaj go w miejscu publicznym (GitHub, fora, zrzuty ekranu).
- Jeśli wycieknie: wejdź do Console → **API Keys** → usuń go, zrób nowy.

### Używaj AI odpowiedzialnie

- Nie używaj AI do oszukiwania, nękania ani podszywania się.
- Przypisuj autorstwo, gdy trzeba; sprawdzaj zasady szkoły/pracy.
- Traktuj wyjście AI jak pomocny **szkic**, a nie ostateczny autorytet — *Ty* odpowiadasz za to, co publikujesz.

---

## 🧮 Szybkie sprawdzenie kosztu

Chcesz oszacować przed uruchomieniem kodu? Zapytaj samego Claude:

```text
Jeśli wyślę około 500 słów i dostanę z powrotem około 800 słów używając Claude Haiku,
mniej więcej ile to tokenów i jaki orientacyjny koszt? Pokaż obliczenia.
```

Przeprowadzi Cię przez to. (Potem zweryfikuj aktualną cenę w Console.)

---

## ✅ Sprawdzenie

- [ ] Potrafisz wyjaśnić subskrypcję vs płatność za zużycie.
- [ ] Wiesz, że Haiku < Sonnet < Opus pod względem kosztu.
- [ ] Masz ustawiony miesięczny limit wydatków.
- [ ] Wiesz, czego nigdy nie udostępniać i by weryfikować ważne fakty.

---

## 🎯 Zadanie

Otwórz stronę **Usage** na console.anthropic.com i zobacz, ile do tej pory kosztowała Twoja nauka (prawdopodobnie grosze). Potwierdź, że limit wydatków jest ustawiony. Spokój ducha odblokowany.

---

## 💡 Najważniejsze wnioski

- Czat = subskrypcja; API = płatność za token (Haiku najtańszy, Opus najdroższy).
- Kontroluj koszt przez Haiku, `max_tokens` i limit wydatków.
- Nigdy nie udostępniaj sekretów ani cudzych danych; weryfikuj ważne fakty.
- Twój klucz API to hasło — chroń go i rotuj.

🌐 [English](../../en/lessons/17-costs-safety.md) · [← Wstecz](16-prompt-engineering.md) · [Strona kursu](../README.md) · [Dalej: Co dalej →](18-co-dalej.md)
