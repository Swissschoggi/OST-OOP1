Gesucht: T-Periodische Funktion $f(t)$
	$\omega={2\pi\over T}$ 
Ziel: Finde $a_k, b_k$ so dass
$S_N(t)=a_0 + \displaystyle\sum_{k=1} ^N a_k cos(\omega_1 k t) + b_k sin(\omega_1 k t)$ 
$f(t)$ "möglichst gut" wiedergibt

Verfahren: "möglichst gut" heisst möglichst keine mittlere quadratische Abweichung

${\color{green}{1\over T}\int_0 ^T}(f(t)-S_N(t))\color{orange}^2 {\color{green}dt}$ 

$0={d\over da_k} {1\over T}\int_0 ^T(f(t)-S_N(t))^2 dt$ für $k=0,1,...,N$
$0= {1\over T}\int_0 ^T{d\over da_k}(f(t)-S_N(t))^2 dt$
$0={1\over T}\int_0 ^T 2(f(t)-S_N(t)) \cdot {d(f(t)-S_N(t))\over da_k} dt$
$0= {2\over T}\int_0 ^T f(t) {d(-S_N(t))\over da_k} -S_N(t) {d(+S_N(t))\over da_k} dt$
$0= {2\over T}\int_0 ^T S_N(t) {dS_N(t)\over da_k} - {2\over T} \int_0 ^T f(t) {dS_N(t)\over da_k} dt$
${2\over T}\int_0 ^T f(t) {dS_N(t)\over da_k} = {2\over T} \int_0 ^T S_N(t) {dS_N(t)\over da_k} dt$

$0={d\over db_k} {1\over T}\int_0 ^T(f(t)-S_N(t))^2 dt$ für $k=1,2,...,N$
