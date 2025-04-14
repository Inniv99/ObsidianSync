Erstellt am 14.04.2025 um 18:54 Uhr

---
Das _PIN-Register_ hängt immer mit einem Port zusammen (A,B,C...) und kann die Zustände an einem Eingangs PIN einlesen. Es steht also direkt in Verbindung mit den physischen Komponenten.
Wenn man den Zustand an einem PIN ablesen möchte, so sähe das folgendermaßen aus:
```
in r16, PINB ; liest alle Eingänge von PORT B ein
in r16, PINB2 ; liest nur den 2. Pin des Ports eins
```