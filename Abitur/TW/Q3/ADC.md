#Q3 #TW Erstellt am 11.12.2024 um 18:56 Uhr

--- 
## Prinzip eines ADC 

Analog-Digital-Wandler sind das Gegenteil eines [[DAC]]s. Sie wandeln kontinuierliche Spannungswerte U in eine Binärzahl D(U) um. D(U) gibt an wie oft ein Spannungsintervall in U enthalten ist.
Dabei gibt es drei Schritte:
1. Sampling: Das analoge Signal wird periodisch abgetastet 
2. Quantisierung: Der abgetastete Wert wird in ein diskretes Intervall eingeordnet
3. Kodierung: Das quantisierte Intervall wird in ein digitales Binärformat übersetzt 
Die Übersetzung hängt hierbei von der Referenzspannung und der Auflösung des ADC ab.
Ein ADC hat verschiedene [[ADC-Verfahren]].

## Kenngrößen von ADC

*Bitanzahl*: diese bestimmen die auflösung des ADC. Ein n-Bit-ADC kann 2^n
Werte darstellen
*Auflösung*: sie gibt die kleinstmögliche Spannungsänderung, bzw. die Abstände der einzelnen Bits an => Uref/ 2^n
*Wandlungszeit*: Die zeit die der ADC benötigt, um ein Signal zu digitalisieren 
*Sample und Hold Stufe*: die Stufe die das analoge Signal, während der Digitalisierung konstant hält.
*Sample Rate*: Die Zeit die der ADC zum "abtasten benötigt", meistens im Datenblatt enthalten


## Arten von ADC

### Flash-ADC
Mehrere Komparatoren vergleichen Uin mit abgestuften Referenzspannungen. Sollte Uin > Uref sein liefert der Komparator ein Low signal, sonst ein High. Der Wert an dem ein Low gesendet wurde, wird dann Digitalisiert.

Vorteil: extrem schnell
Nachteil: hoher Hardware aufwand
### Staircase-Ramp
Eins steigendes Spannungssignal (Ramp), wird mit Uin verglichen. Der Zähler stoppt dann, wenn Ramp und Uin übereinstimmen.

Vorteil: Simpel
Nachteile: Langsam
### Wäageverfahren ( Sukzessive Approximation)
Ein [[DAC]] erzeugt Spannung, welche schrittweise mit Uin verglichen werden, wodurch sich der [[ADC]] langsam dem Eingabewert nähert.

Vorteil: Guter kompromiss zwischen Geschwindigkeit und Genauigkeit
Nachteil: Komplexer als ein Ramp-Verfahren
### Integrationsverfahren ( Rampenverfahren)
- Single-Slope: Die Integrationszeit einer ansteigenden Spannung wird gemessen
- Dual-Slope: Die Zeit, welche für das Auf- und Entladen eines Kondensators benötigt wird, wird gemessen

Vorteile: Sehr genau, tolerant gegenüber rauschen
Nachteile: Langsam

## Wandlungsfehler

### Gain-Error/ Verstärkungsfehler
Steigung ist nicht eins variiert ganz leicht
### Offset-Error/ Nullpunktfehler
Nullpunktfehler: Nullpunkt nicht gesetzt
### Lineaaritätsfehler
Steigung bleibt nicht linear
### Wandlungsfehler 
Widerstände an Schaltern sind nicht null


## Wandlungsfehler graphisch

![[Pasted image 20241211230941.png]]
## Beispielhafte Rechnung eines [[ADC]] mit 4 bits


![[Pasted image 20241209172804.png]]
