# SQL

## SQL
Tabelle erstellen inkl. Primär- und Fremdschlüssel
: `CREATE TABLE "Lebensmittel" (
	"Id"	INTEGER CHECK(typeof(Id) = 'integer'),
	"Name"	TEXT NOT NULL,
    "Kategorie_Id" INTEGER NOT NULL,
	PRIMARY KEY("Id")
    FOREIGN KEY("Kategorie_Id") REFERENCES Kategorie("Id")
);`

Tabelle mit kombiniertem Primärschlüssel erstellen
: `CREATE TABLE Lebensmittel_Inhaltsstoff (
Lebensmittel_Id INTEGER NOT NULL,
Inhaltsstoff_Id INTEGER NOT NULL,
Menge REAL NOT NULL,
PRIMARY KEY(Lebensmittel_Id, Inhaltsstoff_Id),
FOREIGN KEY(Lebensmittel_Id) REFERENCES Lebensmittel(Id),
FOREIGN KEY(Inhaltsstoff_Id) REFERENCES Inhaltsstoff(Id)
);`


Tabelle & alle dazugehörigen Daten entfernen:
: `DROP TABLE database_name.table_name;`  

Daten hinzufügen
: `INSERT INTO Inhaltsstoff (Id, Name) VALUES (1, 'Alkohol (in g)');`

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
