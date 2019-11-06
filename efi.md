# EFI

## Computer/Daten

* [Werbeplakate am Zürich HB](https://www.tagesanzeiger.ch/zuerich/stadt/swisscom-lueftet-geheimnis-um-schwarze-boxen-am-hb-zuerich/story/29988994)
* [geschwindigkeit.ch](https://www.geschwindigkeit.ch/)
* [speedtest.net](https://www.speedtest.net/)

* [digitec.ch](https://www.digitec.ch/)
* [pcpartpicker.com](https://pcpartpicker.com/)
* [newegg.com](https://www.newegg.com/)

* [Apollo 11: A Space Odyssey (YouTube)](https://www.youtube.com/watch?v=yDm5RVzUlGk)
* [Apollo 11: Mit 1 MHz zum Mond (Artikel)](https://www.pctipp.ch/news/gesellschaft/artikel/apollo-11-mit-1-mhz-zum-mond-80567/)

* [brainfaqk Erklärvideso (YouTube)](https://www.youtube.com/playlist?list=PL6DU7YsYvRpA31RgBg1MUTf2EuVtmAF-E&app=desktop)
* [WikiBook über Computerhardware](https://de.m.wikibooks.org/wiki/Computerhardware_f%C3%BCr_Anf%C3%A4nger)
* [Artikel über Moore's Law](https://www.spiegel.de/netzwelt/web/moore-s-law-die-goldene-regel-der-chiphersteller-broeckelt-a-1083468.html)

* [ifixit.com](https://www.ifixit.com)


## Binärsystem

* [Uhr oder keine Uhr?](http://abenteuer-informatik.de/bu.html)
* [Binary Hand Dance](https://www.youtube.com/watch?v=OCYZTg3jahU)
* [ASCII (Wikipedia)](https://de.wikipedia.org/wiki/American_Standard_Code_for_Information_Interchange)
* [Unicode Charts](https://www.unicode.org/charts/)

* [Umrechner Dezimal- in Binärzahlen (Scratch)](https://scratch.mit.edu/projects/227035991/)
* [Tutorial von OrangeOnBlack (Youtube)](https://www.youtube.com/watch?v=vRgNi2zqUgA)
* [Binary Numbers Game](https://games.penjee.com/binary-numbers-game/)
* [Binary Bonanza](https://games.penjee.com/binary-bonanza/)
* [The Binary Game](https://studio.code.org/projects/applab/iukLbcDnzqgoxuu810unLw)

* [WolframAlpha](https://www.wolframalpha.com/); Beispielabfragen:
    * where am I?
    * generate password
    * password strength 123456
    * 255 in binary
    * 16 in hex



## SQL
* [Handysektor erklärt: Was ist eigentlich die Cloud?](https://www.youtube.com/watch?v=VhqSH8HPioU)
* [Download DB Browser for SQLite](https://sqlitebrowser.org/dl/)
* [SQL Island](https://sql-island.informatik.uni-kl.de)
* [Einführungsvideo (Youtube)](https://www.youtube.com/embed/3dWLv8Pxiy4)
* [SQL E.Tutorial](https://frontend-1.et.ethz.ch/sc/4srf2fpLfT37pxBaS)
* [Kahnacademy](https://de.khanacademy.org/computing/computer-programming/sql/sql-basics/v/welcome-to-sql)
* [w3schools](https://www.w3schools.com/sql/)
* [SQL Zoo](https://sqlzoo.net)
* [Terra Datenbank](https://www.sachsen.schule/terra)

## Tabellen erstellen

### Mit einer Inhalts-Spalte plus Primärschlüssel
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
