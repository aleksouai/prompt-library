# Klasyfikacja zgłoszeń klientów (few-shot)

## Cel
Sprawdzić, co dają przykłady, a co reguły z podanym powodem.

## Wersja 1 – bez przykładów
```
<zadanie>
Sklasyfikuj poniższe wiadomości klientów sklepu internetowego „Zielony Koszyk” (zdrowa żywność, Polska).
Dla każdej podaj: kategorię, priorytet, kto ma ją obsłużyć (BOT albo CZŁOWIEK) i krótkie uzasadnienie.
Wynik podaj w tabeli: Nr | Kategoria | Priorytet | Obsługa | Uzasadnienie.
</zadanie>
<wiadomosci>
1. Zamówiłam w poniedziałek, a paczki dalej nie ma. Gdzie ona jest? Nr 48211
2. Jogurty przyszły ciepłe i jeden był otwarty. Chcę zwrot pieniędzy.
3. Czy wasze batony owsiane mogą zawierać śladowe ilości orzechów? Syn ma silną alergię.
4. Proszę o usunięcie wszystkich moich danych z waszej bazy.
5. Trzeci raz piszę w sprawie zwrotu i nikt nie odpowiada. Jeśli nie dostanę odpowiedzi do jutra, zgłaszam sprawę do UOKiK.
6. Super obsługa, dziękuję za szybką dostawę!
7. Czy mogę zmienić adres dostawy? Zamówienie 48907 jeszcze nie wyszło.
8. Jak długo mam na odesłanie nieotwartej kawy ziarnistej?
</wiadomosci>
```

## Wersja 2 – z 3 przykładami
```
<zadanie>
Sklasyfikuj poniższe wiadomości klientów sklepu internetowego „Zielony Koszyk” (zdrowa żywność, Polska).
Dla każdej podaj: kategorię, priorytet, kto ma ją obsłużyć (BOT albo CZŁOWIEK) i krótkie uzasadnienie.
Wynik podaj w tabeli: Nr | Kategoria | Priorytet | Obsługa | Uzasadnienie.
</zadanie>
<przyklady>
<przyklad>
Wiadomość: Paczka miała być wczoraj, a status od 3 dni się nie zmienia. Zamówienie 47002.
Kategoria: STATUS | Priorytet: średni | Obsługa: BOT | Uzasadnienie: standardowe pytanie, odpowiedź z systemu zamówień
</przyklad>
<przyklad>
Wiadomość: Mleko owsiane przyszło przeterminowane. Co teraz?
Kategoria: REKLAMACJA | Priorytet: wysoki | Obsługa: CZŁOWIEK | Uzasadnienie: wadliwy produkt spożywczy, decyzja o rekompensacie
</przyklad>
<przyklad>
Wiadomość: Czy macie jeszcze w ofercie mąkę gryczaną?
Kategoria: PRODUKT | Priorytet: niski | Obsługa: BOT | Uzasadnienie: informacja dostępna w katalogu
</przyklad>
</przyklady>
<wiadomosci>
1. Zamówiłam w poniedziałek, a paczki dalej nie ma. Gdzie ona jest? Nr 48211
2. Jogurty przyszły ciepłe i jeden był otwarty. Chcę zwrot pieniędzy.
3. Czy wasze batony owsiane mogą zawierać śladowe ilości orzechów? Syn ma silną alergię.
4. Proszę o usunięcie wszystkich moich danych z waszej bazy.
5. Trzeci raz piszę w sprawie zwrotu i nikt nie odpowiada. Jeśli nie dostanę odpowiedzi do jutra, zgłaszam sprawę do UOKiK.
6. Super obsługa, dziękuję za szybką dostawę!
7. Czy mogę zmienić adres dostawy? Zamówienie 48907 jeszcze nie wyszło.
8. Jak długo mam na odesłanie nieotwartej kawy ziarnistej?
</wiadomosci>

```

