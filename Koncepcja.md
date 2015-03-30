# Koncepcja rozwiązania #

## Opis ##

Projekt AutoMobile ma na celu wspomagać kierowcę przy wyborze optymalnej drogi przejazdu, biorą pod uwagę bieżącą sytuację na drogach. Urządzenia mobilne w samochodach będą wymieniały się informacjami, aby uzyskać wiedzę o aktualnych warunkach drogowych. Wykorzystując zdobytą wiedzę o zatłoczeniu, korkach, przepustowości itp. AutoMobile wybierze ścieżkę, dzięki której dostaniemy się najszybciej z jednego punktu do drugiego. System AutoMobile będzie w stanie negocjować drogę z innymi urządzeniami, tak aby nie powodować sytuacji, że jakaś droga stanie się nieprzejezdna.

## Zakres projektu i technologia ##
W projekcie AutoMobile każde urządzenie mobilne traktujemy jako agenta. Agent nie posiadają globalnej wiedzy o środowisku (stanie dróg). Może zdobyć tę wiedzę przez eksplorację środowiska i wymianę informacji z innymi agentami. Urządzenia wymieniają się informacją, gdy znajdą się w pewnej odległości od siebie (samochody jadą w tę samą lub przeciwną stronę). Każdy agent realizuje dwa cele: dostanie się z punktu A do punktu B w jak najkrótszym czasie oraz zminimalizować sumaryczny czas przejazdu wszystkich agentów. Może to powodować, że czasami agent wybierze z pozoru dłuższą dla siebie ścieżkę, ale dzięki temu umożliwi łatwy przejazd innym użytkownikom dróg i samochody dojadą szybciej do celu. Realizując cel globalny agentów, możemy znacznie zwiększyć przepustowość dróg. W projekcie AutoMobile wykorzystamy agentowy fraemwork [JADE](http://jade.tilab.com/), który można uruchomić na systemie Android i Windows Phone.

W AutoMobile na czas testowania systemu powstanie specjalny centralny agent, który będzie miał pełną informację o systemie. W znacznym stopniu uprości to implementacje komunikacji między agentami oraz stworzenie innych części systemu.

Każdy samochód zbiera takie informacje jak: czas potrzebny aby dostać z punktu A do punktu B, ile samochodów jadących w przeciwną stronę minąłem, ile razy musiałem się zatrzymać itp. Do pobierania takich informacji wykorzystamy odbiorniki GPS oraz protokół do komunikacji między urządzeniami mobilnymi.
W systemie AtobMobile wykorzystamy zaawansowane algorytmy do planowania ścieżek w środowisku, o którym nie mamy pełnej wiedzy - Partial Global Planning.

## Podsumowanie ##
  * Traktowanie urządzenia mobilnego jako agenta w środowisku,
  * stworzenie specjalnego, centralnego agenta, który posiada pełną informację o systemie oraz ułatwia komunikację między agentami,
  * zdobywanie wiedzy przez agenta na podstawie eksploracji systemu (poruszanie się po drodze i mierzenie parametrów przejazdu),
  * zdobywanie wiedzy przez agenta przez wymianę informacji z innymi agentami (samochody które są blisko, komunikują się ze sobą)
  * realizacja celu lokalnego agenta: wybranie optymalnej drogi przejazdu,
  * realizacja celu globalnego: minimalizacja czasu przejazdu wszystkich agentów (agent czasami wybierze ścieżkę suboptymalną aby ułatwić poruszanie się innym agentom).