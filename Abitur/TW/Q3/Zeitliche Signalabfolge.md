#Q3 #TW Erstellt am 11.12.2024 um 19:04 Uhr

---
## Elemente der zeitlichen Signalabfolge
1.1 Startbit
- Wird zu Beginn jedes Daten-Frames gesendet um den Empfänger zu synch.
- Immer logisch 0 und festgelegte Dauer (Bitzeit)
- Signalisiert dem Empfänger, dass die Datenübertragung beginnt
1.2 Datenbits
- Daten werden Bit für Bit übertragen
- Anzahl der Bits wird festgelegt z.B. 8
- Es geht von LSB zu MSB
- Jedes Bit hat eine konstante Dauer, welche durch die Baudrate bestimmt wird
1.3 [[Parität]]sbit
- Nicht zwingend notwendig
- Dient zur Fehlererkennung
1.4 Stopbit(s)
- Symbolisiert das Ende eines Daten-Frames
- besteht aus 1, 1,5 oder 2 1-Bits
- Empfänger verwendet dieses um sich auf den nächsten Frame vorzubereiten
## Zeitliche Struktur eines Frames
![[Pasted image 20241210122306.png]]
Bsp. siehe [[RS232]]

## Synchronisation
Die Zeitliche Signalabfolge unterscheidet sich dann noch in der [[Asynchrone Kommunikation]] und der [[Synchrone Kommunikation]]. ([[Unterschied Asynchron - Synchron]])