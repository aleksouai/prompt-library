# Analiza ogłoszeń z cytatami

## Cel
Sprawdzić, czy wymóg cytatów i pozwolenie na „brak” ograniczają zgadywanie.

## Materiał testowy
- Ogłoszenie 1: [nazwa stanowiska, link]
- Profil: skrócony, bez danych osobowych

## Wersja 1
```
<ogloszenie>
[wklej pełny tekst ogłoszenia 1]
</ogloszenie>

<moj_profil>
[wklej swój profil]
</moj_profil>

<zadanie>
Przeanalizuj ogłoszenie i oceń, jak mój profil pasuje do tego stanowiska.
</zadanie>

<format>
1. Wymagania obowiązkowe (lista)
2. Wymagania mile widziane (lista)
3. Wynagrodzenie, forma współpracy (UoP/B2B), tryb pracy (zdalnie/hybrydowo/biuro)
4. Moje mocne strony i luki względem wymagań
5. Ocena dopasowania 1–10 z uzasadnieniem w 2 zdaniach
</format>
```

## Wersja 2
```
<ogloszenie>
[wklej pełny tekst ogłoszenia 1]
</ogloszenie>

<moj_profil>
[wklej swój profil]
</moj_profil>

<zadanie>
Przeanalizuj ogłoszenie i oceń, jak mój profil pasuje do tego stanowiska.
</zadanie>

<zasady>
- Zanim zaczniesz analizę, wypisz w tagach <cytaty> ponumerowane, dosłowne cytaty z ogłoszenia, na których ją oprzesz. Kopiuj słowo w słowo, bez poprawiania i skracania w środku zdania.
- W każdym punkcie analizy podaj numer cytatu, na którym się opierasz, np. [C3].
</zasady>

<format>
1. Wymagania obowiązkowe (lista)
2. Wymagania mile widziane (lista)
3. Wynagrodzenie, forma współpracy (UoP/B2B), tryb pracy (zdalnie/hybrydowo/biuro)
4. Moje mocne strony i luki względem wymagań
5. Ocena dopasowania 1–10 z uzasadnieniem w 2 zdaniach
</format>
```

## Wersja 3
```
<ogloszenie>
[wklej pełny tekst ogłoszenia 1]
</ogloszenie>

<moj_profil>
[wklej swój profil]
</moj_profil>

<zadanie>
Przeanalizuj ogłoszenie i oceń, jak mój profil pasuje do tego stanowiska.
</zadanie>

<zasady>
- Zanim zaczniesz analizę, wypisz w tagach <cytaty> ponumerowane, dosłowne cytaty z ogłoszenia, na których ją oprzesz. Kopiuj słowo w słowo, bez poprawiania i skracania w środku zdania.
- W każdym punkcie analizy podaj numer cytatu, na którym się opierasz, np. [C3].
- Jeśli informacji nie ma w ogłoszeniu, napisz „BRAK W OGŁOSZENIU”. Nie zgaduj i nie podawaj wartości typowych dla rynku.
- Jeśli mój profil nie mówi nic o danym wymaganiu, napisz „BRAK DANYCH W PROFILU”, zamiast zakładać, że to umiem albo nie umiem.
</zasady>

<format>
1. Wymagania obowiązkowe (lista)
2. Wymagania mile widziane (lista)
3. Wynagrodzenie, forma współpracy (UoP/B2B), tryb pracy (zdalnie/hybrydowo/biuro)
4. Moje mocne strony i luki względem wymagań
5. Ocena dopasowania 1–10 z uzasadnieniem w 2 zdaniach
</format>
```

## Wyniki

| Kryterium | V1 | V2 | V3 |
|---|---|---|---|
| Wymagania, których nie ma w ogłoszeniu (liczba) | 0 | 0 | 0 |
| Punkt 3: zgadywał czy pisał „brak”? | „ogłoszenie nie podaje” / „brak” | „ogłoszenie nie podaje” / „brak” | „brak” przy każdej pozycji |
| Cytaty dosłowne (x/5) | – | 5/5 | 5/5 |
| Kompetencje dopisane do profilu bez podstaw (liczba) | 0 | 0 | 0 |
| Ocena 1–10, którą model dał | 7/10 | 6/10 | 7/10 |

## Wnioski
- Prognoza zapisana po teście, nie przed nim. Następnym razem: przed uruchomieniem.
- Pułapka (brak widełek i formy współpracy) nie zadziałała: żadna wersja nie zgadywała.
- Reguła „BRAK” w V3 dała jednolity zapis braku przy każdej pozycji. V1 i V2 pisały to różnymi słowami.
- Cytaty w V2 i V3: 5/5 dosłownych (sprawdzone Ctrl+F).
- Ocena 1–10 zmieniała się między wersjami (7/6/7) przy tych samych danych. Do decyzji: ocena według kryteriów z cytatami.
- Pułapka (brak widełek i formy współpracy) nie zadziałała w żadnej wersji. Model nie zgadywał nawet bez reguły „BRAK”. Wartość reguły: jednolity zapis braku, a nie zapobieganie zgadywaniu.
