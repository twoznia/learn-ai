# Lekcja 13 — Automatyczny przegląd kodu z Copilotem

⏱️ **12 minut** · Poziom: Średni · Wymagania: repo GitHub + Copilot

🌐 [English](../../en/lessons/13-automatic-code-review.md) · [← Poprzednia](12-swietne-pull-requesty.md) · [Strona kursu](../README.md) · [Dalej: README i dokumentacja →](14-readme-i-dokumentacja.md)

---

## 🧠 Teoria (4 min)

Copilot może **przeglądać Twój kod** — wskazując błędy, niejasne nazwy, brak obsługi błędów i problemy stylu — zarówno *przed* otwarciem PR (w VS Code), jak i *na* samym PR (na github.com).

Dwa momenty użycia:

1. **Przed startem, w VS Code** — poproś Copilota o przegląd zmian, zanim w ogóle zpushujesz. Łap problemy prywatnie.
2. **Na pull requeście** — poproś **Copilota jako recenzenta**, a on zamieszcza komentarze przeglądu na konkretnych liniach, jak ludzki recenzent. W niektórych konfiguracjach może przeglądać **automatycznie** każdy PR.

Kluczowo, przegląd Copilota **uzupełnia**, a nie zastępuje przegląd ludzki i testy. To szybki pierwszy przebieg, który łapie oczywiste rzeczy, by ludzie skupili się na ważnych.

> Dostępność przeglądu kodu Copilota (i automatycznego) zależy od planu i ustawień repo, a funkcja ewoluuje. Sprawdź bieżącą dokumentację „Copilot code review", by ją włączyć.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Przejrzyj zmiany przed pushem

Na gałęzi, w Copilot Chat:

```text
@workspace Review my changes on this branch for bugs, unclear names, missing
error handling, and edge cases. List findings as a checklist, most important first.
Don't change code — just report.
```

Napraw, co warte, potem zacommituj.

### Krok 2 — Poproś o przegląd Copilota na PR

Otwórz PR (Lekcja 10). W sekcji **Reviewers** dodaj **Copilot** jako recenzenta (gdzie dostępne). Analizuje diff i zamieszcza komentarze.

### Krok 3 — Przeczytaj komentarze przeglądu

Copilot zostawia komentarze na konkretnych liniach, czasem z **sugerowanymi zmianami**, które zacommitujesz jednym kliknięciem. Traktuj każdy jak ludzką sugestię: **oceń**, nie akceptuj na ślepo.

### Krok 4 — Zastosuj lub odrzuć, z osądem

- Prawdziwy błąd lub jasne usprawnienie → zastosuj sugestię.
- Fałszywy alarm lub uwaga poza zakresem → odpowiedz dlaczego i odrzuć.

Wciąż jesteś decydentem; Copilot to asystent-recenzent.

### Krok 5 — Włącz automatyczny przegląd (opcjonalnie)

W ustawieniach repo/organizacji możesz móc sprawić, by Copilot **automatycznie przeglądał** nowe PR-y (np. przez regułę lub ustawienia Copilota repo). Świetne dla spójnego pierwszego przebiegu na każdej zmianie.

### Krok 6 — Łącz warstwy przeglądu

Najmocniejsza konfiguracja je układa:

```text
1) Przegląd Copilota przed startem w VS Code
2) Testy (Lekcja 6) uruchamiane w CI (Lekcja 17)
3) Przegląd Copilota na PR
4) Przegląd ludzki
```

Każda warstwa łapie to, co inne przeoczą.

---

## 🧩 Gdzie Copilot przegląda

| Gdzie | Jak | Najlepsze do |
|-------|-----|----------|
| **VS Code** (przed pushem) | Poproś czat o przegląd gałęzi | Prywatne, szybkie łapanie problemów |
| **Na PR** | Dodaj Copilota jako recenzenta | Komentarze na liniach + sugestie |
| **Automatycznie** | Reguła repo/org (jeśli włączona) | Spójny pierwszy przebieg na każdym PR |

> ⚠️ Przegląd AI przeocza rzeczy i podnosi fałszywe alarmy. To **pierwszy przebieg**, nie substytut testów i ludzkiego osądu.

---

## ✅ Sprawdzian

- [ ] Kazałeś/aś Copilotowi przejrzeć gałąź w VS Code przed pushem.
- [ ] Poprosiłeś/aś o przegląd Copilota na PR i przeczytałeś/aś komentarze.
- [ ] Zastosowałeś/aś jedną dobrą sugestię i odrzuciłeś/aś jedną z uzasadnieniem.
- [ ] Umiesz wyjaśnić, czemu przegląd AI uzupełnia (nie zastępuje) ludzi + testy.

---

## 🎯 Praca domowa

Na prawdziwym PR uruchom pełny stos: przegląd Copilota przed startem w VS Code, napraw problemy, otwórz PR, poproś o przegląd Copilota i działaj na jego komentarzach z osądem. Zanotuj jedną rzecz, którą złapał, a Ty byś przeoczył/a — i jedną, którą pomylił.

---

## 💡 Najważniejsze wnioski

- Copilot przegląda kod **w VS Code przed pushem** i **na PR** (czasem automatycznie).
- Zamieszcza **komentarze i sugestie na liniach** — oceniaj każdą; Ty decydujesz.
- Przegląd AI to **pierwszy przebieg**, który układa się z **testami i przeglądem ludzkim**, nie zastępuje ich.

🌐 [English](../../en/lessons/13-automatic-code-review.md) · [← Poprzednia](12-swietne-pull-requesty.md) · [Strona kursu](../README.md) · [Dalej: README i dokumentacja →](14-readme-i-dokumentacja.md)
