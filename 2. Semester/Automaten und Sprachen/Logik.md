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

Induktionsbeweis:
Prinzip:
	- verankerung: $P(0)$
	- Annahme: $P(n)$
	- Induktionsschritt: $P(n+1)$

Behauptung:
	$P(n): \sum_{k=1}^n k={n(n+1)\over 2}$
	1. $1$ einsetzen.
	2. Formel korrekt für n
	3. Beweis für n+1 (n+1 einsetzen)

**Aufgabe**
$\sum_{k=1}^n k²={n(n+1)(2n+1)\over 6}$
1. $n=1$
 ${1(1+1)(2*1+1)\over 6} = {2*3\over 6}= 1$
2. stimmt
3. $n+1$ einzetzen
${(n+1)*((n+1)+1)(2(n+1)+1)\over 6}$ $= {(n²+2n+1+n+1)*(2n+3)\over 6}$ 


Aussage A = $n³+5$ ungerade $,n \in N$ dann ist $n$ gerade.
$\neg A =$ $n$ ist ungerade
$n³ +5$ ist gerade wenn $n$ ungerade $\implies$ wiederspruch also ist die Aussage bewiesen.

#### Alphabet und Wort
**Alphabet**
Eine nichtleere Menge $\sum$ heisst Alphabet. Die Elemente von $\sum$ heissen Zeichen.
**Wort**
Eine Zeichenkette der Länge $n$ ist ein n-Tupel in $\sum{n}=\sum \times ... \times \sum$. Ein Element von $\sum{n}$ heisst Wort der länge $n$.
$(A, u, t, o, S, p, r) = AutoSpr$
$a^3b^5 = aaabbbbb$
$b^5a^3 = bbbbbaaa$

Immer $\epsilon$ das **Leere Wort** beachten.
**Aufgabe**
	$\sum =$ {$0,1$} in $\sum{*}$ 
	$\sum{*}=\epsilon,0,1,00,11,01,10...$ 

**Wortlänge**
- $|\epsilon| = 0$
- $|01010|_0 =3$
- $|01010|_1=2$
- $|01010|_2=0$

**Aufgabe**
$L= (w \in \sum{*} ||w|_0 =2)$
$\sum{*} = (00,001,010,100,0011...)$

**Eine Teilmenge $L \subset \sum{*}$ heisst Sprache.**

M eine “Maschine”: $L(M) = {w \in \sum{*} | \text{w wird von M akzeptiert}}$
Zu jeder Maschine M gibt es eine Sprache $L(M)$
	