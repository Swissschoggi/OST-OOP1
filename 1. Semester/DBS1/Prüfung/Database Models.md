#### Hierarchisches Modell
```mermaid
graph TD
    A[Unternehmen] --> B[Abteilung A]
	B --> Mitarbeiter1
	B --> Mitarbeiter2
	A --> C[Abteilung B]
	C --> Mitarbeiter3
```
JSON, XML
#### Netzwerk Modell
```mermaid
graph TD
    A[Unternehmen] --> B[Abteilung A]
	B --> Mitarbeiter1
	B --> Mitarbeiter2
	A --> C[Abteilung B]
	B --> Mitarbeiter3
	C --> Mitarbeiter3
```
Graph-DBMS
#### Relationales Modell

| Number | Name   | City       | Nationality | Age |
| ------ | ------ | ---------- | ----------- | --- |
| 1      | Silas  | Rapperswil | CH          | 20  |
| 2      | Jannik | Zürich     | CH          | 21  |
| 3      | Fynn   | Wettswil   | CHI         | 20  |
| 4      | Dylan  | Männedorf  | USA         | 23  |
| 5      | Sara   | Zürich     | CH          | 22  |

#### Objektrelationales Model
```mermaid
classDiagram
    class Unternehmen {
        +int UnternehmenID
        +string Name
        +date Gründungsdatum
        +addAbteilung()
    }
    
    class Abteilung {
        +int AbteilungID
        +string Name
        +int UnternehmenID
    }
    
    class Mitarbeiter {
        +int MitarbeiterID
        +string Vorname
        +string Nachname
        +string Position
    }
    
    Unternehmen "1" --* "many" Abteilung : contains
    Abteilung "many" -- "many" Mitarbeiter : employs
```
