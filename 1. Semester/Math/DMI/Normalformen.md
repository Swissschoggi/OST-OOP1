1. **Negationsformel**: $\neg$ --> steht ausschliesslich direkt vor aussagen
			$(\neg A \land B) \lor \neg C$ ist negations-NF
			$\neg(A\land B)\lor\neg C$ keine negations-NF
			$\neg A \land \neg B \lor \neg C$ ist Negations-NF --> erhält man durch anwenden der Regel De Morgan

2. **Disjunktive Normalform**: $\lor$ --> von verallgemeinerten Konjunktion ($\land$)
			$(A_{11} \land A_{12} \land\text{...}\land A_{1n1})\lor(A_{21}\land A_{22}\land\text{...}\land A_{2n2})\lor\text{...}$ 

3. **Konjunktive Normalform**: $\land$ --> von verallgemeinerten Disjunktionen
			$(A_{11} \lor A_{12} \lor\text{...}\lor A_{1n1})\land(A_{21}\lor A_{22}\lor\text{...}\lor A_{2n2})\land\text{...}$ 

**Beispiel:**
$D=((A\land B)\lor C)\land\neg A$ 

| $A$ | $B$ | $C$ | $A\land B$ | $((A \land B)\lor C)$ | $D=((A\land B)\lor C)\land\neg A$ |
| --- | --- | --- | ---------- | --------------------- | --------------------------------- |
| w   | w   | w   | w          | w                     | f                                 |
| w   | w   | f   | w          | w                     | f                                 |
| w   | f   | w   | f          | w                     | f                                 |
| w   | f   | f   | f          | f                     | f                                 |
| f   | w   | w   | f          | w                     | w                                 |
| f   | w   | f   | f          | f                     | f                                 |
| f   | f   | w   | f          | w                     | w                                 |
| f   | f   | f   | f          | f                     | f                                 |
Disjunktive NF:
Alle $D$ die wahr sind und mit $\lor$ Kombinieren:
$D\iff(\neg A \land B \land C) \lor (\neg A \land \neg B \land C)$ 

Konjunktive NF:
Alle $D$ die falsch sind mit $\land$ kombinieren:
$\neg D \iff((A\land B\land C)\land (A\land B\land\neg C)\land(A\land\neg B\land C)\land(A\land\neg B\land\neg C)\land(\neg A \land B\land\neg C)\land(\neg A\land\neg B \land\neg C))$ $D\iff (\neg(A\land B\land C)\land\neg (A\land B\land\neg C)\land\neg (A\land\neg B\land C)\land\neg(A\land\neg B\land\neg C)\land\neg(\neg A \land B\land\neg C)\land\neg(\neg A\land\neg B \land\neg C))$ In die klammer nehmen: $D\iff ((\neg A\land\neg B\land\neg C)\land (\neg A\land\neg B\land C)\land(\neg A\land B\land\neg C)\land(\neg A\land B\land C)\land(A \land\neg B\land C)\land(A\land B \land C))$ 