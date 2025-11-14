#HS2025 #DM 

## Rest

$R_{9}(10)=1\quad R_{3}(9)=0\quad R_{5}(24)=4$

$R_{9}(10^{201520152015})=1$

$R_{7}(6^{420002016})=1$

$R_{8}(3^{2017})=R_{8}(3\cdot 3^{2016})=R_{8}(3\cdot R_{8}(3^{2})^{1008})=R_{8}(3\cdot 1)=3$

## Teilbarkeit

Zeige für alle $x,y,z\in \mathbb{N}$, falls $x|y$ und $y|z$, dann $x|z$ 

- Da $x|y$, haben wir $y=x\cdot l$ für ein $l\in \mathbb{N}$
- $y|z \dot\implies z = y\cdot k$ für ein $k\in \mathbb{N}$ 
- $\dot\implies z=x\cdot l\cdot k$ für ein $k\in \mathbb{N}$
- $\dot\implies z = x\cdot v$ für ein $v\in \mathbb{N}$
- $x|z$ 

Zeige, dass für jedes $a\in \mathbb{N}$ gilt, $3|a$ oder $3|a+2$ oder $3|a+4$

Fallunterscheidung 

1. $R_{3}(a)=0$ : Wir haben $a=3\cdot k$ für ein $k\in \mathbb{Z}$ und $a=3\cdot k \dot\implies 3|a$
2. $R_{3}(a)=1$ : Wir haben $a=3k+1$ für ein $k\in \mathbb{N}$
$a=3k+1\dot\implies a+2=3k+1+2\dot\implies a+2=3k+3=3(k+1)\dot\implies 3 |a+2$
3. $R_{3}(a)=2$  : Wir haben $a=3k+2$ für ein $k\in \mathbb{N}$
$a=3k+2\dot\implies a+4=3k+2+4\dot\implies a+4=3k+6\dot\implies a+4=3\cdot(k+2)\dot\implies 3 |a+4$

Zeige, dass $5$ die einzige Primzahl ist, die sowohl als Summe als auch als Differenz zweier Primzahlen geschrieben werden kann. 

Sei $p$ so eine Primzahl. Da $2$ die einzige gerade Primzahl ist, gibt es Primzahlen $p_{1},p_{2}$ mit $p=p_{1}+2$ und $p=p_{2}-2$. Also ist $p_{1}$ prim, $p_{1}+2$ ist prim und $p_{1}+4$ ist prim. Laut der letzten Aufgabe muss eine der drei Primzahlen $p_{1},p_{1}+2,p_{1}+4$ durch $3$ teilbar sein. Somit kann $p_{1}$ nur $3$ sein, also ist $5$ die einzige Primzahl mit dieser Eigenschaft. 

## gcd und lcm

$\text{gcd}(36,60)=2^{2}\cdot 3=12$, $\text{lcm}(36,60)=2^{2}\cdot 3^{2} \cdot 5=180$

Primfaktorzerlegung:
- $36=2\cdot 18=2 \cdot 2\cdot 9=2^{2}\cdot 3^{2}$
- $60=2\cdot 30=2 \cdot 2\cdot 15=2^{2}\cdot 3 \cdot 5$

Zeige, dass für alle $a,b,c\in \mathbb{N}\setminus\{ 0 \}$, $\text{gcd}(a,\text{lcm(b,c)})=\text{lcm}(\text{gcd}(a,b),\text{gcd}(a,c))$ 

Seien $a=\prod_{i}p_{i}^{e_{i}},b=\prod_{i}p_{i}^{f_{i}},c=\prod_{i}p_{i}^{g_{i}}$ die Primfaktorzerlegungen von $a,b$ und $c$.

$\text{gcd}(a,\text{lcm}(b,c))=\text{gcd}\left( a,\prod_{i}p_{i}^{\text{max}(f_{i}e_{i})} \right)=\prod_{i}p_{i}^{\text{min}(e_{i},\text{max}(f_{i}g_{i}))}$ 

Andere Seite: $\text{lcm}(\text{gcd}(a,b),\text{gcd}(a,c))=\prod_{i}p_{i}^{\text{max}(\text{min}(e_{i},f_{i}),\text{min}(e_{i},g_{i}))}$ 

Das heisst, es bleibt noch zu zeigen, dass

$\text{min}(x,\text{max}(y,z))=\text{max}(\text{min}(x,y),\text{min}(x,z))$ für alle $x,y,z\in \mathbb{N}$

Nehme o. B. d. A. an, dass $y\le z$. Wir betrachten die drei Fälle

1. $x\le y\le z$
	- $\text{min}(x,\text{max}(y,z))=\text{min}(x,z)=x$ 
	- $\text{max}(\text{min}(x,y),\text{min}(x,z))=\text{max}(x,x)=x$
2. $y\le x \le z$
3. $y\le z \le x$ 

