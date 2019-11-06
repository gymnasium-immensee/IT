# SQL

## Tabellen erstellen

### Mit einer Inhalts-Spalte plus Primärschlüssel
```sql
CREATE TABLE "Kategorie" (
	"Id" INTEGER NOT NULL CHECK(typeof("Id") = 'integer'),
	"Name" TEXT NOT NULL,
	PRIMARY KEY("Id")
);

CREATE TABLE Inhaltsstoff (
	Id INTEGER NOT NULL CHECK(typeof(Id) = 'integer'),
	Name TEXT NOT NULL,
	PRIMARY KEY(Id)
);

```

### Mit einer Inhalts-Spalte sowie Primär- und Fremdschlüssel
```sql
CREATE TABLE Lebensmittel (
	Id INTEGER NOT NULL CHECK(typeof(Id) = 'integer'),
	Name TEXT NOT NULL,
    Kategorie_Id INTEGER NOT NULL,
	PRIMARY KEY(Id)
    FOREIGN KEY(Kategorie_Id) REFERENCES Kategorie(Id)
);
```


### Mit kombiniertem Primärschlüssel und zwei Fremdschlüsseln 
```sql
CREATE TABLE Lebensmittel_Inhaltsstoff (
Lebensmittel_Id INTEGER NOT NULL,
Inhaltsstoff_Id INTEGER NOT NULL,
Menge REAL NOT NULL,
PRIMARY KEY(Lebensmittel_Id, Inhaltsstoff_Id),
FOREIGN KEY(Lebensmittel_Id) REFERENCES Lebensmittel(Id),
FOREIGN KEY(Inhaltsstoff_Id) REFERENCES Inhaltsstoff(Id)
);
```


### Tabelle & alle dazugehörigen Daten entfernen:
```sql
DROP TABLE database_name.table_name;
```

## Daten hinzufügen

### Bei einer Inhaltsspalte plus Primärschlüssel
```sql
INSERT INTO Kategorie (Id, Name) VALUES (1, 'Getränke');
INSERT INTO Kategorie (Id, Name) VALUES (2, 'Früchte und Gemüse');
INSERT INTO Kategorie (Id, Name) VALUES (3, 'Ei und Milchprodukte');
INSERT INTO Kategorie (Id, Name) VALUES (4, 'Getreideprodukte');
INSERT INTO Kategorie (Id, Name) VALUES (5, 'Fleisch und Fisch');
INSERT INTO Kategorie (Id, Name) VALUES (6, 'Süssspeisen');
INSERT INTO Kategorie (Id, Name) VALUES (7, 'anderes');
```


## SQL-Abfragen
Eine Spalte
: `SELECT Name
FROM Lebensmittel`

Mehrere Spalten
: `SELECT Id, Name
FROM Lebensmittel`

Alle Spalten
: `SELECT *
FROM Lebensmittel`

Mit Filter
: `SELECT *
FROM Lebensmittel
WHERE Id = 1000826 OR Id = 1000840;`

Kleiner als & Ordnen
: `SELECT *
FROM Lebensmittel
WHERE Id < 1001000
ORDER BY Name DESC;`

## sqlite3-Befehle
Datenbank öffnen/erstellen
: `.open nwdatenbank.db`

Datenbank sichern
: `.save FILEMANE` 

Programm beenden
: `.exit`

Datenbanken anzeigen
: `.databases`

Tabellen anzeigen
: `.tables`
