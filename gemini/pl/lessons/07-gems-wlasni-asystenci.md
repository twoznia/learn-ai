# Lekcja 07 — Gems: Twoi własni asystenci AI

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: gemini.google.com

🌐 [English](../../en/lessons/07-gems-custom-assistants.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)

---

## 🧠 Teoria (3 min)

Dotąd każda nowa rozmowa zaczynała się od zera. **Gems** to zmieniają.

**Gem** to własna wersja Gemini ze **stałymi instrukcjami**, które piszesz raz — rola, ton i zasady. Otwierasz Gem, a on już zachowuje się tak, jak ustawiłeś, więc przestajesz się powtarzać. Wyobraź sobie danie Gemini **opisu stanowiska**, o którym nigdy nie zapomni.

Popularne Gemy:
- **Asystent pisania** w Twoim głosie.
- **Pomocnik kodowania**, który zawsze wyjaśnia dla początkujących.
- **Pomocnik do nauki** przedmiotu, którego się uczysz.

> Gemy są dostępne w aplikacji Gemini. Jeśli ich nie widzisz na koncie, uzyskasz większość korzyści, zapisując **blok kontekstu** wklejany na początku rozmów (poniżej). Koncepcja jest ta sama.

---

## 🛠️ Praktyka (6 min)

### Ścieżka A — Jeśli masz Gemy

1. W gemini.google.com znajdź **Gems** w lewym panelu (lub opcję **menedżera Gemów** / „New Gem”).
2. Kliknij **New Gem**.
3. Nadaj nazwę, np. **„Mój Asystent”**, i wklej instrukcje:

```text
Jesteś moim osobistym asystentem pracy.
- Odbiorca: ja, zajęty nietechniczny profesjonalista.
- Ton: ciepły, jasny, zwięzły. Bez żargonu, chyba że go zdefiniujesz.
- Zawsze kończ dłuższe odpowiedzi krótką linią „Następny krok:”.
- Jeśli prośba jest niejednoznaczna, zadaj jedno pytanie doprecyzowujące przed odpowiedzią.
- Jeśli nie jesteś pewny faktu, powiedz to, zamiast zgadywać.
```

4. Zapisz. Rozpocznij rozmowę *z tym Gemem* i zauważ, że już zna zasady — bez powtarzania.

### Ścieżka B — Odpowiednik darmowy (dla każdego)

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

Następnie wpisz swoją właściwą prośbę poniżej.

### Przetestuj

Wypróbuj tę samą niejasną prośbę z Gemem/kontekstem i bez:
```text
pomóż mi z newsletterem
```
Z instrukcjami Gemini powinien zadać trafne pytanie i dopasować ton. Bez nich zgaduje.

---

## 🧩 Dobre składniki instrukcji

Ukradnij te linie:

| Cel | Linia do dodania |
|------|-------------|
| Spójny ton | „Pisz w przyjaznym, profesjonalnym tonie.” |
| Krótsze odpowiedzi | „Domyślnie zwięźle; rozwijaj tylko, gdy poproszę.” |
| Mniej błędnych faktów | „Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.” |
| Nastawienie na działanie | „Zakończ jasnym następnym krokiem.” |
| Twoja dziedzina | „Pracuję w <branża>; zakładaj ten kontekst.” |

---

## ✅ Sprawdzenie

- [ ] Utworzyłeś Gem **lub** zapisałeś blok kontekstu.
- [ ] Gemini przestrzegał stałych instrukcji bez powtarzania.
- [ ] Rozumiesz, że Gem = zapisana osobowość + zasady.

---

## 🎯 Zadanie

Napisz **własny** 5-liniowy blok instrukcji opisujący, jak ma zachowywać się Gemini. To jedna z najbardziej opłacalnych rzeczy w kursie — dobre instrukcje poprawiają *każdą* przyszłą rozmowę.

---

## 💡 Najważniejsze wnioski

- **Gems** = własni asystenci Gemini ze stałymi instrukcjami, o których nie zapomina.
- Brak Gemów? Wklej **blok kontekstu** na początku rozmów dla tego samego efektu.
- Jasne instrukcje poprawiają każdą odpowiedź bez dodatkowego wysiłku.

🌐 [English](../../en/lessons/07-gems-custom-assistants.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)
