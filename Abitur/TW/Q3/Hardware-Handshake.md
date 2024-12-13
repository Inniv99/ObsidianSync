#Q3 #TWErstellt am 11.12.2024 um 19:01 Uhr

---
## Prinzip 
Hardware-Handshakes arbeiten auf physischer Ebene, wie z.B. durch [[RS232]] Schnittstellen. Hierbei werden bestimmte Leitungen gekreuzt miteinander verbunden (siehe [[RS232]]).

### Ready/ Busy-Protokoll
Das Ready/Busy-Protokoll ist die einfachste Form eines Hardware-Handshakes und verwendet lediglich DTR. Ready wird mit logisch 1 (High-Pegel) und Busy mit logisch 0 (Low-Pegel) dargestellt. Ready symbolisiert die Empfangsbereitschaft des DEE/DCE und Busy gibt an, dass dieser beschäftigt ist.
## Ablauf (Bsp. anhand RTS/CTS)
1. Sender aktiviert RTS
2. Empfänger aktiviert CTS
3. Sender beginnt mit der Datenübertragung
4. Wenn der Empfänger nicht mehr bereit ist, deaktiviert er CTS und der Sender pausiert bis CTS wieder aktiviert wird