#Digitaltechnik #Q4 Erstellt am 15.03.2025 um 20:53 Uhr

---

**Umsetzung einer 1:1 Beziehung**

ABITURIENTEN(<u>ID</u>, Vorname, Name, Adresse) 
ABITUR(Deutsch, Englisch, Mathematik)

![[Pasted image 20250315214623.png]]

Eine 1:1 Beziehung lässt sich als eine Relation implementieren:
`ABITURIENTEN(ID, Vorname, Name, Adresse, Deutsch, Englisch, Mathematik)`

**Umsetzung einer 1:c Beziehung**

MITARBEITER(<u>ID</u>, Vorname, Name, Adresse) 
ABTEILUNG(<u>ID</u>, Bezeichnung)

![[Pasted image 20250315214727.png]]

Entitätsklasse wird für die Kardinalität `[1,1]` wird genauso überführt.
Entitätskasse für die Kardinalität `[0,1]` erhält zu ihren Attributen einen **Fremdschlüssel** der anderen Entitätsklasse.

`MITARBEITER(ID,Vorname, Name, Adresse)`
`ABTEILUNG(ID, Bezeichnung, MITARBEITER_ID#)`

**Umsetzung einer 1:m Beziehung**

ABTEILUNG(<u>ID</u>, Bezeichnung) 
MITARBEITER(<u>ID</u>, Vorname, Name, Adresse)

![[Pasted image 20250315215603.png]]

Entitätsklasse wird für die Kardinalität `[1,1]` wird genauso überführt.
Entitätsklasse mit Kardinalität `[1,*]` bekommt einen **Fremdschlüssel** der anderen Entitätsklasse.

`ABTEILUNG(ID, Bezeichnung)`
`MITARBEITER(ID, Vorname, Name, Adresse, ABTEILUNG_ID#)`

**Umsetzung einer 1:mc Beziehung**

PAAR(ID, Name, Adresse) 
KIND(ID, Vorname, Name, Geburtstag)

![[Pasted image 20250315215915.png]]

Die Umsetzung erfolgt analog zur 1:c-Beziehung

`PAAR(ID, Name, Adresse)`
`KIND(ID, Vorname, Name, Geburtstag, PAAR_ID#)`

**Umsetzung einer n:m Beziehung**

AUTOR(<u>ID</u>, Vorname, Name)
BUCH(<u>ID</u>, Titel, ISBN, Preis

![[Pasted image 20250315220002.png]]

`n:m`-Beziehung in einer Beziehungstabelle abgebildet, in der Fremdschlüssel für jede Zuordnung von Tupeln der beteiligten Relationen angelegt werden.

`AUTOR(ID, Vorname, Name)
`BUCH(ID, Titel, ISBN, Preis)` 
`AUTOR_BUCH(AUTOR_ID#, BUCH_ID#)`
