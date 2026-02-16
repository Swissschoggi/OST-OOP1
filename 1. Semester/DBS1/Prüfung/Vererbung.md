### Variante 1
 **Je eine Tabelle pro Sub- und Superklasse mit jeweils einem Primärschlüssel der den Primärschlüssel der Superklasse Referenziert.**
Für jede Spezialisierung von Informatiker wird eine Klasse eingeführt (Primärschlüssel =
Primärschlüssel der Superklasse-Tabelle), welche jeweils eine Rolle beschreibt, die ein Informatiker einnehmen kann. Da ein Informatiker z.B. gleichzeitig SW-Engineer oder QS-Spezialist sein kann, entfällt hier das diskriminierende Attribut. Beim Zugriff auf die Daten eines Informatikers müssen daher alle Tabellen durchsucht werden.
```
Operator(PersNr, OperQual,...)
SWEngineer(PersNr, PS, ...)
QSSpezialist(PersNr, QSQual,...)
```
Die Daten eines bestimmten Operators sind also auf drei Tabellen aufgeteilt: In der Tabelle 'Angestellter' finden sich die allgemeinen Angaben, in der Tabelle 'Informatiker' die Angaben die spezifisch für Informatiker sind und schliesslich sind in der Tabelle 'Operator' die Angaben, die spezifisch für einen Operator sind.

### Variante 2
