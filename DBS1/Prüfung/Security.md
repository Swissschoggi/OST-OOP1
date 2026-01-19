Database Security geht eigentlich nur um Zugriffsrechte: wer darf was.

#### SQL-Injection
SQL Injection: Angreifer erstellt SQL-Kommandos oder verändert existierende, um versteckte Daten sichtbar zu machen, Daten zu überschreiben, oder auf Systemebene des Datenbank-Hosts  zu gelangen.
Anstelle Username ein String ' OR true --
```SQL
select * from accounts where username='' AND password='';
select * from accounts where username='' OR true –-' AND password=$2;
```

#### Benutzerverwaltung

Syntax:
```SQL
CREATE ROLE user_name
WITH LOGIN PASSWORD 'password';
```
Role ist der Oberbegriff für Benutzer (USER) oder Gruppe (GROUP)
Man kann eine Role mit oder ohne Login erstellen.

Beispiel:
```SQL
-- a) Create database
CREATE DATABASE skigebietverwaltung;

-- b) Create group with read permissions
CREATE ROLE clients;
GRANT USAGE ON SCHEMA public TO clients;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO clients;

-- c) Revoke public permissions
REVOKE ALL ON SCHEMA public FROM public;

-- d) Create user in group
CREATE USER webclient WITH PASSWORD 'S0c1a1_D1sT4nC3';
GRANT clients TO webclient;

-- e) Can webclient create tables? NO
-- Reason: Only SELECT privilege, no CREATE TABLE permission

-- f) Drop the user --> Löscht alle Objekte die clients als owner hat
DROP ROLE clients;
```

Ein Passwort ändern:
`ALTER ROLE user WITH PASSWORD 'password';`

##### System-Privilegien

| Permission                  | Description                                                     |
| --------------------------- | --------------------------------------------------------------- |
| `CREATEDB`                  | Erlaubt dem Benutzer Datenbanken auf Server zu erstellen        |
| `CREATEROLE`                | Erlaubt der/m Rolle/Benutzer neue Rollen/Benutzer zu erstellen. |
| `NOCREATEDB`/`NOCREATEROLE` | sind Negationen davon                                           |

##### Objekt-Privilegien

| Permission   | Description                                                                                                                                     |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `SELECT`     | Der Benutzer darf die Daten der Tabelle oder Sicht einsehen                                                                                     |
| `INSERT`     | Der Benutzer darf Sachen einfügen                                                                                                               |
| `UPDATE`     | Falls keine Kolonnen angegeben sind, darf der<br>Benutzer alle Werte eines Tupels ändern, andernfalls nur<br>die Werte der angegebenen Kolonnen |
| `DELETE`     | Der Benutzer darf Sachen löschen                                                                                                                |
| `REFERENCES` | Der Benutzer darf Schlüssel definieren                                                                                                          |
| `TRIGGER`    | Der Benutzer darf die stored Procedure aufrufen                                                                                                 |
| `ALL`        | Der Benutzer erhält alle Privilegien                                                                                                            |
#### Revoke
```SQL
REVOKE permission
ON object
FROM user/group
```
