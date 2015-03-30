# Przegląd literatury z zakresu monitorowania natężenia ruchu ulicznego #

# Prezentacja #
[Przegląd dziedziny](https://docs.google.com/presentation/d/1ZW5tvpGnP5ql1OY-FDn84R6XRJrOP5uHEf1vXlCNzkg)

# Acquiring Road Traffic Information through Mobile Phones #
Anurak Poolsawat, Wasan Pattara-Atikom, and Boonchai Ngamwongwattana

## Komentarz ##
Jeden z pierwszych artykułów dotyczących tej tematyki. W czasie gdy powstawał nie było jeszcze smartfonów z WiFi i GPS w standardzie.

## Wprowadzenie ##
  * Przegląd istniejących metod kontrolowania stopnia zatłoczenia:
    * wskazówki udzielane przez radio
    * ekrany na autostradzie wyświetlające ograniczenia prędkości
  * Systemy wykorzystujące kamery i sensory w ustalonych miejscach są drogie w zakupie i utrzymaniu. Aby działać efektywnie muszą być wdrożone na dużą skalę.
  * Operatorzy telefonii komórkowych nie gromadzą informacji o natężeniu ruchu.

## Architektura systemu ##
  * Zaprezentowanie systemu monitorującego zatłoczenie ulic Bankgoku.

  * Telefony komórkowe z aplikacją wysyłającą informacje uzyskane z nadajnika sieci komórkowej, odbiornika GPS lub według subiektywnej oceny użytkownika do serwera przez HTTP POST.

### GSM ###
Informacje z nadajnika GSM:
  * Mobile Country Code
  * Mobile Network Code
  * Location Area Code
  * Cell ID (CID - kod obszaru)

Komórka znajduje się w CID z największą siłą sygnału. Aplikacja mierzy czas znajdowania się telefonu w obszarze CID i wysyła go do serwera w momencie przełączenia się do innego obszaru. Pułapka: CID mogą mieć różne obaszary, stąd ważna jest ilość zebranych próbek.

### GPS ###
  * Wysyłanie co sekundę informacji o lokalizacji.

## Zakończenie ##
  * Analiza kosztów transmisji danych.
  * Dokładność systemu zależy od wielkości społeczności.

# Ubiquitous Architecture for Environmental Sensor Networks in Road Traffic Applications #
J. Guevara, E. Vargas, IEEE, Member, F. Barrero, IEEE, Senior Member, S. Toral, IEEE, Senior
Member

## Komentarz ##
  * Tytuł artykułu brzmi obiecująco, jednak nie da się go wykorzystać w naszym projekcie. Natężenie ruchu ulicznego mierzone jest za pomocą czujników CO w powietrzu, a architektura systemu została zrealizowana w oparciu o standrd IEEE 1451, który nie ma wiele wspólnego z urządzeniami mobilnymi rozumianymi jako telefony komórkowe.

## Streszczenie ##
  * Przedstawienie zarysu budowy sieci sensorowych w samochodach. Wymienienie zalet bezprzewodowych sieci sensorowych.
  * Propozycja zrealizowania systemu monitorowania natężenia ruchu za pomocą środowiskowej sieci sensorowej mierzącej jakość powietrza przy użyciu sensorów umieszczonych w pojazdach.
  * Omówienie standardu sieci sensorowych IEEE 1451 i opis realizacji systemu monitorowania natężenia ruchu.

## Wnioski ##
  * Stopień stężenia CO w powietrzu pozwala na wnioskowanie o natężeniu ruchu.
  * Standard IEEE 1451 oferuje bardzo efektywną architekturę sieci sensorowych.

# iTETRIS: An Integrated Wireless and Traffic Platform for Real-Time Road Traffic Management Solutions #
O. Lazaro, E. Robert, L. Lan, J. Gozalvez, S. Turksma, F. Filali, F. Cartolano, M. A. Urrutia, D.
Krajzewicz

## Komentarz ##
  * Artykuł przedstawia wymagania funkcjonalne i kontekst systemu iTETRIS przeznaczonego do symulacji ruchu ulicznego. Nie zawiera opisu żadnych algorytmów oraz propozycji, w jaki sposób można osiągnąć zamierzone cele. Bardzo obiecujące wydaje się zestawienie projeków zajmująch się problmatyką transportu drogowego.

## Wprowadzenie ##
  * V2V - Vehicle to Vehicle
  * V2I - Vehicle to Infrastructure

  * Protokoły umożliwiające komunikację V2V i V2I pozwalają na usprawnienie zarządzania ruchem poprzez wymianę w czasie rzeczywistym informacji między pojazdami i infrastrukturą drogową. Nie zostały one jednak jeszcze dokładnie zbadane i nie istnieje dojrzała technologia umożliwiająca taką komunikację.

## Ciekawostki światopoglądowe ##
  * 40% pożyczek Banku Światowego przeznaczone jest na usprawnienia infrastruktury drogowej.
  * Odpowiednie zarządzanie ruchem pozwala zwiększyć o 20-30% przepustowość istniejącej infrastruktury drogowej.

## Zakres projektu iTETRIS ##
  1. opracowanie platformy open source do symulacji ruchu ulicznego
  1. specyfikacja niezawodnych i dynamicznych protokołów komunikacji dla pojazdów
  1. dostarczenie automatycznie konfigurujących się, posiadającą zmienną granulację, polityk zarządzania ruchem w czasie rzeczywistym

## Symulacje ruchu w wielkiej skali ##
  * Zostały opracowane modele koncepcyjne komunikacji V2V i V2I, jednak nie zostały one jeszcze przetestowane w rzeczywistym środowisku i w dużej skali.
  * Obecnie prowadzone są analizy wpływu systemów z serii "inteligentny samochód" na dynamikę jazdy i zachowanie kierowców. Wyniki zostaną wykorzystane do oszacowania kosztów i korzyści wynikających z wdrożenia takich systemów.

## Ciekawe projekty badające protokoły V2x ##

### C2C-CC Car 2 Car Communications Consortium ###
http://www.car-to-car.org/
#### Cel ####
  * opracowanie otwartego standardu przemysłowego komunikacji systemów Car 2 Car opartego o bezprzewodową sieć LAN.
#### Wyniki ####
  * Wariant algorytmu zarządzania ruchem jaki należy zastosować zależy od natężenia ruchu. W intensywnym natężeniu ruchu protokół powinien dostosowywać się do dostępnego pasma sieci. W rzadkim natężeniu ruchu bardziej krytyczne jest efektywne cachowanie i przełączanie wiadomości.         Protokół powinien brać pod uwagę utratę pakietów, krótkie czasy trwania połączeń, wysokie RTT.

### CVIS - Cooperative Vehicle-Infrastructure System ###
http://www.cvisproject.org - rozwijanie i testowanie nowych technologiii komunikacji pojazdów z infrastrukturą drogową.

### GeoNet ###
  * rozwijanie specyfikacji implementacji protokołów geograficznego adresowania i routowania w komunikacji V2V i V2I w IPv6.

### SMART-NETS - Signal MAnagement in Real Time for Urban TRaffic NETworkS ###
  * http://www.smartnets.napier.ac.uk
  * zbadanie w jakim stopniu strategia zarządzania ruchem Traffic-responsive Urban Control sprawdza się w sytuacjach wzrastającego natężenia ruchu w porównaniu do innych strategii: TASS, SCOOT i BALANCE.

### MORYNE - Enhancement of public transport efficiency trough the use of mobile sensor networks ###
  * http://www.fp6-moryne.org
  * koncepcja lokalnego zarządzania ruchem na podstawie informacji otrzymywanych z urządzeń mobilnych i publicznego transportu

### COVER ###
  * http://www.ist-cover.eu
  * dostarczanie aplikacji zwiększających przepustowość infrastruktury transportowej i podnoszących bezpieczeństwo na drogach

## Trafficc and Road Condition Monitoring System ##
Ashish Dhar

### Komentarz ###
Raport opisuje propozycję realizacji systemu natężenia ruchu ulicznego i wykrywania dziur w jezdni w Indiach. Natężenie ruchu mierzone jest przez zewnętrzną infrastrukturę wykrywającą zmiany pola magnetycznego. Mobilna sieć akcelerometrów wykorzystana została do lokalizowania dziur w jezdni. Ciekawy przegląd istniejących rozwiązań technologicznych dotyczących rozpoznawania, zliczania, szacowania prędkości pojazdów.

### Streszczenie ###
  * Omówienie warunków na drogach w Indiach, które dyskwalifikują zastosowanie istniejących systemów mierzenia natężenia ruchu - chaotyczne, brak ustalonego kierunku ruchu, duża różnorodność pojazdów. Proponowany system nie powinien wymagać modernizacji dróg, być tani w utrzymaniu i wdrożeniu.
  * Analiza korzyści wynikających z monitorowania natężenia ruchu
    * ostrzeganie przed korkami za pomocą SMS
    * automatyczne adaptowanie długości oczekiwania na światłach drogowych
    * planowanie trasy z ominięciem zatłoczonych odcinków trasy
wczesne wykrywanie dziur w jezdni
    * klasyfikacja, zliczanie, obliczanie prędkości pojazdów

  * Opisanie istniejących systemów monitorowania ruchu pod względem możliwości (zliczanie pojazdów, rozpoznawanie typu pojazdu, szacowanie prędkości, dokładność, działanie w różnych warunkach pogodowych, koszt wdrożenia i utrzymania):
    * Magnetyczne pętle - zainstalowane w jezdni detektory zmian pola magnetycznego
    * Kamery
    * Radary mikrofalowe
    * Systemy laserowe
    * Detektory podczerwieni
    * Detektory ultradźwiękowe
    * Detektory zmian pola magnetycznego gleby - Anisotrobic Magneto-Resistive AMR Magnetic Sensors

  * Techniki wykrywania dziur w jezdni
    * Ludzkie patrole
    * Radar

  * Wykrywanie dziur w jezdni przez akcelerometry umieszczone w pojazdach - potrzeba odfiltrowywania zdarzeń:
    * hamowanie/przyśpieszanie
    * otwieranie drzwi
    * przejazd przez tory kolejowe
  * Zebranie informacji z uwzględnieniem wielu okien czasowych (przyśpieszanie), z wielu pojazdów oraz znajomość infrastruktury(tory kolejowe), pozwala wykluczyć powyższe błędne wskazania akcelerometrów.

  * Propozycja nowej metryki oceny zatłoczenia ulicy - jaka powierzchnia jezdni jest zajęta przez samochody.

# A public transport system based sensor network for road surface condition monitoring #
Kasun De Zoysa, Chamath Keppitiyagama, Gihan P. Seneviratne, and W. W. A. T. Shihan.

  * Zamontowanie w autobusach nadajników GPS, dane zbierane przez lokalne stacje postoju.

  * Inne techniki oceny natężenia ruchu ulicznego uwzględniające mobilną sieć pojazdów z nadajnikami GPS:
    * Prashanth Mohan, Venkata N. Padmanabhan, and Ramachandran Ramjee. Nericell: Rich monitoring of road and trafficc conditions using mobile smartphones.
    * Jungkeun Yoon, Brian Noble, and Mingyan Liu: Surface street traffic estimation

# Partial Global Planning #
[ftp://mas.cs.umass.edu/pub/Durfee/Durfee_IEEE_PGP91.pdf](ftp://mas.cs.umass.edu/pub/Durfee/Durfee_IEEE_PGP91.pdf)
[ftp://dis.cs.umass.edu/pub/lesser/decker-ijicis.pdf](ftp://dis.cs.umass.edu/pub/lesser/decker-ijicis.pdf)
Dwie dość ciekawe publikacje na temat "Partial global planning" czyli właściwie dokładnie to o co nam chodzi. Polecam się zapoznać :)


# In-Network Path Planning for Distributed Sensor Network Navigation in Dynamic Environments #

http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=4660043 (do pobrania z sieci AGH)

Artykuł na temat planowania ścieżek w sieciach sensorów czyli to do czego będziemy dążyli

# Dynamic Road Traffic Management based on Krushkal’s Algorithm #
[Artykuł](https://dl.dropbox.com/u/16733251/05972263.pdf)

Tu jest opis algorytmu wykorzystujący Krushkala i Dijkstra do szacowania najlepszej drogi na podstawie natężenia ruchu. Nie przeczytałem artukułu do końca, ale wyglądam obiecująco.

# Adaptive Routing schemes for Intelligent Transportation Systems #

https://wiki.qut.edu.au/display/TRG/Adaptive+Routing+schemes+for+Intelligent+Transportation+Systems - uczelniane rozwiązanie C2C

# Vehicular ad-hoc network (VANET) #
http://en.wikipedia.org/wiki/Vehicular_ad-hoc_network

# Mobile ad-hoc network (MANET) #
http://en.wikipedia.org/wiki/Mobile_ad_hoc_network

# Intelligent vehicular ad-hoc network #
http://en.wikipedia.org/wiki/InVANET

# Komercyjne rozwiązania #

## TomTom Traffic ##
http://www.tomtom.com/livetraffic/

## Google Maps Navigator ##
[Opis algorytmu](http://googleblog.blogspot.com/2009/08/bright-side-of-sitting-in-traffic.html) - najważniejsza cześć: "(...)your phone sends anonymous bits of data back to Google describing how fast you're moving. When we combine your speed with the speed of other phones on the road, across thousands of phones moving around a city at any given time, we can get a pretty good picture of live traffic conditions. We continuously combine this data and send it back to you for free in the Google Maps traffic layers. It takes almost zero effort on your part — just turn on Google Maps for mobile before starting your car — and the more people that participate, the better the resulting traffic reports get for everybody.(...)"

http://www.iphoneincanada.ca/tips-tricks/how-google-maps-live-traffic-works-crowdsourcing/

http://www.google.com/mobile/maps/

## Waze ##
http://www.waze.com/

## CVIS ##
http://www.cvisproject.org/download/CVIS_Handbook_FINAL%20Version.pdf