#Q3 #TWErstellt am 11.12.2024 um 19:03 Uhr

---
## Prinzip
Software-Handshakes werden durch bestimmte Steuerzeichen innerhalb einer seriellen Datenübertragung gesteuert.

## XON/XOFF
- XON: Signalisiert dem Sender, dass Empfänger empfangsbereit ist.
- XOFF: Signalisiert, dass das Senden eingestellt werden soll
- Für dieses Protokoll werden nur 3 Leitungen des [[RS232]]-Anschluss benötigt: TxD, RxD und GND

### Ablauf
1. Der Sender beginnt mit der Datenübertragung
2. Sollte der Buffer des Empfängers gefüllt sein, sendet er XOFF
3. Sobald er wieder genug freien Buffer hat, sendet er XON

### Vorteile
- Keine zusätzlichen Leitungen erforderlich
- Einfach zu implementieren
### Nachteile
- Steuerzeichen können in den Nutzdaten auftreten und verwirren
- Latenz deutlich langsamer als bei [[Hardware-Handshake]]
- Unsicherheit bei Verlust
### Steuerzeichen
![[Pasted image 20241210125252.png]]
### State-Diagramm
![[Pasted image 20241213163803.png]]



## ETX/ACK
- ETX: End of text => markiert das Ende eines Datenblocks
- ACK: Acknowledgment => bestätigt den erfolgreichen Empfang des Blocks
- NAK: Negative Acknowledgment => Signalisiert einen Fehler und fordert eine erneute Übertragung
- Hierbei handelt es sich um keinen reinen Software-Handshake, da man sowohl DSR, sowie DTR benötigt
- Paket

### Ablauf
1. Der Sender sendet einen Datenblock und fügt am Ende das ETX- Zeichen(0x03) hinzu
2. Der Empfänger prüft die Daten:
	1. Bei Erfolg: ACK 0x06
	2. Bei Fehler: NAK

### Vorteile 
- Robuste Fehlerkontrolle
- Geeignet für Unzuverlässige Verbindungen(zuverlässig wegen ETX)
- einfach zu implementieren
- kostengünstig

### Nachteile 
- zusätzlicher Aufwand durch Kontrollzeichen
- hohe latenz 

## Sequenzdiagramm ETX/ACK
![[ETX_ACK.bmp]]