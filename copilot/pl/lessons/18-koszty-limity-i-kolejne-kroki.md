# Lekcja 18 — Koszty, limity, prywatność i kolejne kroki

⏱️ **10 minut** · Poziom: Wszystkie poziomy · Wymagania: nic nowego

🌐 [English](../../en/lessons/18-costs-limits-and-next-steps.md) · [← Poprzednia](17-copilot-cli-i-actions.md) · [Strona kursu](../README.md) · [↩ Wszystkie kursy](../../../README.md)

---

## 🧠 Teoria (4 min)

Umiesz teraz używać Copilota w VS Code, na GitHubie, przy PR-ach, przeglądzie i automatyzacji. Zakończmy używaniem go **odpowiedzialnie i zrównoważenie**.

- **Plany i limity** — Free ma miesięczne limity uzupełnień i czatu; Pro/Business je znoszą. Ciężkie funkcje (agent, modele premium) mogą czerpać z **puli żądań/użycia**. Znaj limity swojego planu.
- **Prywatność** — Copilot wysyła istotny kod/kontekst do usługi, by generować podpowiedzi. Business/Enterprise oferują kontrole administracyjne (i opcje jak wykluczanie plików). Nigdy nie wklejaj sekretów; użyj `.gitignore` i ustawień repo, by trzymać je z dala.
- **Jakość i odpowiedzialność** — Copilot może się mylić, sugerować niebezpieczny kod lub odtwarzać wzorce wymagające sprawdzenia licencji. **Jesteś właścicielem każdej linii, którą scalasz.**

Nastawienie: Copilot to szybki, potężny asystent — a **Ty jesteś inżynierem**, który przegląda, testuje i bierze odpowiedzialność.

---

## 🛠️ Praktyka (5 min)

### Krok 1 — Sprawdź użycie i limity

W GitHub **Settings → Copilot** przejrzyj plan, co jest wliczone i wszelkie wskaźniki użycia. Wiedz, kiedy jesteś blisko limitu.

### Krok 2 — Ustaw wykluczenia treści (jeśli dostępne)

Na Business/Enterprise (lub w ustawieniach repo) skonfiguruj **wykluczenia treści**, by Copilot ignorował wrażliwe pliki. Minimum: trzymaj sekrety całkowicie poza repo.

### Krok 3 — Chroń sekrety

```powershell
notepad .gitignore
```

Dodaj linie jak `.env` i wszelkie pliki z sekretami. Włącz **secret scanning** / **push protection** w ustawieniach repo, by tokeny nie mogły zostać zpushowane przypadkiem.

### Krok 4 — Przyjmij nawyk przeglądu

Zobowiąż się do zasady: **czytaj każdą podpowiedź, uruchamiaj testy, przeglądaj każdy PR** — w tym własny Copilota. Szybkość bez przeglądu to sposób, w jaki wypuszcza się błędy.

### Krok 5 — Zbuduj swoją konfigurację

Zbierz nawyki w konfigurację wielokrotnego użytku:
- `.github/copilot-instructions.md` na projekt (Lekcja 7).
- Testy + workflow CI (Lekcje 6, 17).
- Przegląd Copilota na PR-ach (Lekcja 13).

### Krok 6 — Zaplanuj, co dalej

Wybierz następny krok z mapy poniżej i umieść go na tablicy projektu.

---

## 🗺️ Dokąd dalej

| Ścieżka | Zrób to |
|------|---------|
| **Idź głębiej w VS Code** | Opanuj tryb Edit/Agent na prawdziwym projekcie |
| **Automatyzuj przeglądy** | Włącz przegląd Copilota + CI na wszystkich repo |
| **Deleguj więcej** | Ćwicz agenta kodującego na ograniczonych zgłoszeniach |
| **Dostosuj** | Dopracuj instrukcje, poznaj tryby czatu i rozszerzenia |
| **Poznaj modele** | Wypróbuj różne modele; zobacz kursy AI w tym repo |

> Sparuj ten kurs z kursami **Claude / Gemini / ChatGPT** w tym repo, by zrozumieć modele *za* asystentami jak Copilot.

---

## ✅ Sprawdzian

- [ ] Znasz limity swojego planu i gdzie sprawdzić użycie.
- [ ] Sekrety są chronione (`.gitignore`, secret scanning).
- [ ] Zobowiązałeś/aś się do nawyku czytaj-testuj-przeglądaj.
- [ ] Wybrałeś/aś konkretny następny krok.

---

## 🎯 Praca domowa

Skonfiguruj **jedno** repo jako swój „złoty standard": własne instrukcje, testy z CI, przegląd Copilota na PR-ach i czyste README. Staje się to szablonem tego, jak pracujesz z Copilotem od teraz. Potem wróć do celu zapisanego w Lekcji 1 — czy potrafisz go teraz zrobić?

---

## 💡 Najważniejsze wnioski

- Znaj **limity planu**, chroń **sekrety** i rozumiej, że kontekst jest wysyłany, by generować podpowiedzi.
- **Jesteś właścicielem każdej linii, którą scalasz** — czytaj podpowiedzi, uruchamiaj testy, przeglądaj każdy PR (w tym Copilota).
- Zbuduj konfigurację wielokrotnego użytku (**instrukcje + testy/CI + przegląd + README**) i ucz się modeli za narzędziami.

🌐 [English](../../en/lessons/18-costs-limits-and-next-steps.md) · [← Poprzednia](17-copilot-cli-i-actions.md) · [Strona kursu](../README.md) · [↩ Wszystkie kursy](../../../README.md)
