Erstellt am 18.04.2025 um 11:54 Uhr

---
Das Status Register enthält Informationen über das Ergebnis der zuletzt ausgeführten Operation und diese kann genutzt werden um den Programm-Fluss zu beeinflussen. Das Status Register wird nach jeder [[Funktionsweise der ALU|ALU-Operation]]geupdated. Dadurch spart man sich viele Vergleiche, wodurch der code kompakter und schneller wird. Das SREG speichert nicht automatisch wenn es in eine Interrupt Routine geht und stellt die Daten auch nicht wieder her, das muss die Software übernehmen.