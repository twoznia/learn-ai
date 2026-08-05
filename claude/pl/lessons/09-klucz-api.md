# Lekcja 09 — Zdobądź klucz API Anthropic

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: e-mail, możliwość doładowania niewielkiej kwoty

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)

---

## 🧠 Teoria (3 min)

Dotąd *rozmawiałeś* z Claude. Aby sprawić, że **Twój własny kod** będzie rozmawiał z Claude, używasz **API** (Application Programming Interface) — drzwi w internecie, do których pukają Twoje programy.

Do korzystania z tych drzwi potrzebujesz **klucza API**: długiego, tajnego ciągu jak `sk-ant-...`, który identyfikuje i rozlicza Twoje konto.

Dwa bardzo ważne fakty:

1. **API jest oddzielne od Twojego planu czatu Claude.ai.** Użycie API to **płatność za faktyczne zużycie** — doładowujesz kilka dolarów kredytu i płacisz za tokeny. Cały dzień nauki zwykle kosztuje kilka groszy. (Szczegóły w Lekcji 17.)
2. **Klucz API to hasło.** Każdy, kto go ma, może wydawać Twoje pieniądze. **Nigdy** go nie udostępniaj, nie wysyłaj e-mailem, nie publikuj na zrzutach ekranu ani w publicznym repozytorium GitHub.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Załóż konto w Console

1. Wejdź na **https://console.anthropic.com**
2. Zarejestruj się / zaloguj (możesz użyć tego samego e-maila co na claude.ai).

> ℹ️ **Console** (console.anthropic.com) to panel *dla programistów*. Różni się od aplikacji *czatu* (claude.ai). Tu zarządzasz kluczami API i płatnościami.

### Krok 2 — Doładuj niewielką kwotę

1. W Console znajdź **Billing** (lub **Plans & Billing**).
2. Dodaj małą kwotę — **5 $ w zupełności wystarczy** na cały kurs.
3. Możesz też ustawić **miesięczny limit wydatków** (np. 5 $), aby nic Cię nie zaskoczyło. Zrób to — to spokój ducha.

### Krok 3 — Utwórz klucz API

1. Przejdź do **API Keys** (w ustawieniach / menu bocznym).
2. Kliknij **Create Key**. Nazwij go np. `kurs-learn-ai`.
3. **Skopiuj klucz teraz** — zwykle nie zobaczysz go ponownie po zamknięciu okna. Jeśli go zgubisz, po prostu utwórz nowy.

### Krok 4 — Zapisz klucz bezpiecznie (jako zmienną środowiskową)

Nie wklejaj klucza do kodu. Zapisz go w Windows jako **zmienną środowiskową** o nazwie `ANTHROPIC_API_KEY`. Twoje skrypty odczytają go automatycznie.

Otwórz **PowerShell** i uruchom (zamień na swój prawdziwy klucz):

```powershell
setx ANTHROPIC_API_KEY "sk-ant-WKLEJ-TU-SWOJ-KLUCZ"
```

Zobaczysz `SUCCESS: Specified value was saved.`

> `setx` zapisuje go trwale dla przyszłych terminali. **Zamknij i otwórz ponownie PowerShell**, aby zadziałał.

### Krok 5 — Sprawdź, że zapisany

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:ANTHROPIC_API_KEY
```

Powinieneś zobaczyć swój klucz. ✅ (Jeśli puste, otwórz ponownie PowerShell — `setx` działa tylko dla *nowych* okien.)

---

## 🔒 Zasady bezpieczeństwa klucza API

| ✅ Rób | ❌ Nie rób |
|------|---------|
| Przechowuj w zmiennej środowiskowej | Nie wpisuj na stałe w skrypty, które udostępniasz |
| Ustaw miesięczny limit wydatków | Nie publikuj w czatach, zgłoszeniach ani repozytoriach |
| Usuń/zmień ujawniony klucz natychmiast | Nie wysyłaj e-mailem ani nie publikuj na zrzutach |
| Używaj jednego klucza na projekt | Nie używaj klucza, który mógł wyciec |

Jeśli klucz kiedykolwiek wycieknie: wejdź do Console → API Keys → **usuń/unieważnij go**, potem zrób nowy. Gotowe.

---

## ✅ Sprawdzenie

- [ ] Masz konto w Console z małym saldem kredytu.
- [ ] Utworzyłeś klucz API i skopiowałeś go.
- [ ] `setx ANTHROPIC_API_KEY "..."` się powiodło.
- [ ] `echo $env:ANTHROPIC_API_KEY` (w nowym oknie) pokazuje klucz.
- [ ] Ustawiłeś miesięczny limit wydatków.

---

## 🎯 Zadanie

Upewnij się, że limit wydatków jest ustawiony. Potem przeczytaj jedną linię na stronie **Usage** w Console, żeby wiedzieć, gdzie później obserwować wydatki.

---

## 💡 Najważniejsze wnioski

- **API** pozwala Twojemu kodowi używać Claude; potrzebuje **klucza API**.
- Rozliczanie API to **płatność za zużycie**, oddzielna od planów czatu.
- Przechowuj klucz jako zmienną środowiskową `ANTHROPIC_API_KEY` — nigdy w udostępnianym kodzie.
- Traktuj klucz jak hasło; ustaw limit wydatków.

🌐 [English](../../en/lessons/09-get-api-key.md) · [← Wstecz](08-instalacja-python.md) · [Strona kursu](../README.md) · [Dalej: Pierwszy skrypt →](10-python-pierwszy-skrypt.md)
