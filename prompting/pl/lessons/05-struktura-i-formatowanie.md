# Lekcja 05 — Struktura i formatowanie promptu

⏱️ **11 minut** · Poziom: Średni · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/05-structure-and-formatting.md) · [← Poprzednia](04-kontekst-i-okno-kontekstowe.md) · [Strona kursu](../README.md) · [Dalej: Few-shot →](06-few-shot.md)

---

## 🧠 Teoria (4 min)

Ściana tekstu myli i ludzi, i modele. **Struktura** czyni Twoją intencję jednoznaczną — i pozwala kontrolować **kształt wyniku**.

Dwa ruchy strukturyzujące robią większość roboty:

1. **Oddziel części promptu.** Użyj nagłówków, numerowanych kroków lub **ograniczników** (jak `"""`, `---` czy tagi w stylu XML), by wyraźnie oddzielić *instrukcje* od *treści do przetworzenia*. To zapobiega myleniu Twoich danych z poleceniami.
2. **Określ format wyniku.** Poproś o dokładnie ten kształt — tabelę, punkty, numerowane kroki, JSON, konkretny szablon. Jeśli nie określisz, dostaniesz domyślny modelu.

Struktura w → struktura z. Dobrze zorganizowany prompt łatwiej modelowi śledzić *i* łatwiej Tobie użyć ponownie.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Oddziel instrukcje od treści

```text
Podsumuj tekst między potrójnymi cudzysłowami w 3 punktach.

"""
[wklej tekst tutaj]
"""
```

Teraz model wie, że blok w cudzysłowach to dane, nie instrukcje.

### Krok 2 — Użyj tagów do wielu wejść

Gdy masz kilka elementów, oznacz je:

```text
<article>…</article>
<audience>zabiegane pielęgniarki</audience>

Zadanie: przepisz <article> dla <audience> na poziomie czytania klasy 9.
```

### Krok 3 — Określ dokładny kształt wyniku

```text
Zwróć tabelę markdown z kolumnami: Opcja | Zalety | Wady | Najlepsze do.
```

Lub ścisły szablon:

```text
Dla każdego elementu wypisz dokładnie:
- Nazwa:
- Jednolinijkowe podsumowanie:
- Ryzyko (niskie/średnie/wysokie):
```

### Krok 4 — Numeruj wieloetapowe instrukcje

```text
Zrób to po kolei:
1. Wypisz kluczowe twierdzenia.
2. Oceń każde jako poparte / niepoparte przez tekst.
3. Daj jeden ogólny werdykt.
```

### Krok 5 — Poproś *tylko* o wynik

By uniknąć wstępu:

```text
Zwróć tylko tabelę, bez wyjaśnień przed ani po.
```

---

## 🧩 Narzędzia strukturyzujące

| Narzędzie | Użyj do |
|------|---------|
| `"""` / `---` / tagi | Oddzielania instrukcji od treści |
| Numerowane kroki | Uporządkowanych, wieloczęściowych zadań |
| „Zwróć tabelę/JSON z…" | Kontroli kształtu wyniku |
| Stały szablon | Spójnego, wielokrotnego użytku wyniku |
| „Wypisz tylko X" | Usuwania wstępu |

---

## ✅ Sprawdzian

- [ ] Użyłeś/aś ograniczników, by oddzielić instrukcje od treści.
- [ ] Oznaczyłeś/aś wiele wejść tagami.
- [ ] Określiłeś/aś dokładny format wyniku (tabela/szablon/JSON).
- [ ] Dostałeś/aś czysty wynik bez niechcianego wstępu.

---

## 🎯 Praca domowa

Weź prompt mieszający instrukcje i wklejoną treść. Przepisz go z jasnymi ogranicznikami i określonym formatem wyniku (tabela lub szablon). Zauważ, o ile spójniejszy jest wynik — i o ile bardziej wielokrotnego użytku prompt.

---

## 💡 Najważniejsze wnioski

- **Ograniczniki/tagi** oddzielają Twoje instrukcje od treści, zapobiegając pomyłce.
- **Określaj format wyniku** (tabela, szablon, JSON, kroki) — inaczej dostaniesz domyślny.
- Strukturyzowane wejście daje **strukturyzowany, wielokrotnego użytku** wynik.

🌐 [English](../../en/lessons/05-structure-and-formatting.md) · [← Poprzednia](04-kontekst-i-okno-kontekstowe.md) · [Strona kursu](../README.md) · [Dalej: Few-shot →](06-few-shot.md)
