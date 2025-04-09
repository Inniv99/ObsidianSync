#Digitaltechnik #Q4 Erstellt am 15.03.2025 um 20:52 Uhr

---

`[]` bedeutet Optionaler Parameter
`{}` bedeutet Variablenname

**Tabelle erstellen**

```sql
CREATE TABLE {name} (datenfeld datentyp [DEFAULT standardwert | NULL | NOT NULL] [AUTO_INCREMENT] PRIMARY KEY({datenfeldname}))
```

- `CREATE TABLE` erstellt eine neue Tabelle
- `AUTO INCREMENT` zählt einen Integer Wert automatisch hoch
- `PRIMARY KEY` legt einen [[Primärschlüssel]] fest
- `NULL` bedeutet, dass das Feld keinen Inhalt besitzt
- `NOT NULL` bedeutet, dass das Feld einen Inhalt haben muss

**Umwandlung von Datentypen**

```sql
CAST({wert} AS {Datentyp})
```

Es können folgende Typen ineinander umgewandelt werden: NUMERIC  CHAR, VARCHAR, DATE CHAR, VARCHAR  NUMMERIC, DATE DATE BLOB, TEXT 80  CHAR, VARCHAR, DATE  nicht möglich

Folgende Typen können ineinander umgewandelt werden:
`NUMERIC` $\rightarrow$ `CHAR, VARCHAR, DATE`
`CHAR, VARCHAR` $\rightarrow$ `NUMERIC, DATE`
`DATE` $\rightarrow$ `CHAR, VARCHAR, DATE`
`BLOB, TEXT` $\rightarrow$ nicht möglich

**Constraints**:

Spalten-Constraints z.B. `NOT-NULL` bei Attribut
Tabellen-Constraint z.B. `PRIMARY KEY` als Zugehörigkeit dieser Tabelle

`CONSTRAINT` Anweisung für Gültigkeitsprüfung eines Attributs:

```sql
CREATE TABLE {name} (... CONSTRAINT {name} CHECK({gültigkeitsprüfung}))
```

| Bedingung                             | Erklärung                                                        |
| ------------------------------------- | ---------------------------------------------------------------- |
| `nummer <= zahl`                      | wahr, wenn `nummer` kleiner als `zahl`                           |
| `name NOT LIKE "%A%"`                 | wahr, wenn `name` den Buchstaben `A` nicht enhält                |
| `abteilung IN ("Einkauf", "Verkauf")` | wahr, wenn `abteilung` den Wert `Einkauf` oder `Verkauf` besitzt |

**Tabellen löschen**

```sql
DROP TABLE [IF EXISTS] {name} 
```

**Tabellen anzeigen**

```sql
SHOW TABLES [FROM {datenbankname}] [LIKE "muster"]
```

**Tabellenstruktur ändern**

- Datenfelder hinzufügen oder löschen
- Datenfelder umbenennen
- Datenfelddefinitionen verändern
- Gültigkeitsprüfungen hinzufügen oder löschen
- [[Primärschlüssel]] hinzufügen oder löschen

```sql
ALTER TABLE {name} ADD {attribut} VARCHAR(20) DEFAULT "default";
ALTER TABLE {name} ADD PRIMARY KEY(id); 
ALTER TABLE {name} ADD CONSTRAINT ppruef CHECK (preis > 0); 
ALTER TABLE {name} DROP wert; 
ALTER TABLE {name} RENAME COLUMN anzahl TO stueck;
```