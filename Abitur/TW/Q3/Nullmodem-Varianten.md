#Q3 #TWErstellt am 11.12.2024 um 19:01 Uhr

---

## 1. Standart-Nullmodem-Kabel (ohne [[Handshake]])
- Nur TxD, RxD und GND sind verbunden
- Steuerleitungen (CTS, RTS, DTR, DSR) werden nicht verwendet
- TxD (Pin2) des ersten Geräts ist mit RxD (Pin3) des zweiten Geräts verbunden und umgekehrt
- GND (Pin 5) ist direkt verbunden
 ![[Pasted image 20241213194215.png]]
### Einsatzbereich
- simple serielle Verbindungen, welche kein [[Handshake]] erfordern

## 2. Nullmodem mit Loopback
- RTS(Pin 7), CTS (Pin 8), DTR(Pin 4) und DSR(Pin 6) werden lokal verbunden und nicht direkt zwischen den Geräten
- TxD und RxD, sowie GND werden über die Pins verbunden
![[Pasted image 20241213193441.png]]
### Einsatzbereich
- Geräte die keinen externen [[Handshake]] benötigen

## 3. Nullmodem mit vollständigem [[Handshake]]
- Sowohl Datenleitungen, sowie [[Handshake]]-Signale werden gekreuzt
- alle Pins werden überkreuzt mit ihrem entsprechenden Gegenüber gekreuzt verbunden (TxD mit RxD und andersherum, DTR mit DSR und andersherum, ...)
![[Pasted image 20241213193609.png]]
### Einsatzbereich
- Geräte die [[Handshake]]-Signale benötigen, um den Datenfluss zu regulieren

## 4. Nullmodem mit partieller Handshake-Verbindung
- es werden nur ausgewählte [[Handshake]]-Signale verbunden z.B. nur RTS/CTS
- in dem Bsp. werden DTS/DST ignoriert oder lokal zutückgeführt
- RTS/CTS wird gekreuzt verbunden sowie TxD und RxD und GND direkt
![[Pasted image 20241213193653.png]]
### Einsatzbereich
- Geräte die nur teilweise [[Handshake]]-Signale nutzen

## Zusammenfassung
![[Pasted image 20241210115109.png]]
