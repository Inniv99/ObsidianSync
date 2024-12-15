#Q3 #TW Erstellt am 14.12.2024 um 12:58 Uhr

---
``` asmatmel 

.def z = r20
.def acc = r21

INIT:
 ldi acc, 0xFF
 out DDRB, 0b11111100
 sbi DDRB, 0b00000011
 ldi z, 50
 cbi PORTB7
MAIN:
 in acc, PINB
 andi acc, 0b00000011
 cpi acc, 0
 breq LOS
 cpi acc, 1
 breq DIR_DOWN
 cpi acc, 2
 breq DIR_UP
 cpi acc, 3
 breq RESET

RESET:
 ldi z, 0

DIR_UP:
 rcall UP
 rjmp LOS

DIR_DOWN:
 rcall DOWN
 rjmp LOS

LOS: 
 sbi PORTB, 7
 rcall Wait1ms

ON:
 mov acc, z
 cpi acc, 0
 breq ON_END

ON_LOOP:
 sbi PORTB, 7
 rcall Wait10us
 dec acc
 cpi acc, 0
 brne ON_LOOP

ON_END:

OFF:
 ldi acc, 100
 sub acc, z
 cpi acc, 0
 breq OFF_END

OFF_LOOP:
 cbi PORTB, 7
 rcall Wait10us
 dec acc
 cpi acc, 0
 brne OFF_LOOP


OFF_END:
 cbi PORTB7 
 rcall Wait18ms
 rjmp MAIN

UP:
 cpi z, 100
 brne INC
 ret

INC:
 inc z
 rcall Wait100ms
 rjmp UP

DOWN:
 cpi z, 0
 brne DEC
 ret

DEC:
 dec z
 rcall Wait100ms
 ret
 
``` 