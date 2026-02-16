### Grundlagen
##### Prüfung
1m² Zusammenfassung = 16 Seiten A4
##### Aufgaben
[Aufgaben auf Github](https://github.com/AndreasFMueller/AutoSpr)

----
These: **Computer sind abstrakte mathematische Objekte.**

--> Was heisst *wahr* in der Mathematik?
	Definition:
	Ein Beweis ist in der Mathematik die als fehlerfrei anerkannte Herleitung der Richtigkeit bzw. der Unrichtigkeit einer Aussage aus einer menge von Axiomen, die als wahr vorausgesetzt werden, und anderen Aussagen, die bereits bewiesen sind.
	
- Ein Beweis erklärt, warum eine Aussage wahr ist.
- Ein als korrekt erkannter Algorithmus ist ebenfalls ein Beweis.

#### Logik
**Prädikate**
- Aussagen über mathematische Objekte, könne wahr oder Falsch sein.
- "Funktionen" mit boolschen Rückgabewerten.
- $P$ , $Q(n)$ --> Prädikat von n abhängig,  $R(x, y, z)$ Prädikat von $x,y \text{ und } z$ abhängig. 
**Verknüpfungen**
- UND: $P \land Q$
- ODER: $P \lor Q$
- NICHT: $\neg P$
- Implikation: $P \implies Q = \neg P \lor Q$
**Distributivgesetze**
$P \land (Q \lor R) = (P \land Q)\lor (P\land R)$
**De Morgan**
$\neg (P\land Q) = \neg P \lor \neg Q$
Negation und Implikation:
$P \implies Q = \neg Q \implies \neg P$
Kontraposition

**Formeln vergleichen**
Normalformen:
$φ = ((x \land y ) \lor z) \land t$
in die Konjunktive oder Disjunktive Normalform bringen:
konjunktive Normalform:
1. Distributivgesetz
	$(x\lor z) \land (y \lor z)$
2. $t$ auf die zwei anwenden.
Lösung: $((x\lor z) \land (y \lor z)) \land t$
Disjunktive Normalform:

**Wieso?**
Erster Schritt für einen vergleichsalgorithmus.

**UND - Verknüpfung**
$n$ Prädikate $P_i$
$P_i$ ist wahr für alle $i = 1,...,n$
$\forall i \in {1,...,n}(P_i)$ für alle $i$ ist $P_i$  wahr
All-Quantor $\forall$ 
Existenz-Quantor $\exists$ 

**Mengen**
- Zeichenmengen: {$a,b,c,d,...,z$}, {$0,...,9$}
**Aufgabe**
Schreiben Sie die folgenden, in aufzählender Form gegebenen Mengen mit Hilfe eines
Prädikates.
a) A = {1, 3, 5, 7, 9, . . . }
$A =$ {$2n + 1 | n \in N$}
b) B = {1, 4, 7, 10, 13, 16, . . . }
$B =$ {$n \in N | n \equiv 1\mod 3$}
c) C = {10, 11, . . . , 99, 1000, 1001, . . . , 9999, 100000, 100001, . . . }
$C =$ {$}
A = {Objekt | Prädikat}

**XOR**
$\Delta$ Symmetrische Differenz

**Paare**
A, B Mengen, Menge aller Paare:
	$A \times B =$ {$(a,b) | a \in A \land b \in B$} 

**Beweis**
- Wenn $a, b, c \in R$ und $a > 0$ dann hat $ax² + bx + c = 0$ zwei verschiedene Lösungen.
- $\sqrt {2} \notin Q$ 
- $\sum_{k=1}^n k={n(n+1)\over 2}$

- Konstruktiver Beweis: liefert eine explizite Lösung
- Wiederspruchsbeweis: besonders geeignet für Unmöglichkeitsaussagen
- Vollständige Induktion: Für aussagen die für alle $n \in N$ gelten

$ax² + bx +c = 0$
$a \neq 0$ und $b^2 − 4ac > 0$
$x² + 2{b\over 2a}x + {b²\over 4a²}-{b²\over 4a²}+ {c\over a}=0$
$x² + 2{b\over 2a}x + {b²\over 4a²} = {b²-4ac\over 4a²}$
$(x+{b\over 2a}²)={b²-4ac\over 4a²}$ 
$x= {-b\over 2a} + \sqrt{{b²-4ac\over 4a²}}$ 

