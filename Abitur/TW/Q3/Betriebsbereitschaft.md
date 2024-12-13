#Q3 #TW Erstellt am 13.12.2024 um 16:45 Uhr

---
###### DTR und DSR-Signalisierung 
![[Pasted image 20241213164631.png]]

1. DTE aktiviert DTR
2. DCE schaltet Fernverbindung auf betriebsbereit
3. sobald die Betriebsbereitschaft hergestellt wurde, aktiviert DCE DSR
4. die Datenübertragung beginnt 
5. DTE signalisiert das Ende der Datenübertragung durch Deaktivierung von DTR 
6. DCE überträgt die noch anhängigen Daten, wodurch die Fernverbindung frei wird und DSR wird wieder deaktiviert