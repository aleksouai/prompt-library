  # Rekomendacja dla zarządu: chatbot AI w obsłudze klienta

  ## Cel
  Porównanie promptu „na szybko” z promptem ustrukturyzowanym.

  ## Wersja 1
  ```
Napisz rekomendację dla zarządu, czy wdrożyć chatbota AI w obsłudze klienta.
```

  ## Wersja 2
  ```
<rola> 
Jesteś doświadczonym konsultantem ds. transformacji cyfrowej, który przygotowuje materiały dla zarządów firm e-commerce. 
</rola> <kontekst> 
Firma: „Zielony Koszyk”, sklep internetowy ze zdrową żywnością, Polska. - 40 000 zamówień miesięcznie - Dział obsługi klienta: 8 osób - 35% zgłoszeń to pytania o status zamówienia, 20% o zwroty - Średni czas pierwszej odpowiedzi: 9 godzin - Zarząd obawia się utraty jakości obsługi i ryzyk prawnych (RODO) </kontekst> <zadanie> 
Przygotuj rekomendację: czy wdrożyć chatbota AI w obsłudze klienta. 
</zadanie> <zasady> 
- Używaj wyłącznie danych z kontekstu. Jeśli potrzebujesz założenia (np. kosztu), oznacz je jako [ZAŁOŻENIE] i podaj uzasadnienie. - Uwzględnij ryzyka i sposób ich ograniczenia. - Język: konkretny, bez marketingowych sformułowań. 
</zasady> <format> 
1. Rekomendacja w jednym zdaniu (tak/nie/warunkowo) 
2. Uzasadnienie: 3 punkty 
3. Zakres pilotażu: co, na jakich zgłoszeniach, ile trwa 
4. KPI pilotażu: 3–4 wskaźniki z wartością docelową 
5. Ryzyka: tabela (ryzyko | wpływ | jak ograniczyć) Maksymalnie 1 strona A4. </format>
```
 ## Wersja 3
```
<rola>
Jesteś doświadczonym konsultantem ds. transformacji cyfrowej. Przygotowujesz materiały decyzyjne dla zarządów firm e-commerce. Odbiorcy nie są technikami, ale znają biznes i finanse.
</rola>

<kontekst>
Firma: „Zielony Koszyk”, sklep internetowy ze zdrową żywnością, Polska.
- 40 000 zamówień miesięcznie
- Zgłoszenia do obsługi: [UZUPEŁNIJ] miesięcznie; kanały: [e-mail / czat / telefon]
- Dział obsługi klienta: 8 osób; koszt pełnego etatu: [UZUPEŁNIJ] zł/mies.
- 35% zgłoszeń to pytania o status zamówienia, 20% o zwroty
- Średni czas pierwszej odpowiedzi: 9 godzin; obecny CSAT: [UZUPEŁNIJ]
- System zamówień: [UZUPEŁNIJ, np. Shopify / własny]
- Budżet na pilotaż: do [UZUPEŁNIJ] zł; decyzja zarządu do [data]
- Cel zarządu: skrócić czas odpowiedzi bez zatrudniania nowych osób przy wzroście sprzedaży
- Obawy zarządu: utrata jakości obsługi, ryzyka prawne (RODO)
</kontekst>

<zadanie>
Przygotuj rekomendację, czy wdrożyć chatbota AI w obsłudze klienta.
Porównaj go z co najmniej jedną tańszą alternatywą (np. proaktywne powiadomienia o statusie, samoobsługowy formularz zwrotów). Wybierz rozwiązanie, które najlepiej realizuje cel zarządu.
Rekomenduj „nie”, jeśli alternatywa daje podobny efekt przy niższym koszcie lub ryzyku.
</zadanie>

<zasady>
- Fakty o firmie bierz wyłącznie z kontekstu. Jeśli brakuje liczby potrzebnej do wniosku, przyjmij założenie, oznacz je [ZAŁOŻENIE] i podaj w jednym zdaniu jego źródło lub logikę.
- Wiedzę ogólną (prawo, praktyka rynkowa, typowe koszty) możesz stosować, ale wskaż przepis lub źródło, jeśli to możliwe.
- Uwzględnij ryzyka prawne (RODO, AI Act, prawo konsumenckie, w tym wyłączenia prawa odstąpienia dla żywności) i operacyjne.
- Język konkretny, liczby zamiast przymiotników, bez sformułowań marketingowych.
</zasady>

<format>
1. Rekomendacja w jednym zdaniu (tak / nie / warunkowo + warunek)
2. Uzasadnienie: 3 punkty, każdy z liczbą z kontekstu lub założeniem
3. Porównanie z alternatywą: 2–3 zdania
4. Zakres pilotażu: co, na jakich zgłoszeniach, ile trwa, ile kosztuje
5. KPI: tabela (wskaźnik | wartość bazowa | cel | sposób pomiaru), 3–4 wiersze
6. Ryzyka: tabela (ryzyko | wpływ: niski/średni/wysoki | jak ograniczyć), 4–6 wierszy
7. Lista założeń do weryfikacji
Długość: maksymalnie 450 słów, bez wstępu i podsumowania.
</format>
```
  ## Wyniki porównania v1 vs v2
