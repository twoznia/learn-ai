# Lekcja 16 — Agent kodujący Copilota

⏱️ **12 minut** · Poziom: Zaawansowany · Wymagania: repo GitHub + Copilot (funkcje agenta zależą od planu)

🌐 [English](../../en/lessons/16-copilot-coding-agent.md) · [← Poprzednia](15-copilot-na-github-com.md) · [Strona kursu](../README.md) · [Dalej: Copilot CLI i Actions →](17-copilot-cli-i-actions.md)

---

## 🧠 Teoria (4 min)

Dotąd *Ty* prowadziłeś/aś Copilota. **Agent kodujący** to odwraca: **przypisujesz zgłoszenie Copilotowi**, a on pracuje w tle — bada repo, robi zmiany na gałęzi i **otwiera pull request** do Twojego przeglądu. To jak delegowanie zadania koledze, który zawsze odsyła PR.

Przepływ:

1. Piszesz jasne **zgłoszenie** (Lekcja 11).
2. **Przypisujesz je Copilotowi** (lub uruchamiasz agenta ze zgłoszenia/PR).
3. Copilot pracuje na gałęzi i otwiera **szkic PR**.
4. **Ty przeglądasz** PR — prosisz o zmiany przez komentarze, a on iteruje.
5. Scalasz, gdy jest gotowe.

Złota zasada zostaje: **to Ty jesteś recenzentem.** Agent proponuje; nic nie scala się bez Twojego zatwierdzenia.

> Dostępność agenta kodującego, gdzie go uruchamiasz i jego dokładne zachowanie zależą od planu i ustawień oraz ewoluują. Sprawdź bieżącą dokumentację „Copilot coding agent".

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Napisz zgłoszenie przyjazne agentowi

Użyj małego, samodzielnego z Lekcji 11, np. „Add a `--language` flag." Zawrzyj **kryteria akceptacji** i wspomnij o plikach. Im jaśniejsze zgłoszenie, tym lepszy PR.

### Krok 2 — Przypisz je Copilotowi

Na zgłoszeniu przypisz je **Copilotowi** (w sekcji Assignees, gdzie dostępne) — lub użyj opcji „start coding agent" / delegowania na github.com lub w VS Code.

### Krok 3 — Obserwuj, jak otwiera PR

Copilot pracuje na gałęzi i otwiera **szkic pull requesta** opisujący, co zrobił. Może to zająć kilka minut.

### Krok 4 — Przejrzyj go jak każdy PR

Przeczytaj diff **Files changed** (Lekcje 10, 13). Czy spełnia kryteria akceptacji? Uruchom kod. Użyj przeglądu Copilota (Lekcja 13) jako drugiego przebiegu.

### Krok 5 — Poproś o zmiany

Nie do końca dobrze? Zostaw **komentarze przeglądu** opisujące, co poprawić. Agent je czyta i **pushuje aktualizacje** do tego samego PR — iterując jak kolega.

### Krok 6 — Scal lub przejmij

Gdy spełnia poprzeczkę, scal. Jeśli utknął, **pobierz gałąź** i dokończ sam/a w VS Code — nigdy nie jesteś zablokowany/a.

---

## 🧩 Prowadzony przez Ciebie vs przez agenta

| | Prowadzony przez Ciebie (Lekcje 2–8) | Przez agenta (ta lekcja) |
|--|--------------------------|----------------------------|
| Wyzwalacz | Wpisujesz w edytorze | Przypisujesz zgłoszenie |
| Gdzie pracuje | Twój otwarty edytor | Gałąź na GitHubie |
| Wynik | Edycje przed Tobą | Pull request |
| Twoja rola | Autor + recenzent | **Recenzent** |

> ⚠️ Dawaj agentowi **ograniczone, dobrze określone** zadania. Przeglądaj jego PR tak starannie jak obcego — przypisuj, ale zawsze weryfikuj.

---

## ✅ Sprawdzian

- [ ] Napisałeś/aś jasne, samodzielne zgłoszenie z kryteriami akceptacji.
- [ ] Przypisałeś/aś/przekazałeś/aś je agentowi kodującemu Copilota.
- [ ] Przejrzałeś/aś PR, który otworzył, i uruchomiłeś/aś kod.
- [ ] Poprosiłeś/aś o zmianę (lub scaliłeś/aś) — zostając recenzentem.

---

## 🎯 Praca domowa

Przekaż agentowi jedno małe, dobrze określone zgłoszenie na repo. Przejrzyj jego PR wobec kryteriów akceptacji, poproś o jedno usprawnienie przez komentarz i zobacz, jak aktualizuje PR. Potem scal. Zastanów się: co czyni zgłoszenie łatwym vs trudnym dla agenta?

---

## 💡 Najważniejsze wnioski

- **Agent kodujący** bierze **przypisane zgłoszenie** i otwiera **pull request**, który przeglądasz.
- Iterujesz przez **komentarze przeglądu**; on pushuje aktualizacje — a Ty zawsze możesz przejąć gałąź.
- Sukces zależy od **jasnych, ograniczonych zgłoszeń** — a Ty pozostajesz **recenzentem**, który zatwierdza scalenie.

🌐 [English](../../en/lessons/16-copilot-coding-agent.md) · [← Poprzednia](15-copilot-na-github-com.md) · [Strona kursu](../README.md) · [Dalej: Copilot CLI i Actions →](17-copilot-cli-i-actions.md)
