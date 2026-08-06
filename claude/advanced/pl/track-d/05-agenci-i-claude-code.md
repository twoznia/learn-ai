# D5 — Agenci i Claude Code na abonamencie

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Pro/Max, Node.js (z kursu podstawowego)

🌐 [English](../../en/track-d/05-agents-and-claude-code.md) · [← Wstecz](04-skille-i-konektory.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (5 min)

Dotąd Claude odpowiadał na pytania i tworzył pliki. **Agent** idzie krok dalej: mając cel, **planuje, wykonuje kroki, używa narzędzi, sprawdza własną pracę i idzie dalej**, aż zadanie jest gotowe — z Twoim zatwierdzaniem po drodze.

Najprzydatniejszy agent dla większości ludzi to **Claude Code** — Claude pracujący bezpośrednio z plikami i poleceniami na Twoim komputerze. Kluczowy fakt tej ścieżki: **Claude Code działa na Twoim abonamencie Pro/Max**. Logujesz się kontem Claude — **bez klucza API, bez osobnego rachunku za tokeny.**

Dwa sposoby myślenia o pracy „agentowej” na Twoim planie:

- **W aplikacjach czatu** — Claude już łączy kroki: planuje, woła Skille i konektory i przechodzi przez wieloczęściową prośbę za jednym razem.
- **Na Twojej maszynie** — Claude Code czyta i edytuje prawdziwe pliki, uruchamia polecenia i iteruje, wszystko pod Twoim zatwierdzeniem.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zainstaluj Claude Code

W **PowerShell**:

```powershell
npm install -g @anthropic-ai/claude-code
```

(Jeśli `npm` nie jest znaleziony, najpierw zainstaluj Node.js z kursu podstawowego.)

### Krok 2 — Zaloguj się abonamentem

Przejdź do folderu, w którym chcesz pracować, i uruchom:

```powershell
mkdir $HOME\claude-code-demo
cd $HOME\claude-code-demo
claude
```

Przy pierwszym uruchomieniu zapyta, jak się zalogować. **Wybierz „zaloguj kontem Claude”** (Twój plan Pro/Max), a nie klucz API. Otworzy się przeglądarka; zatwierdź. Teraz Claude Code używa Twojego **abonamentu** — bez dodatkowych opłat.

> Jeśli wspomni też o opcji klucza API: to płatna ścieżka programistyczna. W tej ścieżce użyj **logowania kontem**.

### Krok 3 — Daj mu mały cel

Wpisz zadanie zwykłym językiem w wierszu:

```text
Utwórz plik notes.md z trzema sekcjami: Cele, Dzisiaj, Później.
Potem dodaj trzy przykładowe punkty pod Dzisiaj.
```

Patrz, jak **planuje**, proponuje zmianę i pyta o pozwolenie przed zapisem. Zatwierdź i sprawdź, że plik się pojawił. Właśnie uruchomiłeś agenta działającego na prawdziwych plikach.

### Krok 4 — Pozwól mu iterować

Agenci błyszczą, gdy doprecyzowujesz:

```text
Teraz dodaj sekcję „Zrobione” na górze i przenieś jeden element z Dzisiaj do niej.
```

Czyta bieżący plik, robi celowaną edycję i pokazuje zmianę. Zatwierdzasz każdy krok — jesteś recenzentem.

### Krok 5 — Poproś o wyjaśnienie i weryfikację

```text
Pokaż mi finalny notes.md i potwierdź, że każda sekcja ma co najmniej jeden punkt.
```

Dobry agent sprawdza własną pracę. Poproś o weryfikację względem tego, czego chciałeś, byś nie brał wyniku na wiarę.

### Krok 6 — Pamiętaj, że limity nadal obowiązują

Claude Code czerpie z **tego samego użycia** co Twój plan. Ciężkie, długie sesje agenta zużywają więcej okna — więc nawyki z D2 i D3 nadal mają znaczenie: jasne cele, chudy kontekst, właściwy model i zaczynanie świeżej sesji do nowego zadania.

---

## 🧩 Nawyki pracy z agentem

| Rób | Zamiast |
|----|------------|
| Podaj cel + ograniczenia, pozwól planować | Mikrozarządzać każdym naciśnięciem |
| Zatwierdzaj każdą zmianę, gdy ją przeglądasz | Ślepo akceptować wszystko |
| Poproś o weryfikację względem Twojej intencji | Ufać wynikowi bez sprawdzenia |
| Pracuj w dedykowanym folderze | Kierować go na cały dysk |
| Zaczynaj od nowa dla nowego zadania | Jedna niekończąca się sesja |

> **Bezpieczeństwo:** Claude Code pyta przed edycją plików lub uruchomieniem poleceń. Trzymaj go w **dedykowanym folderze** (lub gałęzi git), by każdą zmianę łatwo przejrzeć i cofnąć. To zawsze Ty jesteś człowiekiem zatwierdzającym działania.

---

## ✅ Sprawdzenie

- [ ] Claude Code jest zainstalowany i zalogowany **abonamentem** (bez klucza API).
- [ ] Zaplanował i zrobił prawdziwą zmianę pliku, którą zatwierdziłeś.
- [ ] Iterowałeś prośbą uzupełniającą i kazałeś mu zweryfikować własną pracę.
- [ ] Umiesz wyjaśnić, że Claude Code używa użycia Twojego planu, więc nawyki D2/D3 obowiązują.

---

## 🎯 Zadanie

Wybierz małe, prawdziwe, niskiego ryzyka zadanie w dedykowanym folderze — uporządkuj notatki, naszkicuj prosty skrypt, ogarnij listę zadań. Poprowadź je Claude Code, stosując przepływ „najpierw plan, zatwierdzaj każdy krok, weryfikuj na końcu”. Trzymaj cel jasny, byś pozostał efektywny.

---

## 💡 Najważniejsze wnioski

- **Agent** planuje, działa, używa narzędzi i weryfikuje ku celowi — z Twoim zatwierdzaniem każdego kroku.
- **Claude Code** działa na Twoim **abonamencie Pro/Max** (logowanie kontem), więc **bez klucza API i bez dodatkowego rachunku za użycie**.
- Te same **limity** obowiązują — jasne cele i chudy kontekst (D2/D3) trzymają sesje agenta efektywnymi.

🌐 [English](../../en/track-d/05-agents-and-claude-code.md) · [← Wstecz](04-skille-i-konektory.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
