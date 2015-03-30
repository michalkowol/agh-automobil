# Założenia implementacyjne #

  * Zadania planowania trasy są wykonywane przez agenty platformy JADE uruchomione na urządzeniach mobilnych.

  * Agenty na urządzeniach znajdujące się w bliskiej odległości wymieniają między sobą informacje dotyczące aktualnej historii przejechanej trasy

# Idealna architektura #

http://agh-automobil.googlecode.com/files/architektura-idealna.PNG

Architektura idealna zakłada istnienie pewnego protokołu komunikacji p2p, który mógłby być wykorzystany przez JADE i który jednocześnie byłby w stanie parować urządzenia mobilne w czasie rzeczywistym. Brak protokołu tego typu wyklucza niestety takie rozwiązanie i wymusza wprowadzenie dodatkowego komponentu w architekturze (zarówno z fizycznego punktu widzenia, jak i z punktu widzenia agentów).

# Realna architektura #

http://agh-automobil.googlecode.com/files/architektura-realna.PNG

![http://agh-automobil.googlecode.com/files/architektura-szczegoly.png](http://agh-automobil.googlecode.com/files/architektura-szczegoly.png)

Z fizycznego punktu widzenia pojawia się pewien serwer o znanym adresie. Z agentowego punktu widzenia pojawia się nowy agent, do którego wysyłane są wszystkie wiadomości od agentów mobilnych. Ten nowy agent zajmuje się dystrybucją informacji do zainteresowanych agentów - oblicza, które agenty znajdują się blisko siebie i na tej podstawie przekazuje informacje. Jest to hub komunikacyjny, którego zadaniem nie jest analiza uzyskiwanych od agentów informacji, z wyłączeniem informacji geolokalizacyjnych.