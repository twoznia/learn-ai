# D5 — Agenci i Codex CLI na Twoim planie

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Wymagania: konto ChatGPT Plus/Pro, Node.js (z kursu dla początkujących)

🌐 [English](../../en/track-d/05-agents-and-codex-cli.md) · [← Poprzedni](04-instrukcje-wlasne-i-pamiec.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)

---

## 🧠 Teoria (5 min)

Dotąd GPT odpowiadał na pytania i tworzył pliki. **Agent** idzie dalej: mając cel, **planuje, wykonuje kroki, używa narzędzi, sprawdza swoją pracę i kontynuuje**, aż zadanie jest gotowe — z Twoim zatwierdzaniem po drodze.

Najbardziej użytecznym agentem dla większości ludzi jest **Codex CLI** — GPT pracujący bezpośrednio z plikami i poleceniami na Twoim komputerze. Kluczowy fakt tej ścieżki: **możesz zalogować się kontem ChatGPT**, więc użycie Codeksa pochodzi z Twojego **planu Plus/Pro** — bez osobnego klucza API ani rachunku za tokeny na start.

Dwa sposoby myślenia o pracy agentowej:

- **W aplikacji** — ChatGPT już łączy kroki: planuje, używa Deep Research i Zaawansowanej analizy danych i przechodzi przez wieloczęściowe żądanie za jednym razem.
- **Na Twojej maszynie** — Codex CLI czyta i edytuje prawdziwe pliki, uruchamia polecenia i iteruje, pod Twoim zatwierdzeniem.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zainstaluj Codex CLI

W **PowerShell**:

```powershell
npm install -g @openai/codex
```

(Jeśli `npm` nie jest znaleziony, najpierw zainstaluj Node.js z kursu dla początkujących.)

### Krok 2 — Zaloguj się kontem ChatGPT

Przejdź do folderu, w którym chcesz pracować, i uruchom:

```powershell
mkdir $HOME\codex-demo
cd $HOME\codex-demo
codex
```

Przy pierwszym uruchomieniu zapyta, jak się zalogować. **Wybierz „Sign in with ChatGPT"**, by używać planu Plus/Pro (zamiast wklejać klucz API). Otworzy się przeglądarka; zatwierdź. Teraz Codex działa na Twoim **abonamencie** — bez dodatkowych opłat na start.

> Jeśli oferuje też opcję klucza API: to droga deweloperska/licznikowa. W tej ścieżce użyj **logowania ChatGPT**.

### Krok 3 — Daj mu mały cel

Wpisz zadanie zwykłym językiem:

```text
Utwórz plik notes.md z trzema sekcjami: Cele, Dziś, Później.
Następnie dodaj trzy przykładowe punkty pod Dziś.
```

Obserwuj, jak **planuje**, proponuje zmianę i prosi o pozwolenie przed zapisem. Zatwierdź i sprawdź, że plik się pojawił. Właśnie uruchomiłeś/aś agenta na prawdziwych plikach.

### Krok 4 — Pozwól mu iterować

```text
Teraz dodaj sekcję „Zrobione" na górze i przenieś do niej jeden element z Dziś.
```

Odczytuje bieżący plik, robi celowaną edycję i pokazuje Ci zmianę. Zatwierdzasz każdy krok — jesteś recenzentem.

### Krok 5 — Poproś o weryfikację

```text
Pokaż mi finalne notes.md i potwierdź, że każda sekcja ma co najmniej jeden punkt.
```

Dobry agent sprawdza własną pracę — poproś, by zweryfikował ją wobec tego, czego chciałeś/aś.

### Krok 6 — Twoje limity nadal obowiązują

Codex czerpie z użycia Twojego planu. Długie sesje agentowe zużywają więcej — więc nawyki z D2/D3 mają znaczenie: jasne cele, lekki kontekst, właściwy model i świeże sesje do nowych zadań.

---

## 🧩 Nawyki pracy z agentem

| Rób | Zamiast |
|----|------------|
| Podaj cel + ograniczenia, pozwól planować | Mikrozarządzać każdym naciśnięciem klawisza |
| Zatwierdzaj każdą zmianę przy przeglądaniu | Ślepo akceptować wszystko |
| Proś o weryfikację wobec Twojej intencji | Ufać wynikowi bez sprawdzenia |
| Pracuj w dedykowanym folderze | Wskazywać cały dysk |
| Zaczynaj od nowa przy nowym zadaniu | Jedna niekończąca się sesja |

> **Bezpieczeństwo:** Codex CLI pyta przed edycją plików czy uruchomieniem poleceń i domyślnie działa w piaskownicy (więcej w Ścieżce G). Trzymaj go w **dedykowanym folderze** (lub gałęzi git), by każda zmiana była łatwa do przeglądu i cofnięcia. Zawsze to Ty, człowiek, zatwierdzasz działania.

---

## ✅ Sprawdzian

- [ ] Codex CLI jest zainstalowany i zalogowany **kontem ChatGPT** (bez klucza API).
- [ ] Zaplanował i wykonał prawdziwą zmianę pliku, którą zatwierdziłeś/aś.
- [ ] Iterowałeś/aś z dopytaniem i poprosiłeś/aś o weryfikację jego pracy.
- [ ] Umiesz wyjaśnić, że Codex używa użycia Twojego planu, więc D2/D3 obowiązują.

---

## 🎯 Praca domowa

Wybierz małe, prawdziwe, niskiego ryzyka zadanie w dedykowanym folderze — uporządkuj notatki, naszkicuj prosty skrypt, ogarnij listę zadań. Poprowadź je Codeksem CLI według: najpierw plan, zatwierdź każdy krok, zweryfikuj na końcu. Trzymaj cel jasny, by być efektywnym.

---

## 💡 Najważniejsze wnioski

- **Agent** planuje, działa, używa narzędzi i weryfikuje w kierunku celu — z Twoim zatwierdzaniem każdego kroku.
- **Codex CLI** działa na Twoim **planie ChatGPT Plus/Pro** (logowanie kontem) — bez klucza API, bez osobnego rachunku na start.
- Te same **limity użycia** obowiązują — jasne cele i lekki kontekst (D2/D3) utrzymują sesje agentowe efektywnymi.

🌐 [English](../../en/track-d/05-agents-and-codex-cli.md) · [← Poprzedni](04-instrukcje-wlasne-i-pamiec.md) · [Spis ścieżki](../README.md) · [↩ Strona ścieżek zaawansowanych](../README.md)
