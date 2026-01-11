#### Externe Ebene
Ist was der Enduser sieht, sprich die Berechtigungen die er hat um in der Datenbank Daten zu sehen.

#### Konzeptionelle Ebene
Ist der Zusammenhang zwischen Realwelt und Datanbank, wird in ER-Modell dargestellt.

#### Interne Ebene



```mermaid
graph TD
    subgraph Externe Ebene
        A[App 1]
        B[App 2]
        C[App 3]
        D[App n]
        E1[Externes Schema 1]
	    E2[Externes Schema 2]
	    En[Externes Schema n]
    end
    
    subgraph Konzeptionelle Ebene
        K[Konzeptionelles Schema]
        DA[Datenbankschema]
    end
    
    subgraph Interne Ebene
        P[Physische Datenstruktur]
    end
    A --> E1
    B --> E1
    C --> E2
    D --> En
    E1 --> K
    E2 --> K
    En --> K
    K --> DA
    DA --> P

```
