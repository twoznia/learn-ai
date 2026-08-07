# Lekcja 06 — Few-shot (przykłady, które sterują)

⏱️ **11 minut** · Poziom: Średni · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/06-few-shot-prompting.md) · [← Poprzednia](05-struktura-i-formatowanie.md) · [Strona kursu](../README.md) · [Dalej: Role i prompty systemowe →](07-role-i-prompty-systemowe.md)

---

## 🧠 Teoria (4 min)

Czasem najszybszy sposób wyjaśnienia, czego chcesz, to **pokazać** to. Danie modelowi kilku przykładów wejście→wyjście w promptcie to **few-shot** (w przeciwieństwie do **zero-shot**, gdzie tylko opisujesz zadanie).

Dlaczego działa: LLM-y są znakomitymi dopasowywaczami wzorców. Kilka dobrych przykładów przypina ton, format i obsługę przypadków brzegowych znacznie precyzyjniej niż przymiotniki.

Kiedy którego użyć:

- **Zero-shot** — zadanie jest pospolite i jasne („przetłumacz to na francuski"). Opis wystarczy.
- **Few-shot** — kształt wyniku jest konkretny, styl subtelny lub wciąż dostajesz *prawie* to. Pokaż 2–4 przykłady.

Przykłady uczą *wzorca*; model stosuje go do Twojego nowego wejścia.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Zamień mglistą prośbę w przykłady

Zamiast „uczyń nazwy produktów chwytliwymi", pokaż wzorzec:

```text
Przepisz każdą funkcję jako chwytliwą nazwę. Przykłady:

Funkcja: automatycznie synchronizuje pliki → Nazwa: „Zawsze w synchronizacji"
Funkcja: działa bez internetu → Nazwa: „Gotowe offline"

Teraz zrób te:
Funkcja: udostępnia jednym kliknięciem →
Funkcja: robi kopię co godzinę →
```

### Krok 2 — Użyj przykładów, by naprawić dryf formatu

Jeśli model wciąż zmienia format, jeden przykład go blokuje:

```text
Sklasyfikuj sentyment. Formatuj dokładnie jak w przykładzie.

Wejście: „Aplikacja ciągle się zawiesza." → Wyjście: NEGATYWNY (niezawodność)

Wejście: „Uwielbiam nowy design!" →
```

### Krok 3 — Pokaż przypadek brzegowy

Przykłady świetnie uczą wyjątków:

```text
Wyodrębnij datę jako YYYY-MM-DD. Jeśli brak daty, wypisz „BRAK".

„Spotkanie 3 marca 2026" → 2026-03-03
„Zadzwoń kiedyś" → BRAK

„Wyślij do 25.12.2026" →
```

### Krok 4 — Trzymaj przykłady spójne

Twoje przykłady to kontrakt. Jeśli są niespójne, wynik też będzie. Niech każdy podąża za *dokładnym* wzorcem, którego chcesz.

### Krok 5 — Nie przesadzaj

2–4 mocne, zróżnicowane przykłady zwykle biją dziesięć powtarzalnych (i kosztują mniej kontekstu). Dodaj przykład tylko, gdy uczy czegoś nowego.

---

## 🧩 Zero-shot vs few-shot

| | Zero-shot | Few-shot |
|--|-----------|----------|
| Dajesz | Opis | Opis + przykłady |
| Najlepszy gdy | Pospolite, jasne zadanie | Konkretny format, subtelny styl, przypadki brzegowe |
| Koszt | Najtańszy | Trochę więcej kontekstu |
| Supermoc | Szybki | Precyzyjny, spójny |

---

## ✅ Sprawdzian

- [ ] Napisałeś/aś prompt few-shot z 2–4 spójnymi przykładami.
- [ ] Użyłeś/aś przykładu, by zablokować konkretny format wyniku.
- [ ] Nauczyłeś/aś przypadku brzegowego przez przykład.
- [ ] Umiesz powiedzieć, kiedy zero-shot wystarczy, a kiedy dodać przykłady.

---

## 🎯 Praca domowa

Weź zadanie, gdzie AI wciąż daje *prawie* właściwy format. Dodaj 2–3 przykłady demonstrujące dokładny wzorzec (w tym jeden przypadek brzegowy). Potwierdź, że wynik teraz pasuje, i zapisz prompt few-shot do dziennika.

---

## 💡 Najważniejsze wnioski

- **Few-shot** = pokaż 2–4 przykłady wejście→wyjście; **zero-shot** = tylko opisz zadanie.
- Używaj przykładów, gdy **format jest konkretny, styl subtelny lub potrzebujesz obsługi przypadków brzegowych**.
- Przykłady to **kontrakt** — trzymaj je spójne, zróżnicowane i minimalne.

🌐 [English](../../en/lessons/06-few-shot-prompting.md) · [← Poprzednia](05-struktura-i-formatowanie.md) · [Strona kursu](../README.md) · [Dalej: Role i prompty systemowe →](07-role-i-prompty-systemowe.md)
