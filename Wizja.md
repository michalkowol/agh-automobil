# Wizja #

> ## 1. Wstęp ##
Celem niniejszego dokumentu jest ogólne nakreślenie i scharakteryzowanie wymagań stawianych systemowi ze względu na jego przeznaczenie i sposób użycia, a także określenie najważniejszych założeń jego realizacji. Wszelkie decyzje implementacyjne nie są tu podejmowane i opisane zostaną w następnych dokumentach.


> ## 2. Opis problemu ##

W dzisiejszych czasach nawigacja GPS, oparta o statyczne wyznaczanie trasy, przestaje być wystarczająca. Ze względu na bardzo dużą, stale rosnącą liczbę samochodów i szybko zmieniające się warunki na drogach (korki, remonty, wypadki itp.) do wyznaczenia optymalnej trasy przejazdu konieczne jest jej ciągłe aktualizowanie na podstawie informacji o bieżących warunkach drogowych.
Jednym z możliwych rozwiązań problemu jest wykorzystanie powszechności oraz możliwości (obliczeniowych, komunikacyjnych) współczesnych urządzeń mobilnych. Przy ich pomocy możemy gromadzić informacje o czasie przejazdu danej trasy i następnie wymieniać je z innymi urządzeniami.


> ## 3. Opis użytkownika i zewnętrznych podsystemów ##
Użytkownikiem jest kierowca samochodu, który chce dotrzeć do danego punktu docelowego.

> ## 4. Opis produktu ##

System składa się z wielu, autonomicznych, równorzędnych agentów (urządzeń mobilnych).

Głównym zadaniem systemu jest wyznaczanie najszybszej trasy do punktu docelowego na podstawie informacji wymienianych z innymi agentami znajdującymi się w pobliżu. Po każdej wymianie informacji agent aktualizuje optymalną trasę przejazdu. Agenci komunikują się ze sobą bezpośrednio (brak punktu centralnego).

> ## 5. Wymagania funkcjonalne i ich priorytety ##
    * wyznaczanie i aktualizacja optymalnej trasy przejazdu do punktu docelowego
    * wyświetlenie wyznaczonej trasy przejazdu

> ## 6. Inne wymagania dotyczące produktu ##
    * brak centralnego węzła
    * wymagania systemowe - system powinien być heterogeniczny (system Android oraz Windows Phone)
    * dokumentacja - dokumentacja techniczna w formie wiki


> ## 7. Wstępna analiza ryzyka ##
    1. Wybrana architektura wpłynie na brak zadowalających wyników (brak jakichkolwiek implementacji PGP), prawdopodobieństwo 6/10, skutki 10/10.
    1. Problemy z heterogenicznością systemu, prawdopodobieństwo 3/10, skutki 3/10.
    1. Ograniczony czas i środki na wykonanie systemu, prawdopodobieństwo 2/10, skutki 5/10.