Erstellt am 17.04.2025 um 10:25 Uhr

---
Möchte man ein Bitmuster in ein [[Schieberegister]] hineinladen, passiert das Ganze Seriell, d.h. Bit für Bit nacheinander. Wenn alle Bits eingeladen wurden, kann man mit dem Modi _Parallel_ Laden, alle eingeschobenen Bits gleichzeitig ins Ausgaberegister hineinladen. 

Für _Seriell zu Parallel_ [[Schieberegister]] gilt:
Bei n Stufen kann nach n Takten der Datenstrom am Ausgang n wieder _Seriell_ abgegriffen werden. Also bei 4bit kann nach vier Takten am Ausgang Q4 der Datenstrom abgelesen werden.

Für _Parallel zu Seriell_ [[Schieberegister]] gilt:
Nach jedem Takt wird ein Bit ausgelesen und ist somit nach jedem Takt abgreifbar