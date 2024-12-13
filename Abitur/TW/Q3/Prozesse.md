### Erklärung
Prozesse sind Programme, welche aus folgenden Komponenten bestehen:
- Dem auszuführenden Code
- Dem statischen Speicher, welcher den Heap, sowie alle Variablen welche mit static und extern deklariert wurden
- Dem Stack, welcher alle dynamischen Variablen (lokal deklarierte Variablen, Zwischenergebnisse von Rechnungen, etc) speichert
- Dem Registersatz, welcher den **program counter** (zeigt die nächste Anweisung im Programm) und den **stack pointer** enthält

Prozesse laufen sequentiell ab und Jeder hat seinen eigenen Adressenraum, sowie seine eigenen Daten auf die dieser zugreifen und welche er verändern kann. [[Threading]] verändert das Prozess Model.
Ein Prozess kann mehrere Threads enthalten.