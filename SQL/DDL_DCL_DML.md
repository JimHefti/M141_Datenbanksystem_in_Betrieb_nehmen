# DDL DCL DML

## DDL - Data Definition Language

Zweck: DDL ermöglicht das Erstellen, Ändern und Löschen von Schemata, Tabellen, Indizes und anderen Datenstrukturen in einer Datenbank.


Hauptbefehle:
CREATE: Zum Erstellen von Datenbankobjekten, wie Tabellen oder Indizes.
ALTER: Zum Modifizieren bestehender Datenbankstrukturen.
DROP: Zum Löschen von Datenstrukturen.
TRUNCATE: Zum schnellen Löschen aller Zeilen in einer Tabelle, ohne die Struktur selbst zu löschen.

## DML - Data Manipulation Language

Zweck: DML befasst sich mit der Manipulation von Daten innerhalb der vorhandenen Strukturen (zum Beispiel Tabellen).
Hauptbefehle:


SELECT: Zum Abfragen und Anzeigen von Daten aus einer Tabelle.
INSERT: Zum Hinzufügen neuer Daten zu einer Tabelle.
UPDATE: Zum Ändern bestehender Daten in einer Tabelle.
DELETE: Zum Entfernen von Daten aus einer Tabelle.


## DCL - Data Control Language

Zweck: DCL wird verwendet, um die Zugriffsrechte und Sicherheitsrichtlinien der Datenbank zu kontrollieren.
Hauptbefehle:
GRANT: Zum Gewähren von Zugriffsrechten und Privilegien an Benutzer.
REVOKE: Zum Entziehen von zuvor gewährten Privilegien.

| Tätigkeit                              | SQL-Befehl                                                             | Grp |
|----------------------------------------|-----------------------------------------------------------------------|-----|
| 1) alle Daten einer Tabelle anzeigen   | `SELECT * FROM <Tabellenname>;`                                       |     |
| 2) Datenbank auswählen                 | `USE <Datenbankname>;`                                                |     |
| 3) eine neue Datenbank erstellen       | `CREATE DATABASE <Datenbankname>;`                                    |     |
| 4) eine neue Tabelle erstellen         | `CREATE TABLE <Tabellenname> (Spalte1 Datentyp, Spalte2 Datentyp, ...);` |     |
| 5) eine Tabelle löschen                | `DROP TABLE <Tabellenname>;`                                         |     |
| 6) Tabellenstruktur kontrollieren      | `DESCRIBE <Tabellenname>;` oder `SHOW COLUMNS FROM <Tabellenname>;`  |     |
| 7) Datenbanken anzeigen                | `SHOW DATABASES;`                                                    |     |
| 8) Tabellen einer DB anzeigen          | `SHOW TABLES;`                                                       |     |
| 9) Daten in eine Tabelle eintragen     | `INSERT INTO <Tabellenname> (Spalte1, Spalte2, ...) VALUES (Wert1, Wert2, ...);` |     |
| 10) Daten in einer Tabelle ändern      | `UPDATE <Tabellenname> SET Spalte1 = Wert1, Spalte2 = Wert2 WHERE Bedingung;` |     |
| 11) Daten in einer Tabelle löschen     | `DELETE FROM <Tabellenname> WHERE Bedingung;`                        |     |
| 12) einen Index löschen                | `DROP INDEX <Indexname> ON <Tabellenname>;`                          |     |
| 13) einen Index erstellen              | `CREATE INDEX <Indexname> ON <Tabellenname> (Spalte);`               |     |
| 14) Spalte in einer Tabelle löschen    | `ALTER TABLE <Tabellenname> DROP COLUMN <Spaltenname>;`              |     |


![alt text](image.png)




