#Digitaltechnik #Q4 Erstellt am 15.03.2025 um 19:09 Uhr

---

Ein **Fremdschlüssel** ist ein Attribut, welches eine **Beziehung** zu einem Schlüsselfeld einer anderen [[RDBM-Relation]] herstellt.

Kennzeichnung durch:
- Abkürzung "FK"
- Nachgestelltes "#"

##### Beispiel

Aufträge(<u>Auftragsnummer</u>, Datum, ...weitere Attribute, Kundennummer #)

In jedem Tupel in der Relation Aufträge befindet sich eine Kundennummer des Kunden, der den Auftrag ausgelöst hat.