#### Primary-Key
- Ein einzelner Schlüssel pro Tabelle, er ist eindeutig.
- Möglichst kurz `NUMBER(10)`

Create a Primary-Key on the ID column when Persons table is created:
```SQL
CREATE TABLE Persons (  
    ID int NOT NULL,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int,  
    PRIMARY KEY (ID)  
);
```

Man kann auch alternate Keys haben die man mit `UNIQUE` instanziert.

#### Foreign-Key
Ein Foreign key referenziert einen Primary Key
```SQL
ALTER TABLE table
ADD FOREIGN KEY (foreign key column) REFERENCES (primary key column)
```
