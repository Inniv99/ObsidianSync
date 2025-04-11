Erstellt am 11.04.2025 um 11:38 Uhr

---
Das _NAND-Gatter_ besteht aus einem *AND* und einem *NOT* und hat zwei oder mehr Eingänge mit einem Ausgang. Sollten alle Eingänge den Wert 1 haben, so kommt am Ausgang eine 0, sonst immer eine 1.

![[Pasted image 20250411114636.png]]Wenn man einen Term in der [[DNF]] hat kann man diesen in eine NAND-NF umwandeln. Dafür benutzt man das [[De Morgansches Theorem]] und es funktioniert auch mit der [[KNF]]. 

Die Umwandlung von [[DNF]] zu _NAND-NF_ sähe folgendermaßen aus:
![[Pasted image 20250411120116.png]]Und die Umwandlung von [[KNF]] zu _NAND-NF_ so:
![[Pasted image 20250411121244.png]]
Bei dieser Umwandlung muss man jedoch beachten, dass man zwei mal das [[De Morgansches Theorem]] anwendet und ein extra _NAND-Gatter_ hinzufügt.