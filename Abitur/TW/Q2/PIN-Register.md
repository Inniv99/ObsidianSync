Erstellt am 14.04.2025 um 18:54 Uhr

---
Das _PIN-Register_ hängt immer mit einem Port zusammen (A,B,C...) und kann die Zustände an einem Eingangs PIN einlesen. Es steht also direkt in Verbindung mit den physischen Komponenten.
Wenn man den Zustand an einem PIN ablesen möchte, so sähe das folgendermaßen aus:
```amsatmel
in r16, PINB ; liest alle Eingänge von PORT B ein
```
Möchte man aber schauen wie an einem bestimmten PIN der Zustand ist so kann man entweder ausmaskieren oder man benutzt befehle wie `sbi`, welche nur einzelne Bits ansprechen.
```
in r16, PINB // alle Pins in Register einlesen
andi r16, 0b00000011 // alle Bits die nicht 1 sind ausmaskieren
 oder 
sbi PINB, 0
sbi PINB, 1
```
