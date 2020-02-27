## ☁️ SQL

⏮ [Zurück zur EFI Übersicht](/efi/)

* [Download DB Browser for SQLite](https://sqlitebrowser.org/dl/)
* [SQL Island](https://sql-island.informatik.uni-kl.de)
* 📺 [Einführungsvideo (Youtube)](https://www.youtube.com/embed/3dWLv8Pxiy4)
* [SQL E.Tutorial](https://frontend-1.et.ethz.ch/sc/4srf2fpLfT37pxBaS)
* [Kahnacademy](https://de.khanacademy.org/computing/computer-programming/sql/sql-basics/v/welcome-to-sql)
* [w3schools](https://www.w3schools.com/sql/)
* [SQL Zoo](https://sqlzoo.net)
* [Terra Datenbank](https://www.sachsen.schule/terra)
* 📺 [SQLite Datenbank mit Tabellen und Einträgen erstellen (Tutorial 1)](https://is.gd/sqlite)

### Tabellen erstellen

#### Zwei Tabellen («Kategorie» & «Inhaltsstoff») mit je einer Inhalts-Spalte («Name») plus je einem Primärschlüssel («Id»)
```sql
CREATE TABLE Kategorie (
	Id INTEGER NOT NULL CHECK(typeof(Id) = 'integer'),
	Name TEXT NOT NULL,
	PRIMARY KEY(Id)
);

CREATE TABLE Inhaltsstoff (
	Id INTEGER NOT NULL CHECK(typeof(Id) = 'integer'),
	Name TEXT NOT NULL,
	PRIMARY KEY(Id)
);

```

#### Mit einer Inhalts-Spalte sowie Primär- und Fremdschlüssel
```sql
CREATE TABLE Lebensmittel (
	Id INTEGER NOT NULL CHECK(typeof(Id) = 'integer'),
	Name TEXT NOT NULL,
	Kategorie_Id INTEGER NOT NULL,
	PRIMARY KEY(Id),
	FOREIGN KEY(Kategorie_Id) REFERENCES Kategorie(Id)
);
```

#### Zwischentabelle mit kombiniertem Primärschlüssel und zwei Fremdschlüsseln 
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

#### Tabelle & alle dazugehörigen Daten entfernen:
```sql
DROP TABLE database_name.table_name;
```

### Daten hinzufügen

#### In zwei Tabellen («Kategorie», «Inhaltsstoff»), je einer Inhaltsspalte («Name») plus je einem Primärschlüssel («Id»)
```sql
INSERT INTO Kategorie (Id, Name) VALUES (1, 'Getränke');
INSERT INTO Kategorie (Id, Name) VALUES (2, 'Früchte und Gemüse');
INSERT INTO Kategorie (Id, Name) VALUES (3, 'Ei und Milchprodukte');
INSERT INTO Kategorie (Id, Name) VALUES (4, 'Getreideprodukte');
INSERT INTO Kategorie (Id, Name) VALUES (5, 'Fleisch und Fisch');
INSERT INTO Kategorie (Id, Name) VALUES (6, 'Süssspeisen');
INSERT INTO Kategorie (Id, Name) VALUES (7, 'anderes');

INSERT INTO Inhaltsstoff (Id, Name) VALUES (1, 'Alkohol (in g)');
INSERT INTO Inhaltsstoff (Id, Name) VALUES (2, 'Beta-Carotin (in mikrog)');
INSERT INTO Inhaltsstoff (Id, Name) VALUES (3, 'Calcium (in mg)');
INSERT INTO Inhaltsstoff (Id, Name) VALUES (4, 'Cholesterin (in mg)');
INSERT INTO Inhaltsstoff (Id, Name) VALUES (5, 'Eisen (in mg)');
```
👉 [Mehr Inhaltsstoffe (inhaltsstoffe.sql)](https://frontend-1.et.ethz.ch/gridfs/fs/hash/7b88561eccaf4706c155cf6328470f13?download=true)

#### In eine Tabelle («Lebensmittel») mit drei Spalten («Id», «Name», «Kategorie_Id»)
```sql
INSERT INTO Lebensmittel (Id, Name, Kategorie_Id) VALUES (1001025, 'Branntwein aus Getreide (z.B. Whisky)', 1);
```
👉 [Mehr Lebensmittel (lebensmittel.sql)](https://frontend-1.et.ethz.ch/gridfs/fs/hash/769d8bd29f8968268497e34cb0d7890d?download=true)

#### In eine Zwischentabelle einfügen
👉 [lebensmittel_inhaltsstoff.sql](https://frontend-1.et.ethz.ch/gridfs/fs/hash/7effa3fd959cfbc2744323439bd62c00?download=true)


### SQL-Abfragen


#### Eine Spalte


```sql
SELECT Name
FROM Lebensmittel
```

#### Mehrere Spalten

```sql
SELECT Id, Name
FROM Lebensmittel
```

#### Alle Spalten

```sql
SELECT *
FROM Lebensmittel
```

#### Mit Filter

```sql
SELECT *
FROM Lebensmittel
WHERE Id = 1000826 OR Id = 1000840;
```

#### Kleiner als & Ordnen
```sql
SELECT *
FROM Lebensmittel
WHERE Id < 1001000
ORDER BY Name DESC;
```

#### Abfrage über zwei verknüpfte Tabellen
```sql
SELECT Lebensmittel.Name, Kategorie.Name
FROM Lebensmittel INNER JOIN Kategorie ON Lebensmittel.Kategorie_Id = Kategorie.Id;
Schliessen
```

#### Komplexere Abfrage
```sql
SELECT Lebensmittel.Name, Kategorie.Name, Lebensmittel.Id
FROM Lebensmittel INNER JOIN Kategorie ON Lebensmittel.Kategorie_Id = Kategorie.Id
WHERE Lebensmittel.Id > 1001000 AND (Kategorie.Name = 'Getränke' OR Kategorie.Name = 'Früchte und Gemüse')
ORDER BY Kategorie.Name ASC, Lebensmittel.Name DESC
```

#### Abfrage über drei Tabellen
```sql
SELECT Lebensmittel.Name, Inhaltsstoff.Name, Lebensmittel_Inhaltsstoff.Menge
FROM Lebensmittel
 INNER JOIN Lebensmittel_Inhaltsstoff ON Lebensmittel.Id = Lebensmittel_Inhaltsstoff.Lebensmittel_Id
 INNER JOIN Inhaltsstoff ON Lebensmittel_Inhaltsstoff.Inhaltsstoff_Id = Inhaltsstoff.Id
WHERE Lebensmittel_Inhaltsstoff.Menge > 10 AND Inhaltsstoff.Name = 'Zucker (in g)'
ORDER BY Lebensmittel_Inhaltsstoff.Menge DESC;
```

### [sqlite3](https://sqlite.org)-Befehle

Programm starten (Windows)
: [sqlite-tools-win32-x86-xxxxxxx.zip herunterladen](https://sqlite.org/download.html) > entzippen > sqlite3.exe öffnen

Programm starten (Mac, Linux, BSD)
: `sqlite3` im [Terminal](https://support.apple.com/guide/terminal/welcome/mac) eingeben

Datenbank (namens «nwdatenbank.db») öffnen/erstellen
: `.open nwdatenbank.db`

Datenbank sichern
: `.save FILEMANE` 

Programm beenden
: `.exit`

Datenbanken anzeigen
: `.databases`

Tabellen anzeigen
: `.tables`