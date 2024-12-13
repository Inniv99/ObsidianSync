#Q3 #TW Erstellt am 13.12.2024 um 16:53 Uhr

---

##### Sendebereitschaft mittels RTS-CTS
![[Pasted image 20241213165346.png]]

1. DTE aktiviert RTS
2. DCE antwortet mit CTS
3. die Datenübertragung (DTE zu DCE über TxD) beginnt 
4. DCE ist kurzzeitig nicht in der Lage, Daten zu empfangen(z.B. Buffer voll) und deaktiviert CTS
5. DCE kann wieder Daten annehmen 
6. DTE beendet die Datenübertragung durch die Deaktivierung von RTS
7. Daraufhin deaktiviert DCE CTS und beendet die Datenübertragung 
8. DTE darf erst dann wieder RTS aktivieren wenn CTS ausgeschaltet wurde