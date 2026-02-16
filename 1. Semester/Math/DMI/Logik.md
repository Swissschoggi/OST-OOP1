**Aussage:**
Ein Satz der etwas feststellt, eindeutiger Wahrheitssatz (wahr/falsch)

**A:** Rapperswil liegt am Bodensee.
		ist eine falsche Aussage

**B:** $5 \leq 10$ 
		ist eine wahre Aussage.

**C:** Regnet es?
		ist keine Aussage, kein w/f


Aussagen bekommen Buchstaben:
	A: Die Sonne Scheint.
	B: Es regnet.
	C: Der Bus fährt.

Aussagenlogische Formeln verknüpfen Aussagen durch Junktoren (connectors).
	- Negation --> mit Aussage Negatives aussagen $\neg$ 
		$\neg A: \text{Die Sonne scheint nicht.}$
	- Verknüpfung/Konjunktion/"und" --> $\land$ 
		$A\land B : \text{Die Sonne Scheint UND der Bus fährt}$
	- Disjunktion/"oder" --> $\lor$
		$A\lor B : \text{Die Sonne scheint ODER es regnet}$
	- Implikation --> $\implies$
		$A\implies B : \text {Wenn A wahr, dann ist auch B wahr}$
	- Äquivalenz --> $\iff$
		$A\iff B \text{A ist genau und nur dann wahr wenn B wahr ist}$

#### Wahrheitstabelle

| $A$ | $B$ | $A\land B$ | $\neg A$ | $(A\land B) \lor (\neg A)$ |
| --- | --- | ---------- | -------- | -------------------------- |
| w   | w   | w          | f        | w                          |
| w   | f   | f          | f        | f                          |
| f   | w   | f          | w        | w                          |
| f   | f   | f          | w        | w                          |
$2^\text{Anzahl Aussagen}$ 

##### Für Junktoren
	Negation

| $A$ | $\neg A$ | $\neg \neg A$ |
| --- | -------- | ------------- |
| w   | f        | w             |
| f   | w        | f             |
Spalten sind identisch -->      $A \iff \neg \neg A$
						$\iff \neg(\neg A)$
	
	
	Konjunktion

| $A$ | $B$ | $A \land B$ | $B \land A$ |
| --- | --- | ----------- | ----------- |
| w   | w   | w           | w           |
| w   | f   | f           | f           |
| f   | w   | f           | f           |
| f   | f   | f           | f           |
$A \land B \iff B \land A$ --> Kommutativ-Gesetz

	Disjunktion

| $A$ | $B$ | $A\lor B$ | $B\lor A$ |
| --- | --- | --------- | --------- |
| w   | w   | w         | w         |
| w   | f   | w         | w         |
| f   | w   | w         | w         |
| f   | f   | f         | f         |
$A \lor B \iff B \lor A$
Spezialfälle:
	$A \land (\neg A)$ --> Immer falsch --> **Kontradiktion**
	$A \lor (\neg A)$ --> immer wahr  --> **Tantalogie**

	Implikation

| $A$ | $B$ | $A\implies B$ |
| --- | --- | ------------- |
| w   | w   | w             |
| w   | f   | f             |
| f   | w   | w             |
| f   | f   | w             |
1. $A \implies B$ : Wenn A wahr, B wahr
2. $B \implies A$ : Wenn B falsch, dann A falsch
		$(A\implies B) \iff (\neg B \implies \neg A)$

##### **Ausdruck der Implikation mit $\neg$,$\land$,$\lor$ 

| $A$ | $B$ | $A \implies B$ | $\neg A$ | $\neg A \lor B$ |
| --- | --- | -------------- | -------- | --------------- |
| w   | w   | w              | f        | w               |
| w   | f   | f              | f        | f               |
| f   | w   | w              | w        | w               |
| f   | f   | w              | w        | w               |
$(A \implies B) \iff (\neg A \lor B)$

#### Bindestärken und Rechenwege
Prioritäten:
1. $\neg$
2. $\lor$,$\land$
3. $\implies$,$\iff$

$$
\underbrace{
\Big(
\underbrace{
(A \land B) \lor (\underbrace{\neg C}_{\text{1}} \land A)
}_{\text{2}}
\Big)
\implies
(D \lor C)
}_{\text{3}}
$$
Distributivität:
$A \land (B \lor C) = (A \land B) \lor (A \land C)$ 

Absorbtion:
$A \lor (A \land B )\iff A \lor (A \land B) \iff A$

De Morgan:
$\neg(A\land B)\iff\neg A \lor \neg B$
$\neg(A\lor B)\iff\neg A \lor \neg B$ 

| $A$ | $B$ | $A\land B$ | $\neg(A \land B)$ | $\neg A$ | $\neg B$ | $\neg A \lor \neg B$ |
| --- | --- | ---------- | ----------------- | -------- | -------- | -------------------- |
| w   | w   | w          | f                 | f        | f        | f                    |
| w   | f   | f          | w                 | f        | w        | w                    |
| f   | w   | f          | w                 | w        | f        | w                    |
| f   | f   | f          | w                 | w        | w        | w                    |
