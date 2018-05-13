# Maschinenbelegungsplanung

## Problemstellung und Motivation

Frühere Epochen der Großserienfertigung waren durch eine fortschreitende Zentralisierung der Betriebe gekennzeichnet, die auf die Zeit der industriellen Revolution und die Entstehung des Fabriksystems aus der früheren Handwerksproduktion zurückging. Charles Babbage, in “Economy of Machinery and Manufactures” (Babbage 1835), über die Arbeitsökonomie, die durch maschinelle Produktion erleichtert wurde. Die technischen Entwicklungen seiner Zeit wurden begleitet durch die Entstehung von Fabriksystemen und den damit verbundenen Produktivität- und Kostenvorteilen. Zwar können Fabriken effizient produzieren, jedoch ist dieses zentralisierte Paradigma auch durch langwierige, langsam reagierende Lieferketten geprägt. In den letzten drei Jahrzehnten hat Globalisierung die Industrielandschaft mit einzelnen internationalen Produktionsstandorten, die regionale und globale Märkte bedienen, weiter verändert. 

Bei der zentralisierten Werkstattfertigung - also im klassischen Job Shop - wird angenommen, dass es eine einzige Produktionsstätte mit $$m$$ Maschinen gibt. Das Problem besteht darin $$n$$ jobs mit jeweils eigenen Prozessrouten so einzutakten, dass eine Zielfunktion minimiert wird. Meist wird hierfür die Fertigungsdauer, als die maximale Zeit zur Fertigstellung aller Jobs, verwendet. Es werden bei den Lösungsverfahren meist folgende Annahmen getroffen:

- Maschinen & Jobs sind kontinuierlich verfügbar
- Rüstzeit können ignoriert werden oder sind in den Prozesszeiten integriert
- Ein Job kann nur auf einer Maschine gleichzeitig bearbeitet werden
- Eine Maschine kann nur einen Job gleichzeitig bearbeiten

Der Trend zu mehreren Fabriken, die die gleichen Güter für unterschiedliche Märkte produzieren, verändert auch die Anforderungen und Problemstellungen der Maschinenbelegungsplanung. Im Distributed Jobs Shop, bestehend aus $$f$$ Produktionsstätten mit jeweils $$m$$ Maschinen, wird die Planung komplexer. Es müssen zwei Entscheidungen getroffen werden:
(1) Verteilung der Jobs auf die Produktionsstätten 
(2) Einplanung der Jobs auf die Maschinen

Im Distributed Jobs Shop Problem werden zusätzlich zum klassischen Job Shop folgende Annahmen getroffen:

- Jobs können nicht mehreren Produktionsstätten bearbeitet werden
- Produktionsstätten haben jeweils einen identischen Maschinenpark

Die Maschinenbelegungsplanung im Distributed Job Shop kann durch die Adaption von bestehenden Regel-basierten Heuristik oder durch Greedy Heuristiken gelöst werden. Die im Paper “Modeling and heuristics for scheduling of distributed job shops” von Nadir B. und Azab A. entwickelten Heuristiken sollen im folgenden näher erläutert werden.

## Anwendungsbeispiel in der Praxis

Gerade die Halbleiterindustrie lebt schon seit einigen Jahren im Distributed Job Shop innerhalb eines globalen Produktionsnetzwerkes. Zu beobachten ist, dass viele Halbleiterfertiger gerade in der Frontend Produktion (Aufbringen der Transistoren auf dem Wafer) ein weltweites Produktionsnetzwerk haben. In der verschieden Fabriken werden oft auch identische Produkte gefährdet, um den regionalen Bedarf zu sättigen. 

Infineon, beispielsweise, hat 12 Frontend Produktionsstätten weltweit.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_34AC10E35AF26487536528661EC7BDE438B5E36D9B8556471EC64FB0C6D83780_1526112815141_Screen+Shot+2018-05-12+at+10.12.26+AM.png)


Jeder Wafer hat dabei ein spezielles Rezept (Operationsreihenfolge) und wird in dieser Reihenfolge auf unterschiedlichen Maschinen bearbeitet. Selbst die Annahme, dass Rüstzeiten aus der Betrachtung ausgeschlossen werden, trifft bei fast allen Prozessen aufgrund einem hohen Automatisierungsgrad zu.
