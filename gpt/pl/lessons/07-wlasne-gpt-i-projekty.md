# Lekcja 07 — Własne GPT i Projekty

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: konto ChatGPT

🌐 [English](../../en/lessons/07-custom-gpts-and-projects.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)

---

## 🧠 Teoria (3 min)

Dotąd każda nowa rozmowa zaczynała się od zera. Dwie funkcje ChatGPT to zmieniają:

- **Instrukcje własne** — ustawienia mówiące ChatGPT, jak ma odpowiadać we *wszystkich* rozmowach (kim jesteś, ton, zasady).
- **Własne GPT** — zapisana wersja ChatGPT z własnymi instrukcjami (i opcjonalnie plikami), którą otwierasz, a ona już zachowuje się tak, jak ustawiłeś.
- **Projekty** — przestrzeń grupująca powiązane rozmowy, mogąca zawierać **pliki + instrukcje**, które wszystkie współdzielą.

Wyobraź sobie danie ChatGPT **opisu stanowiska**, o którym nigdy nie zapomni — przestajesz się powtarzać.

> Dostępność zależy od planu (część funkcji jest w płatnych poziomach). Jeśli którejś nie ma, uzyskasz większość korzyści, zapisując **blok kontekstu** wklejany na początku rozmów (poniżej).

---

## 🛠️ Praktyka (6 min)

### Ścieżka A — Instrukcje własne (dla większości)

1. W ChatGPT otwórz **Settings → Personalization → Custom instructions** (lub kliknij swoją nazwę/awatar).
2. Wypełnij pola — w „How would you like ChatGPT to respond?” wklej:

```text
- Odbiorca: ja, zajęty nietechniczny profesjonalista.
- Ton: ciepły, jasny, zwięzły. Bez żargonu, chyba że go zdefiniujesz.
- Zawsze kończ dłuższe odpowiedzi krótką linią „Następny krok:”.
- Jeśli prośba jest niejednoznaczna, zadaj jedno pytanie doprecyzowujące przed odpowiedzią.
- Jeśli nie jesteś pewny faktu, powiedz to, zamiast zgadywać.
```

3. Zapisz. Teraz każda rozmowa automatycznie przestrzega tych zasad.

### Ścieżka B — Własny GPT lub Projekt (jeśli dostępne)

1. W panelu bocznym poszukaj **GPTs / „Explore GPTs” → Create** lub **Projects → New project**.
2. Nadaj nazwę (np. **„Mój Asystent”**) i wklej te same instrukcje.
3. Dodaj plik, jeśli przydatny (przewodnik stylu, CV). Rozpocznij rozmowę *wewnątrz* — już zna zasady.

### Ścieżka C — Odpowiednik darmowy (dla każdego)

Zapisz to jako `blok-kontekstu.txt` i wklej na **początku** dowolnej rozmowy:

```text
KONTEKST TEJ ROZMOWY (przestrzegaj tych zasad):
- Działaj jako mój osobisty asystent pracy.
- Jestem nietechniczny; upraszczaj i unikaj żargonu.
- Bądź zwięzły i kończ linią „Następny krok:”.
- Zadaj jedno pytanie doprecyzowujące, jeśli prośba jest niejasna.
- Powiedz „Nie jestem pewny” zamiast zgadywać fakty.

Moja prośba:
```

### Przetestuj

Wypróbuj tę samą niejasną prośbę z instrukcjami i bez:
```text
pomóż mi z newsletterem
```
Z instrukcjami ChatGPT powinien zadać trafne pytanie i dopasować ton. Bez nich zgaduje.

---

## 🧩 Dobre składniki instrukcji

| Cel | Linia do dodania |
|------|-------------|
| Spójny ton | „Pisz w przyjaznym, profesjonalnym tonie.” |
| Krótsze odpowiedzi | „Domyślnie zwięźle; rozwijaj tylko, gdy poproszę.” |
| Mniej błędnych faktów | „Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.” |
| Nastawienie na działanie | „Zakończ jasnym następnym krokiem.” |
| Twoja dziedzina | „Pracuję w <branża>; zakładaj ten kontekst.” |

---

## ✅ Sprawdzenie

- [ ] Ustawiłeś instrukcje własne **lub** zapisałeś blok kontekstu.
- [ ] ChatGPT przestrzegał stałych instrukcji bez powtarzania.
- [ ] Rozumiesz, że GPT-y/Projekty = zapisane instrukcje (+ pliki), które pamięta.

---

## 🎯 Zadanie

Napisz **własny** 5-liniowy blok instrukcji opisujący, jak ma zachowywać się ChatGPT. To jedna z najbardziej opłacalnych rzeczy w kursie — dobre instrukcje poprawiają *każdą* przyszłą rozmowę.

---

## 💡 Najważniejsze wnioski

- **Instrukcje własne / GPT / Projekty** = stałe instrukcje (i pliki), o których ChatGPT nie zapomina.
- Brak dostępu? Wklej **blok kontekstu** na początku rozmów dla tego samego efektu.
- Jasne instrukcje poprawiają każdą odpowiedź bez dodatkowego wysiłku.

🌐 [English](../../en/lessons/07-custom-gpts-and-projects.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)
