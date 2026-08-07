# D5 — Agenci i Gemini CLI na Twoim planie

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Google, Node.js (z kursu podstawowego)

🌐 [English](../../en/track-d/05-agents-and-gemini-cli.md) · [← Wstecz](04-personalizacja-i-pamiec.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (5 min)

Dotąd Gemini odpowiadał na pytania i tworzył pliki. **Agent** idzie dalej: mając cel, **planuje, wykonuje kroki, używa narzędzi, sprawdza pracę i idzie dalej**, aż zadanie jest gotowe — z Twoim zatwierdzaniem po drodze.

Najprzydatniejszy agent dla większości to **Gemini CLI** — Gemini pracujący bezpośrednio z plikami i poleceniami na komputerze. Kluczowy fakt tej ścieżki: **możesz zalogować się kontem Google** i korzystać z **hojnego darmowego poziomu** — bez klucza API i osobnego rozliczania na start.

Dwa sposoby myślenia o pracy agentowej:

- **W aplikacji** — Gemini już łączy kroki: planuje, używa Deep Research, woła połączone aplikacje i przechodzi przez wieloczęściową prośbę za jednym razem.
- **Na Twojej maszynie** — Gemini CLI czyta i edytuje prawdziwe pliki, uruchamia polecenia i iteruje, pod Twoim zatwierdzeniem.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zainstaluj Gemini CLI

W **PowerShell**:

```powershell
npm install -g @google/gemini-cli
```

(Jeśli `npm` nie jest znaleziony, najpierw zainstaluj Node.js z kursu podstawowego.)

### Krok 2 — Zaloguj się kontem Google

Przejdź do folderu, w którym chcesz pracować, i uruchom:

```powershell
mkdir $HOME\gemini-cli-demo
cd $HOME\gemini-cli-demo
gemini
```

Przy pierwszym uruchomieniu zapyta, jak się zalogować. **Wybierz „Login with Google”**, by użyć darmowego poziomu na koncie (zamiast wklejać klucz API). Otworzy się przeglądarka; zatwierdź. Teraz CLI działa na Twoim koncie — bez dodatkowego rozliczania na start.

> Jeśli oferuje też opcję klucza API: to droga programistyczna/rozliczana. W tej ścieżce użyj **logowania Google**.

### Krok 3 — Daj mu mały cel

Wpisz zadanie zwykłym językiem:

```text
Utwórz plik notes.md z trzema sekcjami: Cele, Dzisiaj, Później.
Potem dodaj trzy przykładowe punkty pod Dzisiaj.
```

Patrz, jak **planuje**, proponuje zmianę i pyta o pozwolenie przed zapisem. Zatwierdź i sprawdź, że plik się pojawił. Właśnie uruchomiłeś agenta na prawdziwych plikach.

### Krok 4 — Pozwól mu iterować

```text
Teraz dodaj sekcję „Zrobione” na górze i przenieś jeden element z Dzisiaj do niej.
```

Czyta bieżący plik, robi celowaną edycję i pokazuje zmianę. Zatwierdzasz każdy krok — jesteś recenzentem.

### Krok 5 — Poproś o weryfikację

```text
Pokaż mi finalny notes.md i potwierdź, że każda sekcja ma co najmniej jeden punkt.
```

Dobry agent sprawdza własną pracę — poproś o weryfikację względem tego, czego chciałeś.

### Krok 6 — Twoje limity nadal obowiązują

CLI czerpie z użycia Twojego konta. Długie sesje agenta zużywają więcej — więc nawyki z D2/D3 mają znaczenie: jasne cele, chudy kontekst, właściwy model i świeże sesje do nowych zadań.

---

## 🧩 Nawyki pracy z agentem

| Rób | Zamiast |
|----|------------|
| Podaj cel + ograniczenia, pozwól planować | Mikrozarządzać każdym naciśnięciem |
| Zatwierdzaj każdą zmianę, gdy ją przeglądasz | Ślepo akceptować wszystko |
| Poproś o weryfikację względem intencji | Ufać wynikowi bez sprawdzenia |
| Pracuj w dedykowanym folderze | Kierować go na cały dysk |
| Zaczynaj od nowa dla nowego zadania | Jedna niekończąca się sesja |

> **Bezpieczeństwo:** Gemini CLI pyta przed edycją plików lub uruchomieniem poleceń. Trzymaj go w **dedykowanym folderze** (lub gałęzi git), by każdą zmianę łatwo przejrzeć i cofnąć. To zawsze Ty zatwierdzasz działania.

---

## ✅ Sprawdzenie

- [ ] Gemini CLI jest zainstalowany i zalogowany **kontem Google** (darmowy poziom, bez klucza API).
- [ ] Zaplanował i zrobił prawdziwą zmianę pliku, którą zatwierdziłeś.
- [ ] Iterowałeś prośbą uzupełniającą i kazałeś mu zweryfikować pracę.
- [ ] Umiesz wyjaśnić, że CLI używa użycia konta, więc D2/D3 obowiązują.

---

## 🎯 Zadanie

Wybierz małe, prawdziwe, niskiego ryzyka zadanie w dedykowanym folderze — uporządkuj notatki, naszkicuj prosty skrypt, ogarnij listę zadań. Poprowadź je Gemini CLI: najpierw plan, zatwierdzaj każdy krok, weryfikuj na końcu. Trzymaj cel jasny, byś pozostał efektywny.

---

## 💡 Najważniejsze wnioski

- **Agent** planuje, działa, używa narzędzi i weryfikuje ku celowi — z Twoim zatwierdzaniem każdego kroku.
- **Gemini CLI** działa na **darmowym poziomie konta Google** (logowanie Google) — bez klucza API i osobnego rachunku na start.
- Te same **limity** obowiązują — jasne cele i chudy kontekst (D2/D3) trzymają sesje efektywnymi.

🌐 [English](../../en/track-d/05-agents-and-gemini-cli.md) · [← Wstecz](04-personalizacja-i-pamiec.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
