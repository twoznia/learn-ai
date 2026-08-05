# Lekcja 07 — Projekty i instrukcje własne

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: konto Claude (sieć lub desktop)

🌐 [English](../../en/lessons/07-projects-and-memory.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)

---

## 🧠 Teoria (3 min)

Dotąd każda nowa rozmowa zaczynała się od zera. **Projekty** to zmieniają.

**Projekt** to przestrzeń robocza, w której przechowujesz:

- **Instrukcje własne** — stałe polecenia, których Claude przestrzega w każdej rozmowie tam (Twoja rola, ton, zasady).
- **Pliki wiedzy** — dokumenty, do których Claude może się odwoływać we wszystkich rozmowach projektu (przewodnik stylu, lista produktów, Twoje CV).

Wyobraź sobie Projekt jako danie Claude **opisu stanowiska + szafki na dokumenty**, o których nigdy nie zapomni — dzięki czemu przestajesz się powtarzać.

> Projekty są dostępne w planach płatnych. Na wersji darmowej możesz uzyskać większość korzyści, zapisując **blok kontekstu**, który wklejasz na początku rozmów (pokazany niżej). Tak czy inaczej, koncepcja jest ta sama.

---

## 🛠️ Praktyka (6 min)

### Ścieżka A — Jeśli masz Projekty

1. W claude.ai lub Claude Desktop znajdź **Projects** w lewym panelu → **+ Create Project**.
2. Nazwij np. **„Mój Asystent”**.
3. Otwórz **Instructions** (czasem „Set custom instructions”) i wklej:

```text
Jesteś moim osobistym asystentem pracy.
- Odbiorca: ja, zajęty nietechniczny profesjonalista.
- Ton: ciepły, jasny, zwięzły. Bez żargonu, chyba że go zdefiniujesz.
- Zawsze kończ dłuższe odpowiedzi krótką linią „Następny krok:”.
- Jeśli prośba jest niejednoznaczna, zadaj jedno pytanie doprecyzowujące przed odpowiedzią.
- Jeśli nie jesteś pewny faktu, powiedz to, zamiast zgadywać.
```

4. Dodaj plik wiedzy, jeśli masz (np. PDF o Twojej pracy, przewodnik stylu). Kliknij **Add content / files**.
5. Rozpocznij rozmowę *wewnątrz* projektu i zauważ, że już „zna” zasady — bez powtarzania.

### Ścieżka B — Odpowiednik dla wersji darmowej (dla każdego)

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

Wypróbuj tę samą niejasną prośbę z instrukcjami i bez:
```text
pomóż mi z newsletterem
```
Z instrukcjami na miejscu Claude powinien zadać trafne pytanie doprecyzowujące i dopasować ton. Bez nich zgaduje.

---

## 🧩 Dobre składniki instrukcji własnych

Ukradnij te linie do swoich instrukcji:

| Cel | Linia do dodania |
|------|-------------|
| Spójny ton | „Pisz w przyjaznym, profesjonalnym tonie.” |
| Krótsze odpowiedzi | „Domyślnie zwięźle; rozwijaj tylko, gdy poproszę.” |
| Mniej błędnych faktów | „Jeśli nie jesteś pewny, powiedz to, zamiast zgadywać.” |
| Nastawienie na działanie | „Zakończ jasnym następnym krokiem.” |
| Twoja dziedzina | „Pracuję w <branża>; zakładaj ten kontekst.” |

---

## ✅ Sprawdzenie

- [ ] Utworzyłeś Projekt **lub** zapisałeś blok kontekstu do wielokrotnego użytku.
- [ ] Claude przestrzegał stałych instrukcji bez powtarzania.
- [ ] Rozumiesz, że pliki wiedzy = dokumenty, które Claude pamięta w rozmowach.

---

## 🎯 Zadanie

Napisz **własny** 5-liniowy blok instrukcji opisujący, jak ma zachowywać się Claude. To jedna z najbardziej opłacalnych rzeczy w całym kursie — dobry blok instrukcji poprawia *każdą* przyszłą rozmowę.

---

## 💡 Najważniejsze wnioski

- **Projekty** = stałe instrukcje + pliki referencyjne, o których Claude nie zapomina.
- Brak Projektów? Wklej **blok kontekstu** na początku rozmów, aby uzyskać ten sam efekt.
- Jasne stałe instrukcje poprawiają każdą odpowiedź bez dodatkowego wysiłku.

🌐 [English](../../en/lessons/07-projects-and-memory.md) · [← Wstecz](06-codzienne-zadania.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Pythona →](08-instalacja-python.md)
