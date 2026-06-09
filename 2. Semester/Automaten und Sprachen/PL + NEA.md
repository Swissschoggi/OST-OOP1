### Pumping Lemma
$L$ ist pumpbar wenn es $N>0$ gibt derart dass jeder endliche Automat in drei Teile $w=\color{green}x\color{red}y\color{lightblue}z$ zerlegt werden kann mit:
1. ${\color{green}x\color{red}y}\leq N$ 
2. $|{\color{red}y}|> 0$
3. ${\color{green}x\color{red}y}^k {\color{lightblue}z} \in L \text{ für alle k}\in \mathbb{N}$ 

**Behauptung** 
Die Sprache $L \subset\displaystyle\sum ^*$ ist nicht regulär.

**Beweis (Widerspruch)**
1. Annahme: $L$ ist regulär
2. Gemäss Pumping Lemma gibt es die Pumping Length $N$ 
	- Es darf keine Annahme über die konkrete Grösse von $N$ gemacht werden!
3. Wähle ein Wort $w \in L$ mit $|w|\geq N$
	- Die Definition muss $N$ verwenden!
4. Aufteilung des Wortes gemäss Pumping Lemma
	- $w=\color{green}x\color{red}y\color{lightblue}z$, ${\color{green}x\color{red}y}\leq N$, $|{\color{red}y}|> 0$ 
5. Auswirkung des Pumpens
	- ${\color{green}x\color{red}y}^k {\color{lightblue}z} \notin L$ für mindestens ein $k\in \mathbb{N}$ 
6. Widerspruch und Schlussfolgerung, dass die Annahme falsch ist

### NEA
Alle übergänge wegnehmen die keinen Sinn machen.