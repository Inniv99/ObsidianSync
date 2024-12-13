#Q3 #TW Erstellt am 13.12.2024 um 18:27 Uhr

---
Ein Mutex (Mutual Exclusion) sperrt ein bestimmtes Code-Segment, sodass dieses zu einem bestimmten Abschnitt des [[Prozesse]]s ausgeführt wird. Diese Sperrung führt ein Thread selbst aus und nur dieser Thread kann diese auch wieder aufheben. Mutex benutzen Prioritätsvererbung d.h. Prozesse mit hoher Priorität werden so kurz wie möglich blockiert.

### Wofür wird ein Mutex verwendet?

Ein Mutex wird verwendet, um den Zugriff auf gemeinsam genutzte Ressourcen in einem parallel arbeitenden System zu kontrollieren und zu synchronisieren. Es stellt sicher, dass zu einem bestimmten Zeitpunkt nur ein Thread oder Prozess die betreffende Ressource benutzt. Typische Anwendungsfälle sind:

- Dateisystemzugriffe
- Netzwerkkommunikation
- Zugriff auf gemeinsam genutzte Datenstrukturen
- Controlling hardware components


