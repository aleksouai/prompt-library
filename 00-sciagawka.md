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
- Noreply = prywatność adresu e-mail (commity są publiczne). 2FA = ochrona przed przejęciem konta.
- Commit = jeden zapis zmian (kto, kiedy, co). Historia commitów = możliwość śledzenia i cofania.
- Blok kodu na GitHubie: bez niego Markdown ukrywa tagi <...> i zamienia # w nagłówki. To nie ma związku z modelem AI.
