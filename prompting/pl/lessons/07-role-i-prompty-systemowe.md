# Lekcja 07 — Role i prompty systemowe

⏱️ **11 minut** · Poziom: Średni · Wymagania: dowolny czat AI

🌐 [English](../../en/lessons/07-role-and-system-prompts.md) · [← Poprzednia](06-few-shot.md) · [Strona kursu](../README.md) · [Dalej: Rozumowanie krok po kroku →](08-rozumowanie-krok-po-kroku.md)

---

## 🧠 Teoria (4 min)

Powiedzenie AI, **kim ma być**, kształtuje *jak* odpowiada. **Rola** (lub persona) ustawia głos, głębię i priorytety w jednej linii — „Jesteś sceptycznym redaktorem", „Jesteś przyjazną panią przedszkolanką", „Jesteś starszym inżynierem bezpieczeństwa".

Rola może mieszkać w dwóch miejscach:

- **W Twojej wiadomości** — „Działaj jak dietetyk i…". Działa w każdym czacie.
- **W promptcie systemowym / własnych instrukcjach** — stała rola stosowana do *każdej* wiadomości: własne instrukcje ChatGPT, Projekty/prompt systemowy Claude, Gemy/zapisane info Gemini. Ustaw raz; trwa.

Rola nie jest magią — nie da modelowi wiedzy, której nie ma. Ale niezawodnie steruje **tonem, poziomem szczegółu i tym, co model priorytetyzuje**, co często jest dokładnie tym, czego potrzebujesz.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Ustaw rolę w wiadomości

```text
Jesteś cierpliwym korepetytorem dla zupełnie początkujących. Wyjaśnij, czym jest
API, używając analogii restauracyjnej, potem jednozdaniowej definicji technicznej.
```

### Krok 2 — Zmień rolę, to samo zadanie

```text
Jesteś starszym inżynierem backendu instruującym kolegę. Wyjaśnij, czym jest API,
zakładając, że zna programowanie. Bądź precyzyjny i zwięzły.
```

Ten sam temat, bardzo różna odpowiedź — sterujesz rolą.

### Krok 3 — Dodaj priorytety do roli

Rola może nieść wartości:

```text
Jesteś ostrożnym autorem medycznym. Priorytetyzuj dokładność nad płynnością,
oznaczaj niepewność wprost i nigdy nie podawaj jako faktu czegoś, czego nie jesteś pewien.
```

### Krok 4 — Uczyń ją stałą (system / własne instrukcje)

Umieść rolę, którą powtarzasz, w trwałych ustawieniach narzędzia:

```text
Zawsze odpowiadaj jako zwięzły, praktyczny mentor. Zacznij od odpowiedzi, potem
krótkie „dlaczego". Jestem na Windowsie. Unikaj wypełniaczy i hype'u.
```

Teraz każdy nowy czat startuje w tym głosie.

### Krok 5 — Połącz rolę + format + ograniczenia

Role układają się z wcześniejszymi lekcjami:

```text
Jesteś UX writerem. Przepisz te 3 komunikaty błędów, by były przyjazne i jasne,
poniżej 12 słów każdy, bez języka obwiniania. Zwróć tabelę: Oryginał | Przepisane.
```

---

## 🧩 Gdzie mieszkają role

| Miejsce | Zasięg | Przykłady |
|-------|-------|----------|
| W wiadomości | Ten czat/tura | „Działaj jak…" |
| System / własne instrukcje | Każdy czat | Własne instrukcje ChatGPT, Projekty Claude, Gemy Gemini |
| Zapisany asystent | Wielokrotnego użytku persona | Custom GPT, Gem, Projekt Claude |

> Rola steruje **tonem, głębią, priorytetami** — nie wiedzą. Sparuj ją z prawdziwym kontekstem (Lekcja 4), gdy fakty mają znaczenie.

---

## ✅ Sprawdzian

- [ ] Ustawiłeś/aś rolę w wiadomości i zobaczyłeś/aś, jak kształtuje odpowiedź.
- [ ] Zmieniłeś/aś tylko rolę i dostałeś/aś bardzo różną odpowiedź.
- [ ] Dodałeś/aś priorytety/wartości do roli.
- [ ] Ustawiłeś/aś stałą rolę w trwałych ustawieniach narzędzia.

---

## 🎯 Praca domowa

Napisz jedną stałą rolę tego, jak chcesz, by AI z Tobą rozmawiało (ton, głębia, czego unikać) i umieść ją we własnych instrukcjach / personie narzędzia. Używaj jej przez dzień i dopracuj brzmienie, aż odpowiedzi będą domyślnie pasować.

---

## 💡 Najważniejsze wnioski

- **Rola** ustawia głos, głębię i priorytety w jednej linii — sterując *jak* AI odpowiada.
- Role mogą być **na wiadomość** lub **stałe** (prompty systemowe / własne instrukcje / zapisani asystenci).
- Rola kształtuje **ton i priorytety, nie wiedzę** — połącz ją z prawdziwym kontekstem.

🌐 [English](../../en/lessons/07-role-and-system-prompts.md) · [← Poprzednia](06-few-shot.md) · [Strona kursu](../README.md) · [Dalej: Rozumowanie krok po kroku →](08-rozumowanie-krok-po-kroku.md)
