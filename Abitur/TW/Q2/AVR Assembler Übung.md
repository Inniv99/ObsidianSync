Erstellt am 22.04.2025 um 19:59 Uhr

---
Aufgabe 3.3 Abitur 2020 Vorschlag B
```asmatmel
.def count = r20

INIT: 
ldi r16, 0b11111000
out DDRB, r16
ldi count,0x1001

MAIN:
sbic PB,0
rjmp MAIN
sbic PB,1
rjmp MAIN
sbis PB,2
RCALL DREHEN

DREHEN:

ldi r18, 0b10010000
out PORTB, r18
ldi r18, 0b01010000
out PORTB, r18
ldi r18, 0b01100000
out PORTB, r18
ldi r18, 0b10100000
out PORTB, r18

sbi PB,3
ret
```