# SportLab 2.0 — pierwszy działający fundament (PWA)

To **nowy projekt**, nie aktualizacja poprzedniego `app.py` w Streamlit.

## Co jest zaimplementowane
- Samodzielna aplikacja internetowa PWA (HTML/CSS/JavaScript, bez płatnego hostingu i kluczy API).
- Katalog 24 zatwierdzonych rozgrywek, dynamiczny wybór daty i dostępnych meczów.
- Pobieranie terminarzy i wyników z publicznego repozytorium open-matchday.
- Historia ostatnich meczów w **tych samych rozgrywkach**, średnie goli strzelonych/straconych.
- Uproszczony model Poissona, do trzech propozycji tylko przy dostatecznej liczbie meczów.
- Czat regułowy rozumiejący część pytań o gole i formę, bez płatnej AI.
- Podstawowe testy jednostkowe (`node test.js`).

## Co jeszcze NIE działa / nie jest gotowe
- Brak potwierdzonych kontuzji i składów (nie są wymyślane).
- Brak analizy siły rywali, tabel ligowych, wieloligowej historii klubów, statystyk strzałów/rożnych/kartek, wiarygodnego inteligentnego modelu językowego.
- Procenty z uproszczonego Poissona **nie są skalibrowane ani zweryfikowane na danych historycznych**.
- Nie wszystkie z 24 rozgrywek muszą mieć pliki w źródle. Nazwy folderów są dopasowywane według konwencji repozytorium i wymagają testu z aktualnym katalogiem.
- Godzina z pliku źródłowego jest wyświetlana **bez przeliczania strefy** — nie zakładaj, że jest polska. Data wybrana w formularzu odpowiada dacie źródła.
- Brak danych / brak meczów w źródle nie dowodzi, że mecz nie istnieje.
- Aplikacja wymaga połączenia z internetem do pobrania danych. Cache PWA obejmuje tylko pliki aplikacji, nie zewnętrzne terminarze.
- W tym środowisku nie było możliwe przetestowanie pobierania plików na żywo z GitHub. Przetestowano składnię i funkcje lokalne.

## Publikacja za 0 zł (GitHub Pages)
1. Utwórz **nowe publiczne repozytorium**, np. `sportlab-2`, nie nadpisuj starego SportLab.
2. Prześlij pliki z tego folderu do głównego katalogu repozytorium (bez folderu nadrzędnego).
3. W repozytorium otwórz **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Wybierz `main` i `/ (root)`, zapisz. GitHub poda adres strony.
5. Otwórz adres w Safari na iPhonie i użyj **Udostępnij → Dodaj do ekranu początkowego**, aby używać jako PWA.

Nie działa poprawnie przez dwuklik w `index.html` (file://) — uruchom przez HTTPS/hosting.

## Źródło i warunki
Dane: https://github.com/oladeeayo/open-matchday — publiczne dane dla zastosowań informacyjnych, **niekomercyjnych**, z obowiązkiem atrybucji. Źródło agreguje dane od innych dostawców; sprawdź ich warunki przed publicznym wdrożeniem. Nie sprzedawaj dostępu do tych danych. GitHub API ma limity zapytań.

## Dalsze etapy
1. Test rzeczywistego pobierania i pokrycia 24 rozgrywek; naprawa mapowania folderów i sezonów.
2. Dane historyczne z różnych rozgrywek, normalizacja nazw i stref czasowych.
3. Walidacja modelu i uwzględnianie siły przeciwników.
4. Wiarygodne statystyki strzałów/rożnych/kartek i potwierdzone absencje.
5. Rozbudowa czatu oraz testy regresji i testy integracyjne.
