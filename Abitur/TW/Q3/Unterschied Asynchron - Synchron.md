#Digitaltechnik #Q3 Erstellt am 13.12.2024 um 16:21 Uhr

---

##### Synchrones Verfahren

Es besteht ein festes Zeitfenster in dem die Binärzeichen eingebettet sind. Sender und Empfänger arbeiten im **gleichen Schritttakt**.

Verlangt wird, dass alle Daten vorher bereits vollständig vorhanden sind.

##### Asynchrones Verfahren

Bei der asynchronen Datenübertragung findet die Informationsübertragung Zeichenweise zu einem beliebigen Zeitpunkt statt.

Es gibt **keine Taktleitung**, die Synchronisation ist durch festgelegte Bitrate, Datenformat und Start- und Stoppbits möglich.

![[Pasted image 20241213164653.png]]

##### Asynchron und Synchron im Vergleich

| Asynchron                                                                                                                                                                                | Synchron                                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| - Robuste und Wirkvolle Methode <br>(Start- und Stoppbit senden)<br><br>- Keine Pufferung, kein Gleichlauf<br>zwischen Sender/Empfänger<br><br>- Geringer Hardwareaufwand, kostengünstig | - Effektiver<br><br>- nur reine Datenübertragung<br>keine Start-/Stoppbits<br><br>- optimale Ausnutzung der Übertragungszeit |
