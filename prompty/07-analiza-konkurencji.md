# 07 – Analiza konkurencji ze źródłami (L06)

## Prompt V2
```
<zadanie>
Przygotuj tabelę konkurencji Zielonego Koszyka na podstawie plików projektu.
Konkurenci: BioMarket24, Szybko&Zdrowo, dyskont Oszczędny (linia BioDobre).
</zadanie>

<zasady>
- W każdej komórce: wartość + [numer punktu, data źródła].
- Każdą komórkę oznacz jednym statusem:
  FAKT – dane ze źródła, aktualne;
  DEKLARACJA – twierdzenie konkurenta o sobie albo jego plan, bez dowodu;
  SPRZECZNE – źródła podają różne wartości: pokaż obie z datami i wskaż nowszą;
  NIEAKTUALNE – źródło starsze niż 12 miesięcy;
  BRAK – nie ma w plikach.
  Powód: zarząd zapyta „skąd ta liczba i ile ma lat?”.
- Przy ocenach klientów podaj liczbę opinii. Powód: 12 opinii i 1 240 ocen to dowody o różnej sile.
- Przy porównaniu cen podaj ograniczenia porównania, jeśli są w źródle.
- Wniosek o konkurencie wyprowadzony z ogólnych danych o rynku oznacz [ZAŁOŻENIE].
</zasady>

<format>
Tabela: wiersz = konkurent. Kolumny:
Oferta (liczba produktów) | Dostawa (czas, próg darmowej dostawy) | Cena vs Zielony Koszyk | Grupa docelowa | Hasło komunikacji | Mocne strony wg klientów | Słabe strony wg klientów | Udział w rynku
Pod tabelą: lista SPRZECZNE i NIEAKTUALNE z wyjaśnieniem w 1 zdaniu.
</format>
```

## Wyniki testu (klucz 8 pułapek w ZK-05)
| Wersja | Wynik | Co przegapiła |
|---|---|---|
| V1 bez reguł dowodowych | 5/8 | „Najtańsza” bez komentarza; sprzeczności bez dat i bez wskazania nowszej wartości; oceny bez liczby opinii; hasło reklamowe jako źródło grupy docelowej |
| V2 z regułami | 8/8 | Nie użyła statusu NIEAKTUALNE (cennik z 03.2024); nie oznaczyła oświadczenia zdrowotnego konkurenta |

## Pierwszy test był nieważny
ZK-05 nie było w wiedzy projektu. Model użył tylko ZK-01 i podał nieaktualne dane jako FAKT. Status FAKT jest tak dobry, jak zestaw plików.

## Prognoza a wynik
- Prognoza: niemożliwość przewidzenia prognozy ze względu na źle ustawioną lekcję.
- Wynik: V1 5/8, V2 8/8

## Do V3
- Gdy pasują dwa statusy, podaj oba (np. SPRZECZNE + NIEAKTUALNE).
- Oznacz oświadczenia zdrowotne konkurentów jako ryzyko prawne.

## Wnioski
1. …
2. …
