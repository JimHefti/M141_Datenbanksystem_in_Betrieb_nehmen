# Tabellentypen und Transaktionen


1.  Wie bezeichnet man die Ausführung mehrerer DB-Operationen in einem einzigen Schritt?

    - [ ] Referentielle Integrität

    - [ ] Replikation

    - [ ] Transaktion

    - [ ] Storage Procedure

2.  Warum sollen Locks möglichst schnell freigegeben werden?

    - [ ] damit das DBMS nicht zu stark belastet wird

    - [ ] damit andere DB-Anwender nicht lange warten müssen

    - [ ] damit niemand die Daten ändern kann

    - [ ] damit möglichst viele Benutzer gleichzeitig auf die DB zugreifen können

3.  Welches ist das Standard-Tabellenformat von MySQL (MariaDB)?

    - [ ] InnoDB

    - [ ] MyISAM

    - [ ] ARIA

    - [ ] ISAM

4.  Wann verwenden Sie das InnoDB-Tabellenformat?

    - [ ] wenn möglichst schnell auf die Daten zugegriffen werden muss

    - [ ] wenn auf gar keinen Fall ein Datenverlust vorkommen darf

    - [ ] wenn viele Benutzer gleichzeitig Daten ändern

    - [ ] wenn bei sehr vielen Daten nicht beliebig viel Speicherplatz vorhanden ist

5.  Was trifft auf den sog. Tablespace zu?

    - [ ] Datei, welche die Daten der entsprechenden Tabelle enthält (\*.MYD)

    - [ ] Datei, welche Beschreibung, Daten und Indexe einer Tabelle enthält

    - [ ] Datei, welche alle InnoDB-Tabellen enthält (virtueller Speicher)

    - [ ] wird nach Erreichen von x MB automatisch vergrössert (falls autoextend eingeschaltet)
    
6.  Mit welchen Befehlen werden Transaktionen gesteuert?

    - [ ] UNLOCK TABLES;

    - [ ] COMMIT; oder ROLLBACK;

    - [ ] ALTER TABLE ... TYPE= ...;

    - [ ] BEGIN; oder START TRANSACTION;

7.  Was trifft auf das Locking bei Transaktionen auf InnoDB-Tabellen zu?

    - [ ] in Transaktionen kommt Table locking zur Anwendung

    - [ ] es wird Row locking angewendet

    - [ ] es werden alle Datensätze der entsprechenden Tabelle(n) gesperrt

    - [ ] es werden nur die gerade bearbeiteten Datensätze gesperrt

8.  Welches sind Vorteile der InnoDB-Tabellen gegenüber MyISAM-Tabellen?

    ___   n
      

9.  In welchen Dateien wird die MyISAM-Tabelle KUNDEN gespeichert?

    ___   
      

10.  Notieren Sie den SQL-Befehl, der die InnoDB-Tabelle BESTELLUNGEN erstellt.

    ___   
      

11.  Welche Locking-Art ist a) bei MyISAM-Tabellen b) bei InnoDB-Tabellen möglich?

    ___   
      

12.  Beschreiben Sie den Begriff Datenbank-Transaktion!

    ___   
      

13.  Beschreiben Sie die Bedeutung von I in der Abkürzung ACID.

    ___   
      

14.  Wie stellen Transaktionen bei einem DB-Server-Crash die Datenkonsistenz sicher? (Schwierig)

    ___   
  
15. Mit welcher Locking-Art wartet ein SELECT-Befehl, bis alle Transaktionen auf die angeforderte Tabelle entsperrt sind? 

    ___   
          
16. Wie muss Autocommit gesetzt werden, damit jeder SQL-Befehl zu einer Transaktion gehört und damit explizit mit COMMIT abgeschlossen werden muss, damit er ausgeführt wird? 

    ___   
          