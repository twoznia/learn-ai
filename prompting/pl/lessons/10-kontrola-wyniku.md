# Lekcja 10 — Precyzyjna kontrola wyniku

⏱️ **11 minut** · Poziom: Średni → Zaawansowany · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/10-controlling-output.md) · [← Poprzednia](09-dekompozycja-i-lancuchy.md) · [Strona kursu](../README.md) · [Dalej: Ograniczanie halucynacji →](11-ograniczanie-halucynacji.md)

---

## 🧠 Teoria (4 min)

Możesz kontrolować nie tylko *co* model mówi, ale *dokładnie jak* jest to ukształtowane — długość, ton, strukturę, a nawet formaty czytelne dla maszyn. To ważne, gdy wynik zasila dokument, arkusz lub inny program.

Dźwignie, które kontrolujesz:

- **Długość** — „w jednym zdaniu", „dokładnie 5 punktów", „poniżej 100 słów".
- **Ton i rejestr** — „formalny", „dla 10-latka", „bez skrótów".
- **Struktura** — tabela, szablon, numerowane kroki (Lekcja 5).
- **Formaty maszynowe** — **JSON**, CSV lub ścisły schemat, gdy odczyta to program.

Zasada: **podaj ograniczenie wprost i uczyń je sprawdzalnym.** „Krótki" jest niejasny; „poniżej 50 słów" jest egzekwowalny.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Przypnij długość

```text
Podsumuj to w dokładnie 3 punktach, każdy poniżej 12 słów.
```

### Krok 2 — Kontroluj ton precyzyjnie

```text
Przepisz dla ogólnego odbiorcy: bez żargonu, przyjaźnie ale nie potocznie i bez
wykrzykników.
```

### Krok 3 — Poproś o JSON (dla programów)

```text
Zwróć TYLKO poprawny JSON, bez prozy, w tym schemacie:
{"title": string, "tags": string[], "priority": "low"|"medium"|"high"}
```

Prośba o „tylko JSON" unika owinięcia go gadaniną.

### Krok 4 — Daj ścisły szablon

```text
Dla każdej książki wypisz dokładnie:
Tytuł | Autor | Jednolinijkowy haczyk | Przedział wiekowy
```

### Krok 5 — Ogranicz przykładem (few-shot)

Połącz z Lekcją 6, gdy format musi być idealny:

```text
Formatuj jak: „2026-03-01 — Standup — 15m". Teraz sformatuj te wpisy: …
```

### Krok 6 — Zweryfikuj, że ograniczenie się utrzymało

Sprawdź wynik wobec reguły (liczba słów, poprawny JSON). Jeśli zadryfował, powtórz ograniczenie mocniej: „Przekroczyłeś 50 słów. Zrób od nowa poniżej 50."

---

## 🧩 Kontrole wyniku

| Chcesz | Powiedz |
|------|-----|
| Długość | „poniżej 100 słów" / „dokładnie 5 punktów" |
| Ton | „formalny, trzecia osoba, bez skrótów" |
| Tabela | „tabela markdown z kolumnami …" |
| Czytelne dla maszyn | „zwróć TYLKO poprawny JSON w tym schemacie" |
| Bez wstępu | „wypisz tylko wynik" |

> ⚠️ Nawet przy ścisłym schemacie **waliduj** wynik maszynowy, zanim program go skonsumuje — modele mogą czasem złamać format.

---

## ✅ Sprawdzian

- [ ] Przypiąłeś/ęłaś dokładną długość i utrzymała się.
- [ ] Kontrolowałeś/aś ton konkretnymi regułami.
- [ ] Dostałeś/aś czysty JSON instrukcją „tylko JSON".
- [ ] Powtórzyłeś/aś ograniczenie, gdy wynik zadryfował.

---

## 🎯 Praca domowa

Weź zadanie, którego wynik gdzieś wkleisz (dokument, arkusz, kod). Napisz prompt trafiający dokładny format — długość, strukturę lub schemat JSON — i zwaliduj wynik. Zapisz prompt jako szablon wielokrotnego użytku.

---

## 💡 Najważniejsze wnioski

- Kontroluj **długość, ton, strukturę i formaty maszynowe**, podając każde ograniczenie **wprost i sprawdzalnie**.
- Poproś o **„tylko JSON"** (lub ścisły szablon), gdy program lub dokument skonsumuje wynik.
- Zawsze **waliduj**, że ograniczenie się utrzymało — powtórz je mocno, gdy wynik dryfuje.

🌐 [English](../../en/lessons/10-controlling-output.md) · [← Poprzednia](09-dekompozycja-i-lancuchy.md) · [Strona kursu](../README.md) · [Dalej: Ograniczanie halucynacji →](11-ograniczanie-halucynacji.md)
