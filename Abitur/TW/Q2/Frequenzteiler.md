Erstellt am 03.05.2025 um 10:15 Uhr

---
Zum Aufbau von Frequenzteilern bieten sich Flankengesteuerte T-FlipFlops an, welche den Invertierten Ausgang des vorherigen FF´s erhalten.

![[Pasted image 20250503101824.png]]
Die Bit-Stufe des Frequenzteilers, ist das Teilverhältnis hier gilt ==> 8:1

Frequenzteiler funktionieren aber auch mit Synchron angesteuerten Flip Flops:
![[Pasted image 20250503102904.png]]

Das Zeitablaufdiagramm sieht so aus:
![[Pasted image 20250503102122.png]]

Man berechnet die Frequenz mit folgender Formel:
$$ 
f_T = \frac{f_E}{2^n}
$$
$f_E$ = Eingangsfrequenz
$f_T$ = geteilte Frequenz
$n$ = Anzahl der Flip Flops
