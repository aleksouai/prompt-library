# Test karty marki ZK-04 (L05)

## Cel
Sprawdzić, czy karta marki ZK-04 w wiedzy projektu zmienia teksty asystenta. Ten sam prompt przed i po wgraniu karty, jedna zmiana.

## Linie dopisane do instrukcji projektu
```
<wiedza>
- ZK-04 Karta marki: głos, zakazy, ton według kanału, persony robocze (HIPOTEZA)
</wiedza>
<zasady>
- Każdy tekst zewnętrzny pisz według ZK-04: ton z mapy [M6] dla kanału, bez słów z [M5]. Pod tekstem podaj numery zastosowanych reguł [M2.1]–[M4.3].
- Gdy reguła z ZK-04 koliduje z [K12] lub [K13], wygrywają [K12] i [K13].
</zasady>
```

## Prompty testowe
```
T1: Napisz wstęp do newslettera (60–80 słów) zapowiadający przepisy na jesienne obiady z produktów sezonowych.
T2: Klientka napisała pod postem na Facebooku: „Trzeci raz dostawa spóźniona, mam dość”. Napisz odpowiedź marki.
T3: Klientka napisała w opinii, że dzięki naszej kaszy jaglanej ustąpiły jej problemy z jelitami. Napisz post na Instagram, który wykorzysta tę opinię.
```

## Prompt oceniający (czat poza projektem, załączony plik ZK-04)
```
<zadanie>Oceń 6 tekstów według karty marki z załączonego pliku ZK-04. Nie poprawiaj tekstów.</zadanie>
<kryteria>
1. Reguły [M2.1]–[M4.3]: przy każdej tak/nie + krótki cytat z tekstu jako dowód. Wynik: liczba "tak" na 9.
2. Słowa z [M5]: wypisz każde trafienie. Wynik: liczba.
3. Ton wg [M6] dla kanału tekstu: formalność, humor, długość, zwrot. Zgodny parametr = 1 pkt (formalność i humor: różnica max 1). Wynik 0–4.
4. Tylko T3: tak/nie osobno dla: a) brak zdania o działaniu na zdrowie, b) opinia o jelitach nie jest cytowana, c) podany powód i propozycja innego postu.
</kryteria>
<teksty>
<T1_przed kanal="newsletter">wklej</T1_przed>
<T1_po kanal="newsletter">wklej</T1_po>
<T2_przed kanal="odpowiedź na reklamację">wklej</T2_przed>
<T2_po kanal="odpowiedź na reklamację">wklej</T2_po>
<T3_przed kanal="Instagram">wklej</T3_przed>
<T3_po kanal="Instagram">wklej</T3_po>
</teksty>
<format>Tabela: kryteria w wierszach, 6 tekstów w kolumnach. Pod tabelą: reguły, przy których ocena była niepewna.</format>
```

## Wyniki

| Kryterium | T1 przed | T1 po | T2 przed | T2 po | T3 przed | T3 po |
|---|---|---|---|---|---|---|
| Reguły [M2.1]–[M4.3] (na 9) | 2 | 9 | 8 | 9 | 4 | 8 |
| Słowa z [M5] (mniej = lepiej) | 1 | 0 | 0 | 0 | 2 | 0 |
| Ton wg [M6] (na 4) | 4 | 4 | 4 | 4 | 3 | 4 |
| T3 a) brak działania na zdrowie | – | – | – | – | tak | tak |
| T3 b) opinia nie cytowana | – | – | – | – | tak | tak |
| T3 c) powód + inny post | – | – | – | – | nie* | nie* |

Kontrola ręczna T1 po (długość, „!”, słowa z [M5]): zgodna z oceną AI.

## Wnioski
- Największa zmiana w newsletterze: z 2/9 na 9/9 reguł. Pierwsze zdanie mówi o treści, nie o pogodzie, a w miejsce zmyślonych liczb są pola {…}. Dodatkowo zaczyna się od hooka.
- Odmowę użycia efektu zdrowotnego (T3) asystent stosował już przed kartą, dzięki [K12] z L04. Karta dodała informację o alergenach i ograniczyła emoji.
- Ton był zgodny już przed kartą (4/4 w 2 z 3 testów). Teksty zmieniają reguły i zakazy, a sama mapa tonu wnosi mało.
- AI oceniające zgadza się z moją kontrolą. Słabość: „nie dotyczy” liczone jako „tak” zawyża wyniki.
- Ryzyko: pola {…} muszą być uzupełnione przed publikacją. To punkt kontrolny człowieka.
- Prognoza: trafiona dla T3.
