#### Inner Joins
Ein Inner Join zeigt nur erfolgreiche matches an.
Wenn man nun drei Tabellen hat und die Ausgabe soll etwas anzeigen dass nur mithilfe der Informationen von allen drei machbar ist:

**Element**

| <u>Element_Symbol<u/> | Element_Name |
| --------------------- | ------------ |
| H                     | Hydrogen     |
| C                     | Carbon       |
| N                     | Nitrogen     |
| O                     | Oxygen       |
| Na                    | Sodium       |
| Cl                    | Chlorine     |
| He                    | Helium       |
|                       |              |

**Compound**

| <u>Compound_ID<u/> | Compound_Name    |
| ------------------ | ---------------- |
| 100                | Water            |
| 101                | Carbon Dioxide   |
| 102                | Ammonia          |
| 103                | Table Salt       |
| 104                | Mystery Compound |

**Compound_Element_Details**

| <u>Compound_ID<u/> | Element_Symbol | Number_Of_Atoms |
| ------------------ | -------------- | --------------- |
| 100                | H              | 2               |
| 100                | O              | 1               |
| 101                | C              | 1               |
| 101                | O              | 2               |
| 102                | N              | 1               |
| 102                | H              | 3               |
| 103                | Na             | 1               |
| 103                | Cl             | 1               |
| 104                | Q              | 2               |
| 104                | X              | 1               |
now if we want a Join that only shows Compounds where Hydrogen is used, we use the following query:
```SQL
SELECT
	c.Compound_ID,
	c.Compound_Name
FROM
	Compound_Element_Details ced --ced from now on refers to this table
INNER JOIN
	Compound c
ON
	ced.Compound_ID = c.Compound_ID --Join c and ced Compound_ID
INNER JOIN
	Element e
ON
	ced.Element_Symbol = e.Element_Symbol --Join ced and e Element_Symbol
where
	e.Element_Name = "Hydrogen"
```
This outputs:

| Compound_ID | Compound_Name |
| ----------- | ------------- |
| 100         | Water         |
| 102         | Ammonia       |

#### Left Outer Join
Left Outer Join shows all attributes that have not been successfully matched, it does this by looking at the left side of the JOIN query:
```SQL
SELECT
	e.Element_Symbol,
	e.Element_Name,
	ced.Compound_ID,
	ced.Number_Of_Atoms
FROM
	Element e
LEFT OUTER JOIN
	Compound_Element_Details ced
ON
	e.Element_Symbol = ced.Element_Symbol --Left Outer Join looks at the left side of the =
```

#### Right Outer Join
Right Outer Join does the same as Left Outer Join just on the right side:
```SQL
SELECT
	e.Element_Symbol,
	e.Element_Name,
	ced.Compound_ID,
	ced.Number_Of_Atoms
FROM
	Compound_Element_Details ced
LEFT OUTER JOIN
	Element e
ON
	ced.Element_Symbol = e.Element_Symbol --Right Outer Join looks at the right side of the =
```

#### Full Outer Join
Does basically Left and Right Join together

