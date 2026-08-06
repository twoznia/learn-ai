# Lekcja 15 — Wyszukiwanie w sieci

⏱️ **10 minut** · Poziom: Początkujący → Średni · Potrzebne: ChatGPT (aplikacja lub sieć)

🌐 [English](../../en/lessons/15-web-search.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)

---

## 🧠 Teoria (4 min)

LLM „zna” tylko to, czego nauczył się podczas treningu, więc może być nieaktualny lub coś zmyślić. **Wyszukiwanie w sieci** to naprawia: ChatGPT może **szukać w internecie podczas odpowiadania**, potem opiera odpowiedź na tym, co znalazł, i pokazuje źródła.

Dlaczego to ważne dla początkujących:
- Pytaj o **niedawne wydarzenia, ceny, wersje** — rzeczy, których dane treningowe nie znają.
- Otrzymuj odpowiedzi **z linkami**, które możesz zweryfikować.
- Ograniczaj halucynacje przy pytaniach faktycznych.

> ⚠️ Wyszukiwanie to nie magia — źródła też bywają błędne. Czytaj cytowane linki przy wszystkim, co ważne.

---

## 🛠️ Praktyka (5 min)

### Krok 1 — Zadaj pytanie o „świeże info”

Otwórz ChatGPT i zapytaj o coś wymagającego aktualnych informacji:

```text
Jakie są 3 niedawne, warte uwagi wydarzenia w świecie samochodów elektrycznych w tym miesiącu? Podaj źródła z linkami.
```

ChatGPT zwykle wyszuka w sieci i odpowie z **cytowaniami**. Kliknij źródło, aby zweryfikować.

### Krok 2 — Włącz wyszukiwanie wprost (jeśli trzeba)

Jeśli odpowiada z pamięci zamiast szukać, poszukaj przełącznika **Search / web** lub narzędzia obok pola wiadomości (ikona globusa), włącz go i zapytaj ponownie. Albo po prostu powiedz:

```text
Wyszukaj w sieci i podaj źródła do tego: <Twoje pytanie>
```

### Krok 3 — Porównaj z „bez wyszukiwania”

Zadaj pytanie zależne od czasu **bez** wyszukiwania, potem **z** wyszukiwaniem:

```text
Kto obecnie posiada <jakiś rekord/stanowisko, które niedawno się zmieniło>?
```

Zauważ różnicę: wyszukana odpowiedź jest świeższa i ma linki. Ten kontrast to cały sens.

### Krok 4 — Streść żywą stronę

Wklej link i zapytaj:

```text
Przeczytaj tę stronę i streść ją w 5 punktach, potem wypisz, co powinienem podwójnie sprawdzić:
<wklej URL>
```

---

## 🧭 Kiedy używać wyszukiwania

| Używaj wyszukiwania do… | Pomiń przy… |
|--------------------|--------------|
| Niedawnych wiadomości, cen, premier | Ponadczasowych wyjaśnień („czym jest ułamek”) |
| Pytań „na dziś…” | Twórczego pisania / burzy mózgów |
| Faktów, na których podstawie działasz | Przeredagowywania własnego tekstu |

> 💡 **Dla programistów:** API OpenAI oferuje też wbudowane narzędzia (jak wyszukiwanie w sieci), które włączasz w kodzie. To zaawansowany kolejny krok — aplikacja to najłatwiejsze miejsce na start.

---

## ✅ Sprawdzenie

- [ ] Zadałeś pytanie o „świeże info” i dostałeś źródła.
- [ ] Znalazłeś lub włączyłeś opcję sieci/wyszukiwania.
- [ ] Porównałeś odpowiedź z wyszukiwaniem i bez.

---

## 🎯 Zadanie

Wybierz pytanie, którego odpowiedź niedawno się zmieniła (najnowsza wersja produktu, aktualna cena). Zapytaj ChatGPT z wyszukiwaniem, potem kliknij źródło, aby potwierdzić. Ten krok weryfikacji odróżnia mądrych użytkowników AI od reszty.

---

## 💡 Najważniejsze wnioski

- **Wyszukiwanie w sieci** łączy odpowiedzi ChatGPT z żywymi źródłami z cytowaniami.
- Włącz przełącznik sieci/wyszukiwania albo poproś „wyszukaj w sieci i podaj źródła”.
- Używaj do świeżych/faktycznych pytań; nadal klikaj źródła przy wszystkim, co ważne.

🌐 [English](../../en/lessons/15-web-search.md) · [← Wstecz](14-mini-projekt.md) · [Strona kursu](../README.md) · [Dalej: Prompt engineering →](16-prompt-engineering.md)
