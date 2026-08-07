# G5 — Tryb bezobsługowy i automatyzacja

⏱️ **15 minut** · Ścieżka: 🅶 Codex CLI w głąb · Wymagania: Codex CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/05-headless-mode-and-automation.md) · [← Poprzedni](04-bezpieczna-edycja-z-git.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)

---

## 🧠 Teoria (4 min)

Wszystko dotąd było **interaktywne** — Ty i Codex, tam i z powrotem. Ale Codex może też działać **bezobsługowo**: dajesz mu zadanie w **jednym poleceniu**, on wykonuje pracę i wypisuje wynik, potem kończy. Bez czatu.

To odblokowuje **automatyzację**. Polecenie bezobsługowe może trafić do:

- **Skryptu**, który uruchamia kilka kroków po kolei.
- **Zaplanowanego zadania** (jak potoki w Ścieżce C).
- **Git hooka** lub kroku CI, który sprawdza lub podsumowuje zmiany.

Polecenie to `codex exec` (czasem pokazywane jako tryb nieinteraktywny/`exec`) — ciąg zadania na wejściu, wynik na wyjściu.

> Dokładne nazwy flag i opcje wyjścia zmieniają się z czasem. Sprawdź `codex --help` i bieżącą dokumentację; *wzorzec* — jedno polecenie, jeden wynik — jest tym, co się liczy.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Uruchom jedno zadanie, nieinteraktywnie

Z folderu projektu:

```powershell
codex exec "Podsumuj, co robi ten projekt, w trzech zdaniach."
```

Uruchamia się raz i wypisuje odpowiedź — bez sesji do zarządzania.

### Krok 2 — Trzymaj to bezpiecznie z piaskownicą

Tryb bezobsługowy wciąż respektuje zabezpieczenia z G2. Do automatyzacji tylko-do-odczytu uruchom go w trybie tylko-do-odczytu, by nic nie mógł zmienić:

```powershell
codex exec --sandbox read-only "Wylistuj wszelkie komentarze TODO i gdzie są."
```

> Dopasuj tryb do zadania: **read-only** do raportowania/podsumowań; tryb z zapisem tylko wtedy, gdy zadanie *powinno* zmienić pliki — i tylko gdzieś zabezpieczonym Gitem (G4).

### Krok 3 — Podaj mu własne dane

Przekaż treść przez potok lub wskaż na pliki, by pracował na *Twoim* materiale:

```powershell
git diff | codex exec "Napisz zwięzły komunikat commita dla tego diffa."
```

Jedno polecenie zamienia Twój diff w gotowy do użycia komunikat.

### Krok 4 — Umieść to w małym skrypcie

Połącz kroki w plik `.ps1`:

```powershell
# review.ps1 — szybki automatyczny przegląd bieżących zmian
codex exec --sandbox read-only "Przejrzyj bieżące zmiany git i wypisz ryzyka jako punkty."
```

Uruchamiaj kiedykolwiek przez `./review.ps1`. Tu G1–G4 się opłacają: **AGENTS.md** daje kontekst, **config** ustawia domyślne, **prompty** są wielokrotnego użytku, a **git** trzyma to bezpiecznie — wszystko w jednej automatycznej linii.

### Krok 5 — Zaplanuj to (powiązanie ze Ścieżką C)

Wskaż **Harmonogram zadań** Windows na swój skrypt (dokładnie jak potoki w Ścieżce C) dla codziennego podsumowania, nocnego przeglądu lub tygodniowego raportu — generowanego, gdy śpisz.

### Krok 6 — Wiedz, kiedy *nie* automatyzować

Tryb bezobsługowy jest najlepszy do **powtarzalnych, niskiego ryzyka** zadań (podsumowania, przeglądy, raporty). Dla czegokolwiek niejednoznacznego, kreatywnego lub wysokiej stawki pozostań **interaktywny**, byś mógł/mogła kierować.

---

## 🧩 Interaktywny vs bezobsługowy

| | Interaktywny | Bezobsługowy (`codex exec`) |
|--|-------------|--------------------------|
| Kształt | Czat tam i z powrotem | Jedno polecenie → jeden wynik |
| Najlepszy do | Eksploracji, budowy, kierowania | Podsumowań, przeglądów, skryptowych zadań |
| Pasuje do | Twojej sesji roboczej | Skryptów, harmonogramów, hooków |
| Bezpieczeństwo | Obserwujesz każdy krok | Ustaw tryb piaskownicy + polegaj na Git |

---

## ✅ Sprawdzian

- [ ] Uruchomiłeś/aś zadanie przez `codex exec` i dostałeś/aś jednorazowy wynik.
- [ ] Uruchomiłeś/aś bezpiecznie zadanie bezobsługowe tylko-do-odczytu.
- [ ] Przekazałeś/aś własne dane (np. diff) przez potok do polecenia bezobsługowego.
- [ ] Umieściłeś/aś jedno polecenie bezobsługowe w małym skrypcie i wiesz, kiedy pozostać interaktywnym.

---

## 🎯 Praca domowa

Napisz mały skrypt uruchamiający zadanie bezobsługowe Codeksa, którego naprawdę byś użył/a — pomocnik diff-na-komunikat-commita, lister TODO lub recenzent zmian. Uruchom go tylko-do-odczytu. Opcjonalnie zaplanuj go Harmonogramem zadań (Ścieżka C). Właśnie zautomatyzowałeś/aś własnego asystenta AI.

---

## 💡 Najważniejsze wnioski

- **`codex exec`** uruchamia zadanie **bezobsługowo** — jedno polecenie na wejściu, jeden wynik na wyjściu — do skryptów, harmonogramów i hooków.
- Trzymaj to bezpiecznie: wybierz **tryb piaskownicy** pasujący do zadania (read-only do raportów) i opieraj się na **Git** (G4).
- Automatyzuj **powtarzalną, niskiego ryzyka** pracę; pozostań **interaktywny** przy czymkolwiek niejednoznacznym lub wysokiej stawki.

🌐 [English](../../en/track-g/05-headless-mode-and-automation.md) · [← Poprzedni](04-bezpieczna-edycja-z-git.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)
