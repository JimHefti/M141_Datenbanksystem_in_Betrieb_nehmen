# Tabellentypen und Transaktionen


1.  Wie bezeichnet man die Ausführung mehrerer DB-Operationen in einem einzigen Schritt?



    

    - [ ] Transaktion

    

2.  Warum sollen Locks möglichst schnell freigegeben werden?

  

    - [ ] damit andere DB-Anwender nicht lange warten müssen

    

    

3.  Welches ist das Standard-Tabellenformat von MySQL (MariaDB)?

    - [ ] InnoDB

    

4.  Wann verwenden Sie das InnoDB-Tabellenformat?

   

    - [ ] wenn auf gar keinen Fall ein Datenverlust vorkommen darf

    - [ ] wenn viele Benutzer gleichzeitig Daten ändern

   

5.  Was trifft auf den sog. Tablespace zu?

   

    - [ ] Datei, welche alle InnoDB-Tabellen enthält (virtueller Speicher)

    - [ ] wird nach Erreichen von x MB automatisch vergrössert (falls autoextend eingeschaltet)
    
6.  Mit welchen Befehlen werden Transaktionen gesteuert?

    

    - [ ] COMMIT; oder ROLLBACK;

    

    - [ ] BEGIN; oder START TRANSACTION;

7.  Was trifft auf das Locking bei Transaktionen auf InnoDB-Tabellen zu?


    - [ ] es wird Row locking angewendet

 
    - [ ] es werden nur die gerade bearbeiteten Datensätze gesperrt

8.  Welches sind Vorteile der InnoDB-Tabellen gegenüber MyISAM-Tabellen?

Unterstützung für ACID-konforme Transaktionen: InnoDB unterstützt Transaktionen, die den ACID-Prinzipien (Atomarität, Konsistenz, Isolation, Dauerhaftigkeit) folgen. Das sorgt für zuverlässige Datenverarbeitung und ermöglicht sicheres Rollback bei Fehlern sowie Commit von Datenänderungen.

Row-Level Locking: Im Gegensatz zu MyISAM, das nur Table-Level Locking anbietet, unterstützt InnoDB Row-Level Locking. Dies minimiert die Wahrscheinlichkeit von Konflikten und Sperren bei simultanen Datenzugriffen, was InnoDB für Multi-User-Umgebungen effizienter macht.

Wiederherstellung nach einem Absturz: InnoDB verfügt über integrierte Mechanismen zur Wiederherstellung nach Abstürzen. Durch das Schreiben in ein Log-File (Redo Log) können Transaktionen nach einem Systemfehler wiederhergestellt werden, was die Datenintegrität wesentlich erhöht.

Unterstützung für Fremdschlüssel: InnoDB unterstützt Fremdschlüsselbeziehungen direkt, was die referentielle Integrität erleichtert und die Implementierung von komplexen Datenbeziehungen in Datenbanken vereinfacht.

Automatische Defragmentierung: InnoDB führt eine fortlaufende Optimierung der Daten auf der Festplatte durch, um die Datenfragmentierung zu verringern. Das hilft, die Leistung im Laufe der Zeit zu erhalten und verbessert die Geschwindigkeit der Datenzugriffe.

Mehr Speicheroptionen für große Datenbanken: InnoDB unterstützt sehr große Datenbankgrößen im Vergleich zu MyISAM. Es kann Datenbanken im Terabyte-Bereich handhaben, was es für große Anwendungen und Datenmengen ideal macht. 
      

9.  In welchen Dateien wird die MyISAM-Tabelle KUNDEN gespeichert?

.frm-Datei: Enthält die Definition der Tabellenstruktur. Für die Tabelle KUNDEN wäre das die Datei KUNDEN.frm.

.MYD-Datei (MYData): Hier werden die eigentlichen Daten der Tabelle gespeichert. Für die KUNDEN-Tabelle wäre das die Datei KUNDEN.MYD.

.MYI-Datei (MYIndex): Diese Datei enthält die Indizes der Tabelle. Für die KUNDEN-Tabelle wäre das die Datei KUNDEN.MYI.
    
      

