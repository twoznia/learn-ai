# Lekcja 03 — Podstawy tworzenia promptów

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: konto chatgpt.com

🌐 [English](../../en/lessons/03-prompting-basics.md) · [← Wstecz](02-pierwsza-rozmowa.md) · [Strona kursu](../README.md) · [Dalej: Pliki i obrazy →](04-pliki-i-obrazy.md)

---

## 🧠 Teoria (4 min)

**Prompt** to Twoja instrukcja dla ChatGPT. Różnica między przeciętną a świetną odpowiedzią prawie zawsze wynika z promptu.

### 4 składniki świetnego promptu (**R-K-Z-F**)

| Składnik | Na jakie pytanie odpowiada | Przykład |
|-----------|---------------------|---------|
| **R — Rola** | Kim ma być ChatGPT? | „Jesteś przyjaznym pracownikiem helpdesku IT.” |
| **K — Kontekst** | Jaka jest sytuacja? | „Moja mama, 70 lat, nie może otworzyć e-maila.” |
| **Z — Zadanie** | Czego dokładnie chcesz? | „Napisz instrukcje krok po kroku.” |
| **F — Format** | Jak ma wyglądać odpowiedź? | „Lista numerowana, maks. 6 kroków, bez żargonu.” |

Samo dodanie **Formatu** znacząco poprawia efekty.

### Słaby vs mocny prompt

❌ **Słaby:**
```text
pomóż z e-mailem
```

✅ **Mocny:**
```text
Jesteś przyjaznym pomocnikiem IT. Moja mama (70 lat) używa laptopa z Windows i nie
może otworzyć e-maila. Napisz jasne instrukcje krok po kroku, jak otworzyć Outlooka w sieci.
Format: lista numerowana, maksymalnie 6 kroków, bez technicznego żargonu.
```

Ten sam temat, zupełnie inna jakość.

---

## 🛠️ Praktyka (5 min)

### Ćwiczenie 1 — Dodaj format i patrz, jak się zmienia

Najpierw:
```text
Podaj pomysły na obiad.
```

Potem, w tej samej rozmowie:
```text
Teraz przerób to na tabelę z 3 kolumnami: Danie, Główny składnik, Czas gotowania.
Uwzględnij tylko dania poniżej 30 minut.
```

### Ćwiczenie 2 — Użyj Roli

```text
Jesteś cierpliwym korepetytorem matematyki dla 10-latka. Wyjaśnij, czym jest ułamek,
na przykładzie pizzy. Zmieść się w 100 słowach i zakończ jednym pytaniem do ćwiczenia.
```

### Ćwiczenie 3 — Daj ChatGPT „furtkę”

```text
Jeśli nie jesteś pewny jakiegoś faktu, napisz „Nie jestem pewny” zamiast zgadywać.
```

Wypróbuj:
```text
Ile dokładnie mieszkańców miało moje miasto w zeszły wtorek? Jeśli nie jesteś pewny,
napisz „Nie jestem pewny” zamiast zgadywać.
```

Dobra odpowiedź to przyznanie się przez ChatGPT, że nie może tego wiedzieć.

---

## 🧰 5 wzorców promptów do wielokrotnego użytku (skopiuj je)

**1. Streszczacz**
```text
Streść poniższy tekst w 5 punktach, które zajęta osoba przeczyta w 20 sekund.
Następnie dodaj jedną linię: „Podsumowanie: ...”.

TEKST:
<wklej tekst tutaj>
```

**2. Wyjaśniacz**
```text
Wyjaśnij mi <temat> jak mądremu początkującemu. Użyj jednej codziennej analogii,
unikaj żargonu i zmieść się w 150 słowach.
```

**3. Przeredagowywacz**
```text
Przeredaguj poniższą wiadomość, aby brzmiała uprzejmie, jasno i profesjonalnie.
Zmieść się w 4 zdaniach.

WIADOMOŚĆ:
<wklej wiadomość>
```

**4. Burza mózgów**
```text
Podaj 10 pomysłów na <cel>. Zróżnicuj je: część bezpieczna, część odważna. Po jednej linii.
```

**5. Krok po kroku**
```text
Podaj plan krok po kroku, jak <zadanie>. Ponumeruj kroki, niech będą krótkie,
i powiedz, co zrobić najpierw dzisiaj.
```

---

## ✅ Sprawdzenie

- [ ] Potrafisz wymienić składniki **R-K-Z-F**.
- [ ] Zobaczyłeś, jak dodanie **Formatu** zmieniło odpowiedź.
- [ ] Zapisałeś 5 wzorców gdzieś do ponownego użycia.

---

## 🎯 Zadanie

Weź swoje „irytujące zadanie” i napisz **jeden mocny prompt** używając wszystkich czterech składników R-K-Z-F. Zapisz go w pliku `moje-prompty.txt`.

---

## 💡 Najważniejsze wnioski

- Świetne prompty = **Rola + Kontekst + Zadanie + Format**.
- Dodanie instrukcji **Formatu** to najłatwiejsza duża wygrana.
- Daj ChatGPT prawo powiedzieć „Nie jestem pewny”, aby ograniczyć halucynacje.

🌐 [English](../../en/lessons/03-prompting-basics.md) · [← Wstecz](02-pierwsza-rozmowa.md) · [Strona kursu](../README.md) · [Dalej: Pliki i obrazy →](04-pliki-i-obrazy.md)
