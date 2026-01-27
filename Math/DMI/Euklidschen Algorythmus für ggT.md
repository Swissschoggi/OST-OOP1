1. Setze $x=a$ , $y=b$ , $q=x\text{ }div\text{ } y$ , $r=x-q*y$
2. Wiederhole so lange bis $r=0$ 
Ergebnis:
	$y=ggT(a,b)$
Beispiel:
	$ggT (122,72), a=122, b=72$
	$x_0=a=122,y_0=b=72$

|       | $x_i$ | $y_i$ | $q_i=x_i\text{ }div\text{ } y_i$ | $r=x-q*y$ |
| ----- | ----- | ----- | -------------------------------- | --------- |
| $i=0$ | 122   | 72    | 1                                | 50        |
| $i=1$ | 72    | 50    | 1                                | 22        |
| $i=2$ | 50    | 22    | 2                                | 6         |
| $i=3$ | 22    | 6     | 3                                | 4         |
| $i=4$ | 6     | 4     | 1                                | 2         |
| $i=5$ | 4     | 2     | 2                                | 0         |
y in der untersten Reihe ist der ggT also $ggT(122,72)=2$
