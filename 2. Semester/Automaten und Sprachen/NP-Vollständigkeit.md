$\varphi= a_1 \lor a_2 \lor a_3 \lor a_4$ 
- $\varphi$ is genau dann wahr wenn mindestens ein $a_i$ wahr ist

## 3SAT
**3SAT**
$$
\varphi =
\overbrace{(x_1 \lor x_2 \lor x_3)}^{C_1}
\;\land\;
\overbrace{(\neg x_1 \lor x_2 \lor \neg x_3)}^{C_2}
\;\land\;
\overbrace{(\neg x_1 \lor \neg x_2 \lor \neg x_3)}^{C_3}
$$
**Subset-Sum**
$\langle S=(y_i,z_i,g_k,h_k|i\leq l, k \leq n),t\rangle$ 

| Zahl  | $x_1$ | $x_2$ | $x_3$ | $c_1$ | $c_2$ | $c_3$ |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| $y_1$ | 1     | 0     | 0     | 1     | 0     | 0     |
| $z_1$ | 1     | 0     | 0     | 0     | 1     | 1     |
| $y_2$ |       | 1     | 0     | 1     | 1     | 0     |
| $z_2$ |       | 1     | 0     | 0     | 0     | 1     |
| $y_3$ |       |       | 1     | 1     | 0     | 0     |
| $z_3$ |       |       | 1     | 0     | 1     | 1     |
| $g_1$ |       |       |       | 1     | 0     | 0     |
| $h_1$ |       |       |       | 1     | 0     | 0     |
| $g_2$ |       |       |       |       | 1     | 0     |
| $h_2$ |       |       |       |       | 1     | 0     |
| $g_3$ |       |       |       |       |       | 1     |
| $h_3$ |       |       |       |       |       | 1     |
| $t$   | 1     | 1     | 1     | 3     | 3     | 3     |
**Lösung** $T \subset S: \displaystyle\sum_{s\in T} s=t$ 
- $y_i\in T \implies x_i$ wahr
- $z_i\in T \implies x_i$ falsch
- $g_i,h_i$: Füller, maximal zwei pro Klausel-Spalte

**Folgerung**:
$\varphi$ erfüllbar $\iff \langle S,t\rangle$ lösbar