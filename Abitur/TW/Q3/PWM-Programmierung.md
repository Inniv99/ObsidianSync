#Q3 #TWErstellt am 11.12.2024 um 19:02 Uhr

---

A wird verglichen, modi (00 = nix, 01 (1) down, 10 (2) up, 11 (3) Tastgrad auf 50 => Mittelposition d.h. zur Hälfte an, zur Hälfte aus. P1.7 auf 1 setzen, PWM aktiv A auf Tastgrad ein, solange schleife abwarten 10 mikrosekunden bis 0,5ms voll, dann mit A = 100 - Z Tastgrad aus wartezeit berechnen bis 0,5ms, d.h. bei linksdrehung 1ms warten. Mit UP/DOWN Methode Tastgrad anpassen, immer um 1 höher, wenn Tastgrad EIN nicht schon bei 100%

für Initialisierung bsp PinB0, und 1 als Ausgänge setzten
out DDRB, 0b11111100 // Pins 0/1 als ausgänge setzen
out PORTB, 0b00000011 // mit pull-up


Bsp. Code
; Register-Definitionen
.def duty_cycle = r16 ; Register für den Duty Cycle (0–100)
.def temp = r17        ; Temporäres Register

; I/O-Definitionen
.equ PWM_PIN = PB6     ; PB6 als LED-Ausgang
.equ MODE_PIN1 = PB0   ; PB0 als Modus-Eingang 1
.equ MODE_PIN2 = PB1   ; PB1 als Modus-Eingang 2

; Initialisierung
INIT:
    ldi temp, (1<<PWM_PIN) ; Setze PB6 als Ausgang
    out DDRB, temp         ; Schreibe in DDRB (PB6 = Ausgang)

    ldi temp, 0            ; PB0 und PB1 als Eingänge
    out DDRB, temp         ; Schreibe in DDRB (PB0, PB1 = Eingang)

    ldi temp, (1<<MODE_PIN1) | (1<<MODE_PIN2) ; Pull-Up aktivieren
    out PORTB, temp        ; Schreibe in PORTB (PB0, PB1 mit Pull-Up)

    ldi duty_cycle, 0      ; Initialisiere Duty Cycle mit 0% (LED aus)

; Hauptprogramm
MAIN:
    in temp, PINB          ; Modus-Pins einlesen
    andi temp, 0x03        ; Isoliere PB0 und PB1
    cp temp, 0x00
    breq MODE_OFF          ; Modus 00: LED aus
    cp temp, 0x01
    breq MODE_LOW          ; Modus 01: Helligkeit verringern
    cp temp, 0x02
    breq MODE_HIGH         ; Modus 10: Helligkeit erhöhen
    cp temp, 0x03
    breq MODE_RESET        ; Modus 11: Duty Cycle auf 50%
    rjmp MAIN              ; Unbekannter Modus: Zurück zur Schleife

; Modus 00: LED aus (Duty Cycle = 0%)
MODE_OFF:
    ldi duty_cycle, 0      ; Setze Duty Cycle auf 0%
    rjmp MAIN

; Modus 01: Helligkeit verringern
MODE_LOW:
    cpi duty_cycle, 0      ; Ist Duty Cycle bereits 0%?
    breq MAIN              ; Wenn ja, zurück zur Hauptschleife
    dec duty_cycle         ; Duty Cycle um 1% verringern
    rcall DELAY            ; Warte 10 ms
    rjmp MAIN

; Modus 10: Helligkeit erhöhen
MODE_HIGH:
    cpi duty_cycle, 100    ; Ist Duty Cycle bereits 100%?
    breq MAIN              ; Wenn ja, zurück zur Hauptschleife
    inc duty_cycle         ; Duty Cycle um 1% erhöhen
    rcall DELAY            ; Warte 10 ms
    rjmp MAIN

; Modus 11: Duty Cycle auf 50% zurücksetzen
MODE_RESET:
    ldi duty_cycle, 50     ; Setze Duty Cycle auf 50%
    rjmp MAIN

; PWM-Routine
PWM_LOOP:
    ldi temp, 100          ; Lade Vergleichswert (100 Schritte)
PWM_HIGH_LOOP:
    cpi temp, duty_cycle   ; Ist aktueller Schritt kleiner als Duty Cycle?
    brlo LED_ON            ; Wenn ja, LED an
    rjmp LED_OFF           ; Andernfalls LED aus

LED_ON:
    sbi PORTB, PWM_PIN     ; Setze PWM_PIN (LED an)
    rjmp PWM_END

LED_OFF:
    cbi PORTB, PWM_PIN     ; Lösche PWM_PIN (LED aus)

PWM_END:
    dec temp               ; Reduziere Schrittzähler
    brne PWM_HIGH_LOOP     ; Wiederhole, bis Schrittzähler 0 ist
    rjmp MAIN              ; Zurück zur Hauptschleife

; 10-ms-Warteschleife
DELAY:
    ldi temp, 250
DELAY_LOOP1:
    ldi r18, 250
DELAY_LOOP2:
    dec r18
    brne DELAY_LOOP2
    dec temp
    brne DELAY_LOOP1
    ret


Aufgabe:
Aufgabe: PWM-Programmierung für einen ATmega2560 Mikrocontroller
Problemstellung:
Programmieren Sie einen ATmega2560 Mikrocontroller, um die Helligkeit einer LED über PWM zu steuern. Verwenden Sie dafür den Pin PB6 als PWM-Ausgang und die Pins PB0 und PB1 als Modus-Eingänge.

PB6 (PWM_PIN) soll eine LED ansteuern.
PB0 und PB1 (MODE_PIN1 und MODE_PIN2) bestimmen den Betriebsmodus:
Modus 00 (LED AUS): Die LED bleibt ausgeschaltet (Duty Cycle = 0%).
Modus 01 (Helligkeit verringern): Der Duty Cycle wird kontinuierlich verringert, bis die LED aus ist (min = 0%).
Modus 10 (Helligkeit erhöhen): Der Duty Cycle wird kontinuierlich erhöht, bis die LED voll leuchtet (max = 100%).
Modus 11 (Reset): Der Duty Cycle wird auf 50% zurückgesetzt, und die LED leuchtet mit halber Helligkeit.
Das Programm soll in einer Schleife laufen und kontinuierlich auf Änderungen der Modi reagieren.

Anforderungen:
Initialisieren Sie den Port PB6 als Ausgang und die Ports PB0 und PB1 als Eingänge.
Verwenden Sie ein Register (z. B. r16), um den Duty Cycle zu speichern.
Implementieren Sie die Funktionalität für alle vier Modi:
Modus 00: Duty Cycle = 0%.
Modus 01: Duty Cycle verringern.
Modus 10: Duty Cycle erhöhen.
Modus 11: Duty Cycle auf 50% zurücksetzen.
Implementieren Sie eine PWM-Routine, bei der die LED entsprechend des Duty Cycles ein- und ausgeschaltet wird.
Hinweise:
Verwenden Sie den Takt des ATmega2560 und Timer-Interrupts für die PWM-Generierung (falls erforderlich).
Fügen Sie eine Wartezeit von 10 ms in die UP- und DOWN-Routinen ein, um die Geschwindigkeit der Helligkeitsänderung zu steuern.
Verwenden Sie ähnliche Struktur wie in der gegebenen Aufgabe: mit Labels für MAIN, UP, DOWN, ON, OFF, und so weiter.


