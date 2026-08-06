# G3 — Podagenci

⏱️ **15 minut** · Ścieżka: 🅶 Claude Code w głąb · Potrzebne: Claude Code zainstalowany i zalogowany

🌐 [English](../../en/track-g/03-subagents.md) · [← Wstecz](02-komendy-ukosnik.md) · [Indeks ścieżki](../README.md) · [Dalej: Haki →](04-haki.md)

---

## 🧠 Teoria (4 min)

**Podagent** to wyspecjalizowany pomocnik, któremu Claude Code może oddać skupione zadanie — z **własnymi instrukcjami, własnymi narzędziami i własnym świeżym kontekstem**. Główny agent trzyma się szerokiego obrazu i **deleguje** wąskie zadanie.

Czemu to potężne:

- **Skupienie.** Podagent „recenzent” robi tylko recenzję; „pisarz testów” tylko testy. Jasna rola = lepsze wyjście.
- **Czysty kontekst.** Każdy podagent startuje świeżo, więc duże śledztwo nie zapycha głównej rozmowy.
- **Praca prawie równoległa.** Główny agent może rozdzielać niezależne zadania do podagentów zamiast robić wszystko w jednym wątku.

Podagent jest definiowany małym **plikiem Markdown z nagłówkiem frontmatter** — nazwa, opis, które narzędzia może użyć, opcjonalnie który model. Claude czyta opis, by zdecydować, kiedy go użyć.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Utwórz podagenta przez `/agents`

W Claude Code:

```text
/agents
```

Podążaj za podpowiedziami, by utworzyć nowego podagenta. Zapisze plik Markdown (w `.claude/agents/`), który możesz otworzyć i edytować.

### Krok 2 — Zrozum kształt pliku

Plik podagenta wygląda tak:

```markdown
---
name: reviewer
description: Recenzuje ostatnie zmiany kodu pod kątem błędów, jasności i ryzyka. Użyj po edycjach.
tools: Read, Grep, Glob
model: sonnet
---

Jesteś starannym recenzentem kodu. Patrz tylko na to, co się zmieniło.
Raportuj znaleziska jako listę, od najpoważniejszych, każde z file:line i jednolinijkową poprawką.
Nie edytuj plików — tylko raportuj.
```

- **name** — jak się do niego odwołuje.
- **description** — *kiedy* go użyć (Claude to czyta, by delegować).
- **tools** — wąski zestaw dozwolony (najmniejsze uprawnienia!).
- **model** — opcjonalny; lżejszy model do prostych pomocników oszczędza użycie.
- **body** — jego prompt systemowy / rola.

### Krok 3 — Pozwól go używać automatycznie

Zrób zmianę, potem poproś głównego agenta o recenzję — powinien **delegować** do Twojego recenzenta:

```text
Właśnie edytowałem funkcję logowania. Zrecenzuj moje ostatnie zmiany.
```

Patrz, jak główny agent przekazuje do podagenta `reviewer`, który raportuje z powrotem. Główny wątek zostaje czysty.

### Krok 4 — Wywołaj jednego wprost

Możesz też wołać podagenta po nazwie:

```text
Użyj podagenta reviewer na plikach, które zmieniłem dzisiaj.
```

### Krok 5 — Zbuduj mały zespół

Dodaj kilku skupionych pomocników:

- `tester` — „Napisz i uruchom testy dla kodu, który wskażę; raportuj pass/fail.” (narzędzia obejmują uruchamianie testów)
- `explainer` — „Wyjaśnij nieznany plik dla początkującego.” (tylko-odczyt)

Daj każdemu **najwęższe narzędzia**, których potrzebuje. Recenzent/explainer tylko-odczyt nie może przypadkiem niczego zmienić.

### Krok 6 — Wiedz, kiedy NIE delegować

Podagenci dodają narzut (każdy ustala kontekst od nowa). Do szybkiej edycji jednego pliku główny agent jest szybszy. Deleguj **skupioną, niezależną lub powtarzalną** pracę — recenzje, testy, śledztwa — nie trywialne jednolinijkowce.

---

## 🧩 Projektowanie dobrych podagentów

| Pole | Zrób dobrze |
|-------|--------------|
| `name` | Krótkie, jak rola (`reviewer`, `tester`) |
| `description` | Powiedz *kiedy* użyć — Claude po tym routuje |
| `tools` | Najwęższy zestaw (tylko-odczyt do recenzji/wyjaśnień) |
| `model` | Lżejszy model do prostych pomocników oszczędza użycie |
| body | Jedna jasna rola, jeden jasny format wyjścia |

> **Bezpieczeństwo = najmniejsze uprawnienia.** Podagent może użyć tylko narzędzi, które wypiszesz. Trzymaj recenzentów/explainerów tylko-odczyt, by delegacja nie mogła spowodować niespodziewanych edycji.

---

## ✅ Sprawdzenie

- [ ] Utworzyłeś podagenta przez `/agents` i przeczytałeś jego plik Markdown.
- [ ] Rozumiesz name / description / tools / model / body.
- [ ] Główny agent **delegował** do Twojego podagenta automatycznie.
- [ ] Dałeś podagentowi narzędzia najmniejszych uprawnień.

---

## 🎯 Zadanie

Utwórz `reviewer` (tylko-odczyt) i jeszcze jednego skupionego podagenta do powtarzalnego zadania. Daj każdemu precyzyjny opis i najwęższe narzędzia. Potem uruchom prawdziwą zmianę i potwierdź, że główny agent deleguje do właściwego.

---

## 💡 Najważniejsze wnioski

- **Podagenci** to wyspecjalizowani pomocnicy z **własnymi instrukcjami, narzędziami i świeżym kontekstem** — główny agent deleguje skupioną pracę.
- Definiowani przez **plik Markdown z frontmatter** (`.claude/agents/`): name, description, tools, model, body — zarządzaj przez `/agents`.
- **Najmniejsze uprawnienia** i **jasne opisy** czynią delegację bezpieczną i trafną; nie deleguj trywialnych jednolinijkowców.

🌐 [English](../../en/track-g/03-subagents.md) · [← Wstecz](02-komendy-ukosnik.md) · [Indeks ścieżki](../README.md) · [Dalej: Haki →](04-haki.md)
