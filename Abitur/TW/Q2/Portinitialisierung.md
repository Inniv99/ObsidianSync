Erstellt am 14.04.2025 um 18:59 Uhr

---
Hat man einen _Port_ und möchte diesen dementsprechend initialisieren, so geht man wie folgt vor:
Ein einzelner Pin soll Ein- oder Ausgang werden
 ``sbi DDRA, 0`` PinA0 wird zum Ausgang, weil wir an der Stelle eine 1 setzen
 ``cbi DDRB, 0`` PinA0 wird zum Eingang, weil wir an der Stelle eine 0 setzen
 Möchte man mehrere Bits auf einmal setzen, z.B. wie folgt: 
 ![[Pasted image 20250423170945.png]]
 Dann kann man dies auch so umsetzen:
 ```asmatmel
 ldi r16, 0b01111111
 out DDRA, r16
 ldi r16, 0b00000000
 out DDRB, r16
```
Port 1 entspricht hier Port A
Port 2 entspricht Port B