10.  Notieren Sie den SQL-Befehl, der die InnoDB-Tabelle BESTELLUNGEN erstellt.
```sql
CREATE TABLE BESTELLUNGEN (
    BestellID INT AUTO_INCREMENT PRIMARY KEY,
    KundeID INT,
    ProduktID INT,
    Menge INT,
    Bestelldatum DATE,
    Lieferdatum DATE,
    Status VARCHAR(50),
    Gesamtpreis DECIMAL(10, 2),
    FOREIGN KEY (KundeID) REFERENCES KUNDEN(KundeID),
    FOREIGN KEY (ProduktID) REFERENCES PRODUKTE(ProduktID)
) ENGINE=InnoDB;
```
      

11.  Welche Locking-Art ist a) bei MyISAM-Tabellen b) bei InnoDB-Tabellen möglich?

a) MyISAM-Tabellen:

Nutzen ausschließlich Table-Level Locking, bei dem die gesamte Tabelle für die Dauer einer Operation gesperrt wird.

b) InnoDB-Tabellen:

Verwenden Row-Level Locking, wobei nur die direkt betroffenen Datensätze gesperrt werden.
Können auch Table Locks einsetzen, allerdings ist Row-Level Locking die bevorzugte Methode.
      

12.  Beschreiben Sie den Begriff Datenbank-Transaktion!

    Eine Datenbank-Transaktion ist eine Gruppe von Aktionen, die zusammen in einer Datenbank ausgeführt werden. Sie funktioniert nach dem Prinzip „alles oder nichts“: Entweder werden alle Aktionen erfolgreich durchgeführt und gespeichert, oder es wird so getan, als wäre nichts passiert, wenn ein Fehler auftritt. Das hilft, die Daten genau und sicher zu halten.
      

13.  Beschreiben Sie die Bedeutung von I in der Abkürzung ACID.

    Das „I“ in der Abkürzung ACID, die für die Prinzipien von Datenbanktransaktionen steht, bezieht sich auf Isolation. Die Isolation stellt sicher, dass die Änderungen, die innerhalb einer einzelnen Transaktion gemacht werden, für andere gleichzeitig laufende Transaktionen unsichtbar sind, bis die Transaktion vollständig abgeschlossen ist. Dies verhindert, dass Transaktionen, die zur gleichen Zeit durchgeführt werden, sich gegenseitig beeinflussen und möglicherweise inkonsistente Daten erzeugen. Isolation trägt dazu bei, die Datenintegrität in einer Datenbankumgebung mit vielen gleichzeitigen Benutzern zu wahren.
      

14.  Wie stellen Transaktionen bei einem DB-Server-Crash die Datenkonsistenz sicher? (Schwierig)

Write-Ahead Logging (WAL): Änderungen werden zuerst in ein Log-File geschrieben, bevor sie in der Datenbank durchgeführt werden. Dieses Log hilft, die Datenbank nach einem Crash wiederherzustellen.

Checkpointing: Die Datenbank erstellt regelmäßige Checkpoints im Log, die angeben, bis zu welchem Punkt Änderungen sicher gespeichert wurden. Das beschleunigt die Wiederherstellung nach einem Absturz.

Atomicity: Stellt sicher, dass eine Transaktion komplett ausgeführt wird oder im Fehlerfall keine Änderungen übernimmt. Nach einem Crash werden unvollständige Transaktionen rückgängig gemacht.
  
15. Mit welcher Locking-Art wartet ein SELECT-Befehl, bis alle Transaktionen auf die angeforderte Tabelle entsperrt sind? 

    Ein normaler SELECT-Befehl in Datenbanken wartet nicht auf die Freigabe von Sperren und liest Daten, ohne andere Transaktionen zu blockieren. Wenn jedoch eine konsistente Ansicht nötig ist, kann der Befehl mit LOCK IN SHARE MODE oder FOR SHARE in MySQL ausgeführt werden, um einen Shared Lock zu setzen, der dann das Warten auf die Freigabe aller relevanten Sperren beinhaltet. 
          
16. Wie muss Autocommit gesetzt werden, damit jeder SQL-Befehl zu einer Transaktion gehört und damit explizit mit COMMIT abgeschlossen werden muss, damit er ausgeführt wird? 

    Um zu erreichen, dass jeder SQL-Befehl explizit mit COMMIT abgeschlossen werden muss, setzen Sie Autocommit auf OFF. Dies bewirkt, dass Änderungen nicht automatisch in die Datenbank übernommen werden.
          