# Lekcja 11 — Ograniczanie halucynacji i osadzanie odpowiedzi

⏱️ **12 minut** · Poziom: Zaawansowany · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/11-reducing-hallucinations.md) · [← Poprzednia](10-kontrola-wyniku.md) · [Strona kursu](../README.md) · [Dalej: Autokrytyka i iteracja →](12-autokrytyka-i-iteracja.md)

---

## 🧠 Teoria (4 min)

**Halucynacja** to gdy model podaje coś fałszywego jako prawdę — wymyślony fakt, fałszywe cytowanie, zmyślone API. Dzieje się, bo model przewiduje *prawdopodobny* tekst, a prawdopodobny nie zawsze jest poprawny. Nie wyeliminujesz tego, ale dobre promptowanie **znacząco to zmniejsza**.

Kluczowe taktyki:

1. **Osadź odpowiedź w dostarczonych źródłach.** Daj modelowi tekst do użycia i powiedz „odpowiadaj tylko z tego". Nie wymyśli tego, czego kazano mu się trzymać.
2. **Daj mu furtkę.** Wprost pozwól na „Nie wiem". Modele halucynują częściowo, bo zachowują się, jakby musiały zawsze odpowiedzieć.
3. **Proś o niepewność i źródła.** „Oznacz cokolwiek, czego nie jesteś pewien" i „cytuj, skąd pochodzi każde twierdzenie" wydobywa chwiejne części.
4. **Weryfikuj niezależnie.** Przy czymkolwiek ważnym sprawdź twierdzenie sam/a — zwłaszcza nazwiska, liczby, cytaty i cytowania.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Osadź w Twoim tekście

```text
Odpowiadaj używając TYLKO poniższego dokumentu. Jeśli odpowiedzi w nim nie ma,
powiedz „Nieokreślone w dokumencie". Nie używaj wiedzy z zewnątrz.

"""
[wklej źródło]
"""

Pytanie: …
```

### Krok 2 — Daj pozwolenie na „Nie wiem"

```text
Jeśli nie jesteś pewien, powiedz to zamiast zgadywać. Lepiej powiedzieć
„Nie jestem pewien" niż wymyślić odpowiedź.
```

### Krok 3 — Poproś, by oddzielił fakt od wnioskowania

```text
Oznacz każde stwierdzenie jako [ZE ŹRÓDŁA] lub [MOJE WNIOSKOWANIE], bym widział/a,
co jest osadzone vs wywnioskowane.
```

### Krok 4 — Żądaj sprawdzalnych cytowań

```text
Dla każdego twierdzenia zacytuj dokładne zdanie ze źródła, na którym się opiera.
```

Jeśli nie potrafi zacytować źródła, to twierdzenie jest podejrzane.

### Krok 5 — Przetestuj ryzykowną odpowiedź pod naciskiem

```text
Co uczyniłoby tę odpowiedź błędną? Wypisz założenia, które, jeśli fałszywe, ją łamią.
```

### Krok 6 — Weryfikuj, co ważne

Traktuj nazwiska, statystyki, cytaty, twierdzenia prawne/medyczne/finansowe i cytowania jako **niezweryfikowane**, dopóki sam/a nie sprawdzisz. Cytowane ≠ poprawne.

---

## 🧩 Zestaw anty-halucynacyjny

| Taktyka | Ruch promptu |
|--------|-------------|
| Osadź | „Odpowiadaj tylko z tego źródła" |
| Pozwól na niepewność | „Powiedz »Nie wiem«, jeśli niepewny" |
| Oddziel | „Oznacz fakt vs wnioskowanie" |
| Cytuj | „Zacytuj zdanie, którego używa każde twierdzenie" |
| Weryfikuj | Ty sprawdzasz nazwiska/liczby/cytowania |

> ⚠️ To zmniejsza, nie usuwa halucynacji. Przy odpowiedziach wysokiej stawki **niezależna weryfikacja jest obowiązkowa**.

---

## ✅ Sprawdzian

- [ ] Osadziłeś/aś odpowiedź w dostarczonym źródle i odmówił wyjścia poza nie.
- [ ] Dałeś/aś modelowi pozwolenie na „Nie wiem".
- [ ] Kazałeś/aś oddzielić fakty od wnioskowań (lub cytować zdania).
- [ ] Zweryfikowałeś/aś twierdzenie faktyczne sam/a.

---

## 🎯 Praca domowa

Zadaj AI pytanie faktyczne z Twojej dziedziny dwoma sposobami: raz otwarcie, raz osadzone w źródle, które wklejasz z „odpowiadaj tylko z tego; powiedz, jeśli tego nie ma". Porównaj. Potem sprawdź jedno twierdzenie z otwartej odpowiedzi — czy się utrzymało?

---

## 💡 Najważniejsze wnioski

- **Halucynacje** biorą się z przewidywania *prawdopodobnego* tekstu — zmniejsz je, **osadzając** odpowiedzi w dostarczonych źródłach.
- **Daj modelowi furtkę** („Nie wiem") i poproś, by **cytował zdania** i **oznaczał niepewność**.
- Te taktyki zmniejszają, ale nie usuwają ryzyka — **weryfikuj sam/a wszystko, co ważne**.

🌐 [English](../../en/lessons/11-reducing-hallucinations.md) · [← Poprzednia](10-kontrola-wyniku.md) · [Strona kursu](../README.md) · [Dalej: Autokrytyka i iteracja →](12-autokrytyka-i-iteracja.md)
