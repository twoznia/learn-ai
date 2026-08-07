# Lekcja 14 — Zbuduj bibliotekę wzorców promptów

⏱️ **11 minut** · Poziom: Średni · Wymagania: dowolny czat AI, Twój `my-prompts.md`

🌐 [English](../../en/lessons/14-prompt-pattern-library.md) · [← Poprzednia](13-dlugie-dokumenty.md) · [Strona kursu](../README.md) · [Dalej: Ewaluacja promptów →](15-ewaluacja-promptow.md)

---

## 🧠 Teoria (4 min)

Profesjonaliści nie wymyślają promptów za każdym razem od nowa — używają ponownie **wzorców**: sprawdzonych szablonów z lukami do wypełnienia. Po 13 lekcjach masz elementy; teraz organizujesz je w osobistą **bibliotekę**, z której czerpiesz natychmiast.

Dobry wzorzec jest:
- **Sparametryzowany** — stała struktura, luki na zmienne części (`[temat]`, `[odbiorca]`).
- **Przetestowany** — widziałeś/aś, że działa, więc mu ufasz.
- **Oznaczony** — nazwany zadaniem, które robi, byś go znalazł/a.

Kilka wzorców wartych posiadania: **Podsumuj**, **Przepisz w stylu**, **Wyodrębnij do tabeli/JSON**, **Wyjaśnij prosto**, **Skrytykuj i ulepsz**, **Porównaj opcje**, **Naszkicuj i dopracuj**. Buduj swoje z prawdziwych zadań.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Zamień sukces w szablon

Weź prompt, który zadziałał, i zastąp konkrety slotami:

```text
[ROLA]. Podsumuj [TREŚĆ] dla [ODBIORCY] w [N] punktach, każdy poniżej [LIMIT]
słów. Skup się na [FOKUS]. Wypisz tylko punkty.
```

### Krok 2 — Napisz 3 podstawowe wzorce

Dodaj je do `my-prompts.md`, każdy ze slotami:

```text
## Wyodrębnij do tabeli
Z [ŹRÓDŁA] wyodrębnij do tabeli: [KOL1] | [KOL2] | [KOL3].
Zacytuj tekst źródłowy dla każdego wiersza. Wypisz tylko tabelę.
```
```text
## Wyjaśnij prosto
Jesteś cierpliwym korepetytorem. Wyjaśnij [POJĘCIE] dla [ODBIORCY] z jedną analogią,
potem 1-zdaniową precyzyjną definicją. Poniżej [N] słów, bez żargonu.
```
```text
## Skrytykuj i ulepsz
Skrytykuj poniższy tekst wobec [KRYTERIÓW]. Wypisz słabości, potem mocniejszą
wersję. Tekst: """[TEKST]"""
```

### Krok 3 — Organizuj według zadania

Grupuj wzorce pod nagłówkami: *Pisanie, Analiza, Dane, Nauka, Kod*. Szybkie znalezienie właściwego to cały sens.

### Krok 4 — Zanotuj, kiedy każdy działa

Pod każdym wzorcem dodaj linię: *„Najlepszy do… / nie do…"*, by przyszły Ty wybierał poprawnie.

### Krok 5 — Używaj ponownie stałych wzorców

Wzorce, których używasz ciągle, awansuj do **zapisanych asystentów** narzędzia (Custom GPT, Gem, Projekt Claude) lub własnych instrukcji (Lekcja 7) — wzorzec, którego nigdy nie musisz wklejać.

---

## 🧩 Biblioteka startowa

| Wzorzec | Zadanie |
|---------|-----|
| Podsumuj | Skondensuj do N punktów dla odbiorcy |
| Przepisz w stylu | Dopasuj ton/rejestr |
| Wyodrębnij do tabeli/JSON | Wyciągnij dane strukturalne |
| Wyjaśnij prosto | Naucz pojęcia |
| Skrytykuj i ulepsz | Pętla samoredakcji |
| Porównaj opcje | Tabele decyzyjne |

---

## ✅ Sprawdzian

- [ ] Przekształciłeś/aś działający prompt w sparametryzowany szablon.
- [ ] Zapisałeś/aś co najmniej 3 podstawowe wzorce, uporządkowane według zadania.
- [ ] Każdy wzorzec ma notkę „najlepszy do / nie do".
- [ ] Awansowałeś/aś jeden wzorzec do zapisanego asystenta lub własnych instrukcji.

---

## 🎯 Praca domowa

Rozbuduj bibliotekę do 6–8 przetestowanych wzorców pokrywających zadania, które robisz najczęściej. Użyj jednego w tym tygodniu wprost z biblioteki (wypełnij sloty, uruchom) i dopracuj szablon na podstawie wyniku.

---

## 💡 Najważniejsze wnioski

- Używaj ponownie **sparametryzowanych, przetestowanych, oznaczonych wzorców** zamiast przepisywać prompty za każdym razem.
- Organizuj bibliotekę **według zadania** z notkami „najlepszy do / nie do".
- Awansuj najczęściej używane wzorce do **zapisanych asystentów / własnych instrukcji**, byś nigdy ich nie wklejał ponownie.

🌐 [English](../../en/lessons/14-prompt-pattern-library.md) · [← Poprzednia](13-dlugie-dokumenty.md) · [Strona kursu](../README.md) · [Dalej: Ewaluacja promptów →](15-ewaluacja-promptow.md)
