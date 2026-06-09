## Chomsky Normalform
$A \rightarrow BC$ oder $A  \rightarrow a$ und $S \rightarrow \epsilon$
1. Neue Start variable $S_0 \rightarrow S$ (wenn nötig)
2. $\epsilon$-Regeln $\begin{cases}A \rightarrow \epsilon \\B\rightarrow AC \end{cases}\implies$ A kann weg gelassen werden $\implies \begin{cases}B \rightarrow AC \\B\rightarrow C \end{cases}$ 
3. Unit Rules $\begin{cases}A \rightarrow B \\B\rightarrow CD \end{cases}\implies$ aus A kann man wie aus B auch CD machen $\implies\begin{cases}A \rightarrow CD \\B\rightarrow CD \end{cases}$ 
4. Verkettung: $A\rightarrow u_1u_2...u_n$ ersetzt durch $A \rightarrow u_1A_1, A_1\rightarrow u_2A_2,...,A_{n-2}\rightarrow u_{n-1}u_n$ und falls $u_i$ ein Terminalsymbol ist: $A_{i-1}\rightarrow U_iA_i, U_i\rightarrow u_i$

Wird zu Parse-Algorithmus

##### Gegeben
1. Grammatik $G=(V,\sum,R,S)$
2. Variable $A \in V$
3. Wort $w \in \sum^*$
###### Frage
Ist $w$ aus $A$ ableitbar? in Zeichen: $A \implies w$
