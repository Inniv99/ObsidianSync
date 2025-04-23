Erstellt am 23.04.2025 um 16:55 Uhr

---
Ein Schieberegister besteht aus _synchron_ geschalteten JK Flip Flops, für welche J = Q und K = Q¬ gilt, außer für das erste Flip Flop.
![[Pasted image 20250423165808.png]]
Schieberegister benutzen nur die _Set_ und _Reset_ Funktion der FF´s, daher gilt wenn J = 1 K = 0 und J = 0 K  = 1.
Wird zB. das Bitmuster 1101 eingelesen kommt es als 1011 wieder heraus
Die Ausgänge sind retardiert, wodurch Data In auf die fallende Flanke des Taktes reagiert.