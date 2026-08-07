# G4 — Bezpieczna edycja z Git

⏱️ **15 minut** · Ścieżka: 🅶 Codex CLI w głąb · Wymagania: Codex CLI + zainstalowany Git (`git --version`)

🌐 [English](../../en/track-g/04-safe-editing-with-git.md) · [← Poprzedni](03-konfiguracja-i-wlasne-prompty.md) · [Spis ścieżki](../README.md) · [Dalej: Tryb bezobsługowy i automatyzacja →](05-tryb-bezobslugowy-i-automatyzacja.md)

---

## 🧠 Teoria (4 min)

Gdy agent edytuje Twoje pliki, potrzebujesz **przycisku cofania** i sposobu, by **dokładnie zobaczyć, co się zmieniło**. Tym narzędziem jest **Git** — i to największe pojedyncze ulepszenie bezpieczeństwa dla kodowania wspieranego AI.

Idea jest prosta:

- **Zacommituj** czysty punkt startowy *zanim* pozwolisz Codeksowi pracować.
- Pozwól mu wprowadzić zmiany, potem **przejrzyj diff** — dokładne przed/po.
- **Zachowaj** dobre zmiany (commit) lub **wyrzuć je** (restore) — natychmiast, całkowicie.

Z Gitem pod sobą żadna edycja agenta nie jest trwała, dopóki *Ty* tak nie zdecydujesz. To łączy się bezpośrednio z piaskownicą z G2: piaskownica ogranicza, *gdzie* może zapisywać; Git pozwala *cofnąć* to, co zapisał.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Zacznij czysto

W swoim projekcie upewnij się, że wszystko jest najpierw zacommitowane:

```powershell
git status
git add -A
git commit -m "Czysty punkt startowy przed pracą agenta"
```

Czyste drzewo oznacza, że każda zmiana, którą zobaczysz dalej, pochodzi z tej sesji.

### Krok 2 — Pozwól Codeksowi wprowadzić zmianę

Poproś o małą, prawdziwą edycję:

```text
Dodaj walidację danych wejściowych do głównej funkcji i krótki komentarz ją wyjaśniający.
```

### Krok 3 — Przejrzyj diff

Zobacz dokładnie, co się zmieniło — linia po linii:

```powershell
git diff
```

**Przeczytaj to.** To nawyk, który utrzymuje Cię w kontroli: nigdy nie akceptuj edycji, na które nie spojrzałeś/aś. Możesz nawet poprosić Codeksa, by przeprowadził Cię przez swój własny diff.

### Krok 4 — Zachowaj lub cofnij

**Zadowolony/a?** Zacommituj:

```powershell
git add -A
git commit -m "Dodaj walidację danych wejściowych"
```

**Niezadowolony/a?** Wyrzuć zmiany i wróć do czystego punktu:

```powershell
git restore .
```

(To odrzuca *niezacommitowane* zmiany. Ponieważ zacommitowałeś/aś w Kroku 1, nie tracisz nic, czego chciałeś/aś.)

### Krok 5 — Pracuj w małych pętlach

Bezpieczny rytm:

1. Zacommituj czysty punkt.
2. Poproś o **jedną** skupioną zmianę.
3. Przejrzyj diff.
4. Zacommituj lub cofnij.
5. Powtórz.

Małe pętle oznaczają małe diffy — łatwe do przeglądu, łatwe do cofnięcia.

### Krok 6 — Gałąź dla czegokolwiek większego

Dla większego eksperymentu pracuj na gałęzi, by `main` pozostał bezpieczny:

```powershell
git switch -c experiment
```

Podoba się? Scal później. Nie? Usuń gałąź — `main` nigdy się nie ruszył.

---

## 🧩 Twoja siatka bezpieczeństwa

| Chcesz… | Polecenie |
|----------|---------|
| Zapisać czysty punkt startowy | `git commit -m "..."` |
| Zobaczyć dokładnie, co się zmieniło | `git diff` |
| Zachować zmiany | `git add -A && git commit` |
| Cofnąć niezacommitowane zmiany | `git restore .` |
| Wyizolować duży eksperyment | `git switch -c <gałąź>` |

> ⚠️ **Nigdy nie pozwól agentowi pracować na niezacommitowanej, niezabezpieczonej pracy.** Najpierw zacommituj — wtedy każda edycja jest do przejrzenia i odwracalna.

---

## ✅ Sprawdzian

- [ ] Zacommitowałeś/aś czysty punkt startowy przed pozwoleniem Codeksowi na edycję.
- [ ] Przejrzałeś/aś zmianę przez `git diff`.
- [ ] Zachowałeś/aś jedną zmianę (commit) i cofnąłeś/ęłaś inną (`git restore`).
- [ ] Umiesz opisać pętlę commit → zmiana → diff → zachowaj/cofnij.

---

## 🎯 Praca domowa

Na prawdziwym projekcie zrób trzy pętle edycji z Codeksem: zacommituj czysty punkt, poproś o jedną zmianę, przejrzyj diff, potem zacommituj lub cofnij. Zachowaj jedną, cofnij jedną celowo, byś zaufał/a swojemu przyciskowi cofania.

---

## 💡 Najważniejsze wnioski

- **Git to Twój przycisk cofania** dla edycji agenta — zacommituj najpierw czysty punkt, a nic nie jest trwałe, dopóki nie powiesz.
- Zawsze **przeglądaj `git diff`** przed akceptacją zmian; nigdy nie scalaj edycji, których nie przeczytałeś/aś.
- Pracuj w **małych pętlach** (commit → zmiana → diff → zachowaj/cofnij) i **rozgałęziaj** przy większych eksperymentach.

🌐 [English](../../en/track-g/04-safe-editing-with-git.md) · [← Poprzedni](03-konfiguracja-i-wlasne-prompty.md) · [Spis ścieżki](../README.md) · [Dalej: Tryb bezobsługowy i automatyzacja →](05-tryb-bezobslugowy-i-automatyzacja.md)
