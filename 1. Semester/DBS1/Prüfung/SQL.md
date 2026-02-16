To create a **database**:
```SQL
CREATE DATABASE skigebietverwaltung;
```

To create a **table**:
```SQL
CREATE TABLE Person (
    id SERIAL PRIMARY KEY,
    vorname VARCHAR(50) NOT NULL,
    nachname VARCHAR(50) NOT NULL,
    telefon VARCHAR(20),
    email VARCHAR(100)
);
```

**User/Role management:** `CREATE USER`, `CREATE ROLE`, `GRANT`, `REVOKE`
	**Privilege levels:** `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `ALL`
```SQL
CREATE ROLE clients;
GRANT USAGE ON SCHEMA public TO clients;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO clients;
```
#### Insert Statements
```SQL
INSERT INTO person (id, vorname, nachname) VALUES
	(1, "Helga", "Bücheler");
```

Der Lohn des Verwaltungsmitglieds mit der ID 15 wird um 1'000 CHF erhöht.
```SQL
UPDATE verwaltungsmitglied
SET lohn = lohn + 1000
WHERE id = 15;
```
