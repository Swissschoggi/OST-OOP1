#### 1. Normalform
Eine Tabelle ist in ersten Normalform (1. NF), falls die Wertebereiche der Attribute atomar (Jedes Feld genau einen Wert) sind.
**nicht 1.NF:**

| id  | produkte             |
| --- | -------------------- |
| 1   | Produkt A, Produkt B |
| 2   | Produkt C            |
	
**1.NF:**

| id  | produkte  |
| --- | --------- |
| 1   | Produkt A |
| 2   | Produkt B |
| 3   | Produkt C |

#### 2. Normalform
Eine Tabelle ist in der 1 Normalform wenn jeder Attribut voll vom [Primary-Key](Keys#Primary-Key) Abhängig ist.
