# Lekcja 09 — Zdobądź klucz API OpenAI

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: e-mail, możliwość doładowania niewielkiej kwoty

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)

---

## 🧠 Teoria (3 min)

Dotąd *rozmawiałeś* z ChatGPT. Aby sprawić, że **Twój własny kod** będzie rozmawiał z GPT, używasz **API** (Application Programming Interface) — drzwi w internecie, do których pukają Twoje programy.

Do korzystania z tych drzwi potrzebujesz **klucza API**: tajnego ciągu jak `sk-...`, który identyfikuje i rozlicza Twoje konto.

Dwa ważne fakty:

1. **API jest oddzielne od subskrypcji ChatGPT.** Użycie API to **płatność za zużycie** — doładowujesz małe saldo i płacisz za tokeny. Cały dzień nauki zwykle kosztuje kilka groszy.
2. **Klucz API to hasło.** Każdy, kto go ma, może wydawać Twoje pieniądze. **Nigdy** go nie udostępniaj, nie wysyłaj e-mailem, nie publikuj na zrzutach ani w publicznym repozytorium GitHub.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Otwórz OpenAI Platform

1. Wejdź na **https://platform.openai.com**
2. Zaloguj się / zarejestruj (możesz użyć tego samego loginu co ChatGPT).

> ℹ️ **Platform** (platform.openai.com) to panel *dla programistów* — klucze API i płatności. Różni się od aplikacji *czatu* (chatgpt.com).

### Krok 2 — Doładuj niewielką kwotę

1. Przejdź do **Settings → Billing**.
2. Dodaj małą kwotę — **5 $ w zupełności wystarczy** na cały kurs.
3. Rozważ ustawienie **limitu użycia** (np. 5 $/miesiąc), aby nic Cię nie zaskoczyło. Zrób to — to spokój ducha.

### Krok 3 — Utwórz klucz API

1. Przejdź do **API keys** (w menu panelu).
2. Kliknij **Create new secret key**. Nazwij go np. `kurs-learn-ai`.
3. **Skopiuj klucz teraz** — zwykle nie zobaczysz go ponownie po zamknięciu okna. Jeśli go zgubisz, po prostu utwórz nowy.

### Krok 4 — Zapisz klucz bezpiecznie (jako zmienną środowiskową)

Nie wklejaj klucza do kodu. Zapisz go w Windows jako **zmienną środowiskową** o nazwie `OPENAI_API_KEY`. Twoje skrypty odczytają go automatycznie.

Otwórz **PowerShell** i uruchom (zamień na swój prawdziwy klucz):

```powershell
setx OPENAI_API_KEY "sk-WKLEJ-TU-SWOJ-KLUCZ"
```

Zobaczysz `SUCCESS: Specified value was saved.`

> `setx` zapisuje go trwale dla przyszłych terminali. **Zamknij i otwórz ponownie PowerShell**, aby zadziałał.

### Krok 5 — Sprawdź, że zapisany

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:OPENAI_API_KEY
```

Powinieneś zobaczyć klucz. ✅ (Jeśli puste, otwórz ponownie PowerShell — `setx` działa tylko dla *nowych* okien.)

---

## 🔒 Zasady bezpieczeństwa klucza API

| ✅ Rób | ❌ Nie rób |
|------|---------|
| Przechowuj w zmiennej środowiskowej | Nie wpisuj na stałe w udostępniane skrypty |
| Ustaw limit użycia/wydatków | Nie publikuj w czatach, zgłoszeniach ani repozytoriach |
| Usuń/zmień ujawniony klucz natychmiast | Nie wysyłaj e-mailem ani nie publikuj na zrzutach |
| Używaj jednego klucza na projekt | Nie używaj klucza, który mógł wyciec |

Jeśli klucz wycieknie: Platform → **API keys** → **unieważnij go**, potem zrób nowy.

---

## ✅ Sprawdzenie

- [ ] Masz konto Platform z małym saldem kredytu.
- [ ] Utworzyłeś klucz API i skopiowałeś go.
- [ ] `setx OPENAI_API_KEY "..."` się powiodło.
- [ ] `echo $env:OPENAI_API_KEY` (w nowym oknie) pokazuje klucz.
- [ ] Ustawiłeś limit użycia.

---

## 🎯 Zadanie

Upewnij się, że limit użycia jest ustawiony. Potem otwórz stronę **Usage** na Platform, żeby wiedzieć, gdzie później obserwować wydatki.

---

## 💡 Najważniejsze wnioski

- **API** pozwala Twojemu kodowi używać GPT; potrzebuje **klucza API** z platform.openai.com.
- Rozliczanie API to **płatność za zużycie**, oddzielna od subskrypcji ChatGPT.
- Przechowuj klucz jako zmienną środowiskową `OPENAI_API_KEY` — nigdy w udostępnianym kodzie.
- Traktuj klucz jak hasło; ustaw limit wydatków.

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)
