# Ściągawka AI

## Markdown (format plików .md)

| Co | Jak zapisać |
|---|---|
| Nagłówek / podtytuł | `#` / `##` na początku linii |
| Punkt listy | `-` na początku linii |
| Tabela | kolumny oddzielone `\|`, pod nagłówkiem linia `\|---\|---\|` |
| Blok kodu (tekst 1:1) | linia z trzema backtickami przed i po tekście |

- Backtick to znak ` (klawisz pod Esc).
- Blok kodu: ZAWSZE dla promptów. Bez niego GitHub ukrywa tagi typu <rola> i łączy linie.
- Przed tabelą zostaw pustą linię, inaczej się nie wyświetli.
- Zawsze sprawdzaj wynik w zakładce Preview przed zapisem.

## GitHub

- Nowy plik: Add file → Create new file → nazwa z końcówką .md
- Edycja pliku: otwórz plik → ołówek (Edit) → Preview → Commit changes
- Commit = zapisana wersja zmian (co, kto, kiedy, opis). Opis krótki i konkretny, np. „Popraw formatowanie promptów”.
- Adres noreply (Settings → Emails): ID+username@users.noreply.github.com. Podpisuje commity zamiast prawdziwego e-maila. To nie jest skrzynka.

## Prompty

Struktura promptu (tagi oddzielają dane od instrukcji):
- <rola> kim jest model
- <kontekst> dane i fakty
- <zadanie> co ma zrobić
- <zasady> ograniczenia, np. „tylko dane z kontekstu, założenia oznacz [ZAŁOŻENIE]”
- <format> struktura i długość odpowiedzi
- <przyklad> wzór stylu (few-shot), opcjonalnie

Zanim poprawiasz prompt, miej:
1. kryteria sukcesu (np. tabela ocen 1–5),
2. sposób testu (porównanie wersji),
3. pierwszą wersję promptu.

Testowanie:
- Każda wersja w NOWYM czacie, inaczej model sugeruje się poprzednią.
- Każda wersja promptu w pliku = prompt + ocena + wnioski.

Pułapki:
- Format może przesądzić decyzję (np. sekcja „pilotaż” zakłada „tak”). Dodaj: „jeśli »nie«, opisz warunki zmiany decyzji”.
- Poprawki od Claude'a oceniaj krytycznie, nie przyjmuj automatycznie.

## Moje błędy

| Problem | Naprawa |
|---|---|
| Tagi w prompcie zniknęły na GitHubie | Otocz prompt blokiem kodu (trzy backticki) |
| Tabela skopiowana z czatu = zwykły tekst | Zapisz ją składnią Markdown (`\|` i `---`) |

## Bezpieczeństwo i GitHub – poprawki z powtórki L02
- Noreply = prywatność adresu e-mail (commity są publiczne). 2FA = ochrona przed przejęciem konta. Adres zastępczy w commitach → chroni prywatność (spam, wyciek maila).
- Commit = jeden zapis zmian (kto, kiedy, co). Historia commitów = możliwość śledzenia i cofania + data. Publiczny.
- Blok kodu na GitHubie: bez niego Markdown ukrywa tagi <...> i zamienia # w nagłówki. To nie ma związku z modelem AI.
- 2FA = hasło + kod z telefonu → chroni konto przed przejęciem.

## Oznaczenia w promtach
Tagi XML (<nazwa> … </nazwa>):
- To nie HTML. Nazwy wymyślam sama, model rozumie je po znaczeniu.
- Zawsze, gdy wklejam dokument/dane albo piszę szablon do wielokrotnego użytku.
- Przy krótkich pytaniach zbędne. Przy prostych promptach mogą być nagłówki ##.
- Zawsze zamykam tag. Nazwy bez polskich znaków i spacji.

- ## Analiza dokumentów (L03)
- Dokument na górze promptu, pytanie na końcu. Każdy dokument w osobnym tagu.
- Ugruntowanie: najpierw dosłowne cytaty (C1, C2...), potem analiza z odwołaniami [C1].
- Pozwól modelowi napisać „BRAK W OGŁOSZENIU”, inaczej zgaduje, żeby wypełnić format.
- Weryfikacja: Ctrl+F w źródle, szukaj 5–6 pierwszych słów cytatu.
- Cytaty zmniejszają liczbę halucynacji, ale ich nie eliminują. Krytyczne dane sprawdzam sama.
- Repo publiczne: link zamiast pełnego tekstu, bez danych osobowych.

## Case strategiczny – zasady
- Brief mówi "3 priorytety" = dokładnie 3. Sprawy operacyjne osobno: "Higiena operacyjna (0–3 mies.)".
- Hipoteza = przyczyna, którą da się sprawdzić danymi. "Udziały spadają" to objaw, nie hipoteza.
- Każdy priorytet: czasownik + KPI z liczbą i terminem + czego NIE robimy.
- Przed oddaniem: sprawdź, czy żaden priorytet nie przeczy wybranej strategii, i sprawdź odwołania (P1, P2...).
- Efekt mianownika: mniej nowych klientów = wyższy % powracających bez zmiany lojalności. Sprawdzaj liczby bezwzględne i kohorty.
- Odpowiedź dla zarządu: decyzja → powód → co sprawdzę i kiedy. "Nie mam pewności, sprawdzę X" > obrona tezy.

## Prompt analityczny – zasady
- BRAK = brak faktu w źródłach. [ZAŁOŻENIE] = tylko interpretacja. Nie mieszaj tych reguł w jednym prompcie.
- Format musi pomieścić wszystko, o co prosi zadanie (np. mocne strony I ryzyka).
- Przykład numeru źródła w prompcie w tym samym formacie co w dokumentach ([1.4], nie [1-4]).
