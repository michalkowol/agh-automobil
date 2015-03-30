## Wprowadzenie ##

W ramach weryfikowania przydatności JADE w projekcie agh-automobil uruchomiono aplikacje demo przygotowane przez zespół JADE na platformach Android i .Net.

## Szczegóły ##

Kroki potrzebne do uruchomienia aplikacji zostały opisane w osobnych dokumentach:
  * [Android](https://agh-automobil.googlecode.com/files/Tutorial_Jade_Android.pdf)
  * [.Net Framework](https://agh-automobil.googlecode.com/files/Tutorial_Jade_DotNet2.pdf)

## Podsumowanie ##

Framework JADE udostępniana jest w różnych wersjach:
  * Java
  * JADE Leap Android
  * JADE Leap .Net

Każda z wersji różni się oferowaną funkcjonalnością. Najbardziej uboga jest wersja na platformę .Net.

### Wsparcie JADE dla platformy .Net ###

Port JADE dla .NET napisano w języku J#, który przestał być wspierany w 2005 roku. Uruchomienie dema, o bardzo okrojonej funkcjonalności przysporzyło wiele problemów, które szczegółowo zostały opisane w osobnym dokumencie.

Poniżej znajduje się lista ograniczeń dla programistów wykorzystujących JADE na platformie .Net:

  * JADE-LEAP for dotnet is derived from JADE-LEAP pjava version and there is't any graphical interface (except for Sniffer agent GUI).
  * At the moment, it is not possible to “introspect” (by means of the Introspector agent) an agent running on a dotnet container.
  * The HTTPS service is not supported.
  * The Mobility service is supported with the following limitation:
  * If you would transfer an agent with a GUI, the GUI have to be written in J# language using the Java Swing components available with the Supplementary UI packages from Microsoft (see 1.3)
  * RMI is not supported.
  * It is not possible to monitor .NET agents with Java RMA agent GUI.
  * Communication between .NET agents and Java agents is possible using HTTP Message Transport Protocol.

### Komentarz ###
Wpieranie platformy .Net nie jest priorytetem dla zespołu JADE, a próbą do zainteresowania frameworkiem większej liczby klientów.

### Wsparcie JADE dla platformy Android ###

Projektem demo na platformę Android był chat umożliwiający użytkownikom aplikacji na wybranie loginu i wymienianie wiadomości tekstowych. Do działania systemu potrzebne było wcześniejsze uruchomienie serwera JADE w osobnym procesie.

Autor nie znalazł informacji o ograniczeniach wersji JADE na platformę Andorid.