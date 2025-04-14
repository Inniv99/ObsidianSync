Erstellt am 14.04.2025 um 18:48 Uhr

---
Das _Data-Direction-Register_(kurz DDR) legt fest, ob an einem PIN ein Eingang oder Ausgang vorliegt. Dabei bedeutet eine logische 0, dass es ein Eingang ist und logisch 1, dass es ein Ausgang ist.

```
ldi r16, 0b00000001
out DDRB, r16
```
In diesem Beispiel, wurde das 0. Bit auf 1 gesetzt und die restlichen auf 0, sodass PINB 0 ein Ausgang und PINB 1-7 Eingänge sind.
