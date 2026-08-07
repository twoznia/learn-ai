# Lekcja 09 — Dekompozycja i łańcuchy promptów

⏱️ **12 minut** · Poziom: Średni → Zaawansowany · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/09-decomposition-and-chaining.md) · [← Poprzednia](08-rozumowanie-krok-po-kroku.md) · [Strona kursu](../README.md) · [Dalej: Kontrola wyniku →](10-kontrola-wyniku.md)

---

## 🧠 Teoria (4 min)

Duże, złożone prośby w jednym gigantycznym promptcie często dają przeciętne wyniki — model żongluje zbyt wieloma rzeczami naraz. **Dekompozycja** to rozbicie zadania na mniejsze kroki; **łańcuch promptów** to podawanie wyniku jednego kroku do następnego.

Dwa sposoby:

- **Jeden strukturyzowany prompt, sekwencyjnie** — „Zrób krok 1, potem 2, potem 3", by model podszedł do nich po kolei (buduje na Lekcji 8).
- **Wiele łączonych promptów** — uruchamiasz prompt, bierzesz jego wynik i używasz jako wejścia następnego. Każdy krok jest skupiony i do przejrzenia.

Łańcuchy błyszczą w prawdziwych przepływach: **konspekt → szkic → krytyka → poprawka** lub **wyodrębnij → analizuj → podsumuj**. Możesz zbadać (i naprawić) każdy etap, zamiast liczyć, że jeden mega-prompt trafi wszystko.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zdekomponuj w jednym promptcie

```text
Napisz wpis blogowy etapami, pokazując każdy:
1. 5-punktowy konspekt.
2. Szkic z tego konspektu.
3. Trzy konkretne usprawnienia, które byś wprowadził.
4. Finalną poprawioną wersję.
```

### Krok 2 — Łańcuch przez osobne prompty

Prompt 1:

```text
Daj mi 5-punktowy konspekt wpisu o „robieniu kopii zapasowej PC".
```

Przejrzyj/edytuj konspekt, potem Prompt 2:

```text
Oto konspekt: [wklej]. Napisz 300-słowowy szkic dokładnie za nim podążający.
```

Potem Prompt 3:

```text
Skrytykuj ten szkic pod kątem klarowności i utnij 15%: [wklej].
```

Kontrolowałeś/aś i ulepszyłeś/aś każdy etap.

### Krok 3 — Użyj jednego wyniku jako wejścia drugiego

```text
Wyodrębnij wszystkie punkty do działania z tych notatek ze spotkania jako listę.
```

Potem:

```text
Dla każdego punktu powyżej naszkicuj jednolinijkową wiadomość na Slacka do odpowiedzialnego.
```

### Krok 4 — Dodaj krok przeglądu

Zawsze wstaw punkt kontrolny, na którym możesz działać:

```text
Przed finalizacją wypisz wszelkie założenia, które przyjąłeś, i cokolwiek niejasnego.
```

### Krok 5 — Wiedz, kiedy jeden prompt wystarczy

Małe zadania nie potrzebują łańcucha. Sięgaj po niego, gdy zadanie ma **odrębne etapy**, każdy wart przeglądu.

---

## 🧩 Częste łańcuchy

| Przepływ | Łańcuch |
|----------|-------|
| Pisanie | Konspekt → szkic → krytyka → poprawka |
| Badanie | Zbierz → wyodrębnij → analizuj → podsumuj |
| Dane | Parsuj → przekształć → waliduj → raportuj |
| Decyzje | Opcje → zważ → rekomenduj → zaplanuj |

---

## ✅ Sprawdzian

- [ ] Rozbiłeś/aś duże zadanie na uporządkowane kroki w jednym promptcie.
- [ ] Połączyłeś/aś osobne prompty, podając wynik do wejścia.
- [ ] Przejrzałeś/aś/edytowałeś/aś pośredni wynik przed kontynuacją.
- [ ] Umiesz nazwać zadanie wymagające łańcucha vs takie, które nie.

---

## 🎯 Praca domowa

Wybierz coś, o co normalnie prosisz za jednym razem (raport, plan, artykuł). Zrób to jako łańcuch co najmniej trzech promptów, przeglądając każdy etap. Porównaj finalny wynik z wersją jednego mega-promptu — zanotuj, gdzie przegląd w połowie go ulepszył.

---

## 💡 Najważniejsze wnioski

- **Dekomponuj** złożone zadania na kroki; **łącz** prompty, podając jeden wynik do następnego.
- Łańcuch pozwala **zbadać i naprawić każdy etap**, zamiast ufać jednemu gigantycznemu promptowi.
- Używaj go, gdy zadanie ma **odrębne, warte przeglądu etapy**; pomiń przy małych prośbach.

🌐 [English](../../en/lessons/09-decomposition-and-chaining.md) · [← Poprzednia](08-rozumowanie-krok-po-kroku.md) · [Strona kursu](../README.md) · [Dalej: Kontrola wyniku →](10-kontrola-wyniku.md)