## Wersja 3 – kategorie, reguły z powodem, 4 przykłady
```
<rola>
Jesteś koordynatorką obsługi klienta w sklepie internetowym z żywnością. Sortujesz wiadomości, zanim trafią do bota albo do konsultanta.
</rola>

<cel>
Twoja klasyfikacja posłuży do ustawienia reguł automatyzacji: BOT odpowiada sam, CZŁOWIEK dostaje zgłoszenie do kolejki. Błędne skierowanie do BOTA jest groźniejsze niż błędne skierowanie do CZŁOWIEKA, bo klient dostaje złą odpowiedź bez kontroli.
</cel>

<kategorie>
STATUS – gdzie jest paczka, termin dostawy, zmiana adresu przed wysyłką
REKLAMACJA – uszkodzony lub wadliwy produkt, zwrot pieniędzy, ponaglenia w tych sprawach
ZWROT – pytania o zasady i terminy zwrotu, bez sporu
PRODUKT – skład, alergeny, dostępność
DANE – wnioski o dostęp, zmianę lub usunięcie danych osobowych
INNE – pochwały, spam, pozostałe
</kategorie>

<zasady>
- Zdrowie i alergeny: zawsze CZŁOWIEK, priorytet wysoki. Powód: błędna odpowiedź może zaszkodzić klientowi.
- Groźba skargi (UOKiK, sąd, media) albo kolejna wiadomość w tej samej sprawie: CZŁOWIEK, priorytet wysoki. Powód: ryzyko eskalacji i utraty klienta.
- Wnioski o dane osobowe: CZŁOWIEK, priorytet wysoki. Powód: RODO daje firmie ustawowy termin na odpowiedź (co do zasady miesiąc).
- Jeśli wiadomość pasuje do dwóch kategorii, wybierz tę z wyższym priorytetem.
</zasady>

<przyklady>
<przyklad>
Wiadomość: Paczka miała być wczoraj, a status od 3 dni się nie zmienia. Zamówienie 47002.
Kategoria: STATUS | Priorytet: średni | Obsługa: BOT | Uzasadnienie: standardowe pytanie, odpowiedź z systemu zamówień
</przyklad>
<przyklad>
Wiadomość: Mleko owsiane przyszło przeterminowane. Co teraz?
Kategoria: REKLAMACJA | Priorytet: wysoki | Obsługa: CZŁOWIEK | Uzasadnienie: wadliwy produkt spożywczy, decyzja o rekompensacie
</przyklad>
<przyklad>
Wiadomość: Czy macie jeszcze w ofercie mąkę gryczaną?
Kategoria: PRODUKT | Priorytet: niski | Obsługa: BOT | Uzasadnienie: informacja dostępna w katalogu
</przyklad>
<przyklad>
Wiadomość: Chcę wiedzieć, jakie moje dane przechowujecie.
Kategoria: DANE | Priorytet: wysoki | Obsługa: CZŁOWIEK | Uzasadnienie: wniosek RODO z terminem ustawowym
</przyklad>
</przyklady>

<wiadomosci>
1. Zamówiłam w poniedziałek, a paczki dalej nie ma. Gdzie ona jest? Nr 48211
2. Jogurty przyszły ciepłe i jeden był otwarty. Chcę zwrot pieniędzy.
3. Czy wasze batony owsiane mogą zawierać śladowe ilości orzechów? Syn ma silną alergię.
4. Proszę o usunięcie wszystkich moich danych z waszej bazy.
5. Trzeci raz piszę w sprawie zwrotu i nikt nie odpowiada. Jeśli nie dostanę odpowiedzi do jutra, zgłaszam sprawę do UOKiK.
6. Super obsługa, dziękuję za szybką dostawę!
7. Czy mogę zmienić adres dostawy? Zamówienie 48907 jeszcze nie wyszło.
8. Jak długo mam na odesłanie nieotwartej kawy ziarnistej?
</wiadomosci>

<format>
Tabela: Nr | Kategoria | Priorytet | Obsługa | Uzasadnienie (maks. 10 słów). Bez wstępu i podsumowania.
</format>
```

## Wyniki: wiadomości-pułapki
| Wiadomość | Wersja 1 | Wersja 2 | Wersja 3 |
|---|---|---|---|
| 3 (alergia) |	wysoki, człowiek | wysoki, człowiek | wysoki, człowiek |
| 4 (usunięcie danych) | wysoki, człowiek | wysoki, człowiek |	wysoki, człowiek |
| 5 (groźba UOKiK) | krytyczny, człowiek |	krytyczny, człowiek | wysoki, człowiek |

## Wnioski
Wnioski po porównaniu wyniku 2 promptów:
1.	Konkretne i klarowne opisanie Kategorii  od razu widać, czego dotyczy bez konieczności domysłów (oraz zbędnych opisów)
2.	Pomimo braku przykładów przy pierwszym prompcie, definicja Priorytetu oraz Rodzaj obsługi zostały tak samo sklasyfikowane. Może to być efekt prostego zadania.
3.	W przypadku wrażliwego obszaru, jakim jest RODO – w obu przypadkach podana ta sama kwalifikacja. Status ustawiony na „krytyczny”. 
4.	Ciekawym jest, że w obu wersjach AI potraktowała wiadomości związane z UOKiK surowiej od wiadomości związanych z ryzykiem alergii.
5. Po trzecim prompcie: różnice są nieznaczne. Od początku AI dobrze i w ten sam sposób klasyfikuje zdarzenia, a to niezależnie od wytycznych. Różnica jest dopiero przy 3 wersji promptu, gdzie AI zmieniło klasyfikację dla tematów prawnych RODO z „krytyczny” na „wysoki”. Same przykłady (wersja 2) nie ograniczyły skali, mimo że pokazywały tylko niski, średni i wysoki. Dopiero jawne reguły w wersji 3 to zrobiły. Zmiana jednak to byłby dobry wniosek przy testach, żeby zastanowić się nad wprowadzeniem wiadomości krytycznych i odróżnieniem ich od priorytetowo wysokich. 
Uzasadnienie jest też z każdą wersją krótsze (bardziej konkretne) - W wersji 3 to skutek instrukcji „maks. 10 słów”, nie większej konkretności modelu.
