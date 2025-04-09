#Digitaltechnik #Q4 Erstellt am 15.03.2025 um 20:48 Uhr

---

`[]` bedeutet Optionaler Parameter
`{}` bedeutet Variablenname

**Datenbank erstellen**

```sql
CREATE DATABASE [IF NOT EXISTS] {name};
```

- Name maximal 64 Zeichen

**Datenbank anzeigen**: 

```SQL
SHOW DATABASES;
SHOW DATABASE {name};
```

**Datenbank auswählen**:

```sql
USE DATABASE {name};
```

Eine Datenbank muss erst ausgewählt werden, bevor diese verwendet werden kann z.B. um [[RDBM-Relation|Relationen]] einzufügen.

**Datenbank löschen**:

```sql
DROP DATABASE [IF EXISTS] {name}
```
