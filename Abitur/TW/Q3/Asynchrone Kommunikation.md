#Q3 #TW 

Erstellt am 11.12.2024 um 18:58 Uhr

---
## Prinzip
Bei der asynchronen Kommunikation gibt es keinen gemeinsamen Takt zwischen Sender und Empfänger. Die Synchronisation erfolgt durch das Startbit.

1. Der Empfänger erkennt die Änderung des Pegels von High(Idle) zu Low durch das Senden des Startbits, wodurch er anfängt Daten zu lesen.
2. Empfänger liest die Daten basierend auf der Baudrate
3. Ein Stopbit wird gesendet und der Empfänger erkennt den nächsten Frame