| Kryterium | Wersja 1 | Wersja 2 |
|---|---|---|
| Konkretność (czy dotyczy tej firmy) | 1 | 3 |
| Przydatność dla zarządu | 1 | 3 |
| Brak zmyślonych danych (5 = żadnych) | 1 | 3 |
| Gotowość do użycia bez poprawek | 2 | 3 |

  ## Wnioski
  - Domyślnie warunkuje projekt na "tak"
  - Zadanie prawidłowo zrozumiane i użyte liczby są właściwe.
  - Założenie oznaczone, ale brak wyjaśnienia z czego wynika założona kwota.
  - Brakuje nadal konkretów - ale zadanie zostało wykonane zgodnie z opisem w prompcie.
  - Jasne warunki bez przestrzeni do interpretacji oraz jasne oczekiwania.

 ## Wyniki porównania v2 vs v3
| Kryterium | Wersja 1 | Wersja 2 | Wersja 3
|---|---|---|---|
| Konkretność (czy dotyczy tej firmy) | 1 | 3 | 5 |
| Przydatność dla zarządu | 1 | 3 | 5 |
| Brak zmyślonych danych (5 = żadnych) | 1 | 3 | 5 |
| Gotowość do użycia bez poprawek | 2 | 3 | 5 |

  ## Wnioski v3
  - rekomendacja nie była już domyślna, tylko oparta na rzetelnej analizie projektu - dokładniejsze zdefiniowanie warunków oraz oczekiwań dało precyzyjniejsze i bardziej biznesowe wnioski
  - brak domyślnej interpretacji
  - Element	Wynik sprawdzenia
6 000 × 35% = 2 100, × 20% = 1 200, razem 3 300	✅ poprawne
72 000 ÷ 6 000 = 12 zł za zgłoszenie	✅ poprawne, założenie oznaczone
Koszt pilotażu 32 600 zł ≈ 33 000	✅ poprawne
Przepisy (art. 38 UPK, art. 28 i 44 RODO, art. 50 AI Act)	✅ trafne dla tego case’u
„Uwalnia 2 etaty, czyli 18 000 zł/mies.”	⚠️ Mylące. Cel zarządu to „bez nowych zatrudnień”, nie zwolnienia. To odzyskana pojemność zespołu, nie oszczędność w gotówce. Zarząd zapyta: „to zwalniamy 2 osoby?”
Alternatywa „tańsza”	⚠️ Różnica jest mniejsza, niż sugeruje tekst: ok. 4 200 zł/mies. (SMS + aplikacje) wobec ok. 6 000 zł. Głównym argumentem jest niższe ryzyko, nie koszt.
Rekomendacja „w jednym zdaniu”	⚠️ Ma dwa zdania. Drobne, ale to złamanie formatu.
Ostatnie założenie (przyczyną 9 h jest wolumen)	⚠️ Najważniejsze w całym dokumencie. Jeśli 9 h wynika z godzin pracy zespołu (np. brak dyżurów wieczorem i w weekend), cała rekomendacja upada. Należy je sprawdzić przed pilotażem, nie po nim.
