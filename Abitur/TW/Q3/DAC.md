Erstellt am 11.12.2024 um 19:01 Uhr

---
## Prinzip:
Ein Digital to Analogue Converter (DAC) wandelt digitale Signale (Bits), in analoge Ausgaben, wie z.B. in Volt um. Ein Bit kann den Wert 1 oder 0 annehmen, wodurch die Ausgangsspannung berechnet werden kann.
Dabei wird eine [[R2R-Ladder]] verwendet 


## Berechnung $U_{out}$  
Die Ausgangsspannung Uout, lässt sich folgendermaßen berechnen:
Uout = Uref * D/2^n 

Uref = Referenzspannung
D = Dezimalwert des Bitmusters
n = Anzahl der bits des DAC
Bei dieser Rechnung benutzt man das Superpositionsprinzip, bei welchem die Beiträge der Bits einzeln betrachtet werden und dann zusammen addiert werden.



#TW #Q3