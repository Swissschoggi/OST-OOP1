**Ziel:** Es soll gezeigt werden, dass $A(n)$ gilt, $\forall n \in \mathbb{N}\text{ , }n\geq n_0$   
	Nutzen der Abtrennungsregel:
		$A \land (A\implies B)\implies B$ 
	für die Induktion;
		$A(_{n0}) \land (A(_{n0})\implies A(_{n_0+1}))\implies A(_{n_0+1})$ 
	Iterativ:
		$A(_{n0}) \land (A(_{n0})\implies A(_{n_0+1}))\implies\forall n \geq n_0 \text{ : } A(_n)$ 

- $A(_{n0})$--> A gilt für das erste Element
- $(A(_{n0})\implies A(_{n_0+1}))$--> Wenn A für das Element n gilt, dann gilt auch n+1
- $\forall n \geq n_0 \text{ : } A(_n)$-->A gilt für alle $n\geq n_0$

$S(n)=\sum_{k=1}^n k={1\over 2}n*(n+1), \forall n \in \mathbb{N},n\geq 1$ 
	1. Verankerung: $n=1$
		$S(1)=\sum_{k=1}^1 k=1$ Linke Seite der Formel
		${1\over 2} *1*(1+1)=1$ Rechte Seite der Formel
	2. Induktionsschritt: $n\text{ --> }n+1$
		a) annahme
			Formel gilt für n
			$S(n)=\sum_{k=1}^n k={1\over 2}n(n+1)$ 
		b) zu zeigen
			Formel gilt auch für $n+1$:
			$S(n+1)=\sum_{k=1}^{n+1}k={1\over 2}(n+1)*(n+2)$ 
		c) Beweis
			$\sum_{k=1}^{n+1}k=\sum_{k=1}^n k+(n+1)$
				gemäss a):
					$={1\over 2}n(n+1)(n+1)$
					$={1\over 2}n(n+1)(n+2)$

1. **Verankerung**: Es wird geprüft, ob $A(n)$ für den ersten Wert richtig ist. Ob also die Aussage $A(n_0)$ gilt. Z.B. für $n_0 = 0$ oder für $n_0 = 1$ 
2. **Induktionsschritt**: $n\text{ --> }n+1$,
		Es wird gezeigt:1§
	Wenn $A(n)$ gilt, dann gilt auch $A(n+1)$. Als Formel: $A(n)\implies A(n+1)$
		a) **Induktionsannahme:** $A(n)$ sei richtig für $n$
		b) **Induktionsbehauptung:** $A(n+1)$
		c)**Induktionsbeweis:** Es wird die Aussage $A(n)$ verwendet, um die Richtigkeit der Behauptung $A(n+1)$ zu zeigen.


#### Beispiel:
Zeige mittels vollständiger Induktion, dass
	$\forall n \in \mathbb{N},n\geq 2 : 6 | (n^3 -n)$ 
d.h. die Zahl $n^3 -n$ ist durch $6$ teilbar.

Verankerung: $n=2$
	$n^3 -n = 8-2=6$ ist durch 6 teilbar!
Induktion:
	i) annahme: $6|(n^3-n)$
	ii) zu zeigen: $6|((n+1)^3-(n+1))$
	iii) Beweis:
		$(n+1)^3 -(n+1)$
		$=n^3+3n^2+3n+1-n-1$
		$=n^3+3n^2+2n$
		$=n^3 -n +n +3n^2 +2n$
		$=(n^3-n)+(n+3n^2+2n)$
		$=(n^3-n)+3(n^2+n)$
		$=(n^3-n)+3*(n*(n+1))$ 
		$n^3 -n$ ist durch 6 teilbar wegen i)
		$n*(n+1)$ ist gerade
	Summe von 2 durch 6 teilbaren Zahlen ist auch durch 6 teilbar