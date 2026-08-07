# Lekcja 02 — Anatomia mocnego promptu

⏱️ **11 minut** · Poziom: Początkujący · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/02-anatomy-of-a-prompt.md) · [← Poprzednia](01-czym-jest-inzynieria-promptow.md) · [Strona kursu](../README.md) · [Dalej: Bądź konkretny →](03-badz-konkretny.md)

---

## 🧠 Teoria (4 min)

Większość mocnych promptów zawiera te same **klocki**. Nie użyjesz wszystkich za każdym razem, ale ich znajomość zamienia „napisz prompt" w wypełnianie listy kontrolnej.

| Klocek | Co robi | Przykład |
|-------|--------------|---------|
| **Rola** | Kim ma być AI | „Jesteś cierpliwym korepetytorem matematyki." |
| **Zadanie** | Jeden jasny cel | „Wyjaśnij twierdzenie Pitagorasa." |
| **Kontekst** | Potrzebne tło | „Czytelnik to 12-latek początkujący." |
| **Format** | Kształt wyniku | „Użyj 3 krótkich kroków i jednego przykładu." |
| **Ograniczenia** | Limity i reguły | „Bez żargonu. Poniżej 120 słów." |
| **Przykłady** | Wzór do naśladowania | „Tak jak to: …" |

Pomyśl **R-Z-K-F-O**: Rola, Zadanie, Kontekst, Format, Ograniczenia (przykłady, gdy pomagają). Prompt, który je nazywa, zostawia mało miejsca, by AI źle zgadło.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Buduj po jednym klocku

Zacznij minimalnie:

```text
Wyjaśnij rekurencję.
```

Dodaj **rolę** i **odbiorcę/kontekst**:

```text
Jesteś przyjaznym korepetytorem programowania. Wyjaśnij rekurencję komuś, kto
nigdy nie programował.
```

Dodaj **format** i **ograniczenia**:

```text
Jesteś przyjaznym korepetytorem programowania. Wyjaśnij rekurencję komuś, kto
nigdy nie programował. Użyj najpierw analogii z życia, potem 3 krótkich punktów.
Zmieść się w 150 słowach i unikaj kodu.
```

Uruchom każdą wersję i obserwuj, jak odpowiedź się wyostrza.

### Krok 2 — Użyj szablonu

Trzymaj ten szkielet w dzienniku i wypełniaj:

```text
Rola: Jesteś ____.
Zadanie: ____.
Kontekst: ____.
Format: ____.
Ograniczenia: ____.
```

### Krok 3 — Dodaj przykład (opcjonalnie)

Jeśli kształt ma znaczenie, pokaż jeden:

```text
Formatuj tak:
Termin — jednolinijkowa definicja — malutki przykład
```

### Krok 4 — Przytnij, czego nie potrzebujesz

Nie każdy prompt potrzebuje roli czy przykładów. Zawrzyj klocek tylko, gdy **zmienia odpowiedź**. Klarowność bije długość.

---

## 🧩 Szablon do wypełnienia

| Klocek | Twój prompt |
|-------|-------------|
| Rola | „Jesteś…" |
| Zadanie | „Twoim zadaniem jest…" |
| Kontekst | „Sytuacja to…" |
| Format | „Odpowiedz jako…" |
| Ograniczenia | „Reguły: …" |

---

## ✅ Sprawdzian

- [ ] Umiesz wymienić główne klocki promptu (rola, zadanie, kontekst, format, ograniczenia).
- [ ] Zbudowałeś/aś prompt, dodając klocek po klocku, i zobaczyłeś/aś poprawę.
- [ ] Zapisałeś/aś szablon do dziennika.
- [ ] Umiesz wyjaśnić, kiedy *pominąć* klocek.

---

## 🎯 Praca domowa

Wybierz prawdziwe zadanie i napisz je pełnym szablonem R-Z-K-F-O. Potem usuń każdy klocek, który nie zmienił wyniku. Zapisz oszczędną wersję finalną — uczysz się zawierać dokładnie to, co potrzebne.

---

## 💡 Najważniejsze wnioski

- Mocne prompty budują się z **Roli, Zadania, Kontekstu, Formatu, Ograniczeń** (plus przykłady, gdy przydatne).
- Dodawaj każdy klocek tylko, gdy **zmienia odpowiedź** — klarowność bije długość.
- Szablon **do wypełnienia** zamienia pisanie promptów w powtarzalną listę kontrolną.

🌐 [English](../../en/lessons/02-anatomy-of-a-prompt.md) · [← Poprzednia](01-czym-jest-inzynieria-promptow.md) · [Strona kursu](../README.md) · [Dalej: Bądź konkretny →](03-badz-konkretny.md)
