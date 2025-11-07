#HS2025 #DM 

$\mathbb{Z}_{m}=\{ 0,\dots,m-1 \}$

Beispiele: 

$2^{20}\equiv_{15}(2^{4})^{5}\equiv_{15}1^{5}\equiv_{15}1$ 

$7^{17}\equiv_{11}7\cdot 7^{16}\equiv_{11}7\cdot(((7^{2})^{2})^{2})^{2}\equiv_{11}6$ 

## Modulare Inversion

Betrachte $a\cdot x\equiv_{m}1$ bei gegebenen $a,m\in \mathbb{Z}$ für $x\in \mathbb{Z}_{m}$ und $\text{gcd}(a,m)=1$. Dann existiert $u,v$ mit $u\cdot a+v\cdot m=\text{gcd}(a,m)=1$, also $u\cdot a\equiv_{m}1$ und $x=R_{m}(u)$.

Schreibweise $x\equiv_{m}a^{-1}$ oder $x\equiv_{m} \frac{1}{a}$

Beispiele: $5^{-1}\equiv_{13}8$, $7^{-1}\equiv_{90}13$ 

gibt es ein $x \in \mathbb{Z}$ mit $x\equiv_{3}2$ und $x\equiv_{4}1$ 

**Theorem 4.19:** Seien $m_{1},\dots,m_{r}>0$ paarweise teilerfremd. Für $M=\prod_{i=1}^{r}m_{i}$ und beliebige $a_{i},\dots,a_{r}$ mit $a_{i}\in \mathbb{Z}_{m}$ ist das System $x\equiv_{m}a_{1},\dots,x\equiv_{m_{r}}a_{r}$ eindeutig lösbar für $x\in \mathbb{Z}_{M}$.

Beweis: $M_{i}=\frac{M}{m_{i}}$, damit $\text{gcd}(M_{i},m_{i})=1$, weil $\text{gcd}(m_{k},m_{i})=1$ für $k\not= i$. Also gibt es ein $N_{i}$ mit $M_{i}\cdot N_{i} \equiv_{m}1$. Weiter ist $M_{i}\cdot N_{i}\equiv_{m_{k}}0$ für $k\not=i$. Deshalb ist

$$
\left( \sum_{i=1}^{r}a_{i}\cdot M_{i}\cdot N_{i}\right)\equiv_{m_{k}}a_{k} \quad \text{für alle k und } x=R_{M}\left( \sum a_{i}\cdot M_{i}\cdot N_{i} \right)
$$

Jede weitere Lösung $x'\in \mathbb{Z}_{M}$ erfüllt $x'\equiv_{m_{k}}x$, also $m_{k}\mid (x'-x)$ und damit $M\mid (x'-x)$

## Kryptographie

Grundannahme: riesige Primzahl $p$ $R_{p}(g^{x})$ (z.B. für g=2, und geg. $x$) effizient berechenbar, aber geg. $R_{p}(g^{x})$ und $g,p$ ist es schwer, $x$ zu finden.

$A\to B$

$A$
- wählt $x_{A}$ zufällig
- setzt $y_{A}=R_{p}(g^{x_{A}})$
- $A$ schickt $B$ $y_{A}$ 

$B$
- wählt $x_{B}$ zufällig
- setzt $y_{B}=R_{p}(g^{x_{B}})$ 
- $B$ schickt $A$ $y_{B}$ 

$k_{AB}\equiv R_{p}(y_{B}^{x_{A}})$ und $k_{BA}\equiv R_{p}(y_{A}^{x_{B}})$

$k_{AB}\equiv_{p}y_{B}^{x_{A}}\equiv_{p}(g^{x_{B}})^{x_{A}}\equiv_{p}(g^{x_{A}})^{x_{B}}\equiv_{p}y_{A}^{x_{B}}\equiv_{p}k_{BA}$ 

**Beobachtung:** DHKE benutzt nur Multiplikation in $\mathbb{Z}_{p}$ 
- $\mathbb{Z}$ und $\mathbb{Z}_{p}$ gut verstanden, also andere Strukturen nutzen?
- $\langle S;*\rangle$ anstelle von $\langle \mathbb{Z}_{p};\cdot\rangle$ 