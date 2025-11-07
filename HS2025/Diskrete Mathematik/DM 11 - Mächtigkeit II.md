#HS2025 #DM 


## Mächtigkeit

**Erinnerung:** 
- $A\sim B$, falls bijektive Funktion $f:A\to B$ existiert
- $A\preccurlyeq B$, falls injektive Funktion $f:A\to B$ existiert
- $A$ abzählbar, falls $A\preccurlyeq \mathbb{N}$ (sonst $A$ überabzählbar)
- $|A|=n$, falls $A\sim n$

**Bemerkung:** $f:A\to B$ bijektiv $\dot\implies f^{-1} \stackrel{\text{def}}=\hat{f}: B\to A$ bijektiv.

**Beispiele:** 
- $\mathbb{Z}\sim \mathbb{N}$, weil $f:\mathbb{N}\to \mathbb{Z}$ mit $f(n)=(-1)^{n} \left\lceil  \frac{n}{2}  \right\rceil$ bijektiv.
- $(0,1)\sim \mathbb{R}$, weil $f: \mathbb{R} \to (0,1)$ mit $f(x)=\frac{1}{(e^{x}+1)}$ 

**Lemma 3.15**
1. $\sim$ ist eine Äquivalenzrelation
2. $\preccurlyeq$ ist transitiv
3. $A\subseteq B \implies A\preccurlyeq B$

**Theorem 3.16:** $A\preccurlyeq B$ und $B\preccurlyeq A \implies A\sim B$ 

**Theorem 3.17:** $A\preccurlyeq \mathbb{N}\iff A$ endlich oder $A\sim \mathbb{N}$ 

Beweis:

"$\implies$"
$A\preccurlyeq \mathbb{N}\dot\implies$ es gibt injektive $f:A\to \mathbb{N}$
- $\dot\implies f:A \to f(A)$ bijektiv

Fall 1: $f(A)$ endlich, also existiert bijektive $g: f(A)\to n \dot\implies g\circ f:A\to n$ bijektiv

Fall 2: $f(A)$ nicht endlich, dann konstruiere Bijektion $g:f(A) \to \mathbb{N}$ wie folgt
- setze $C_{0}\stackrel{\text{def}}=f(A)$. Für das kleinste $c_{0}\in C_{0}$ setze $g(c_{0})=0$ 
- setze $C_{1}\stackrel{\text{def}}=C_{0}\setminus \{ c_{0} \}$ Für das kleinste $c_{1}\in C_{1}$ setze $g(c_{1})=1$
- fahre so fort. Vorgehen bricht nicht ab ($\dot\implies g$ surjektiv) und definiert $g(c)$ für $c\in f(A)$ nach endlich viele Schritten.

"$\impliedby$" 
Fall 1: $A$ endlich dann existiert $f:A\to n \subseteq \mathbb{N}$ , also $f:A\to \mathbb{N}$ injektiv

Fall 2: $A\sim \mathbb{N}$, dann $A\preccurlyeq \mathbb{N}$ 

## Bitstrings

**Schreibweise:** $A^{*}$ für die Menge aller endlichen Folgen über $A$

Beispiel: $\{ 0,1 \}^{*}=\{ \varepsilon, 0,1,00,10,11,\dots\}$ Menge aller endlichen Bitstrings

$|x|\stackrel{\text{def}}=$ Länge von $x$ (Bsp.: $|01|=2$); "$||$" ist Konkatenation von Bitstrings

**Theorem:** $\{ 0,1 \}^{*}\sim \mathbb{N}$

Beweis: sei $\text{Zahl}(x)$ die Interpretation von Bitstring $x$ als natürliche Zahl.
Dann: $f:\{ 0,1 \}^{*}\to \mathbb{N}$ mit $f(x)=\text{Zahl}(1||x)-1$ bijektiv

**Theorem:** $\mathbb{N}\times \mathbb{N}\sim \mathbb{N}$

**Theorem:** $A$ abzählbar $\implies A^{*}$ abzählbar.

Beweisidee: Kodiere endliche Folge $(a_{1},\dots,a_{n})$ mit $a_{i}$ eindeutig als Bitstring. Sei dazu $f:A\to \{ 0,1 \}^{*}$ die Kodierungsfunktion für einzelne $A$-Elemente. Kodiere z.B. $(a_{1},\dots,a_{n})$ als $\underbrace{0\dots0}_{|f(a_{1})|}||f(a_{1})||\underbrace{0\dots0}_{|f(a_{2})|}||f(a_{2})||\dots$ bis $f(a_{n})$

**Theorem:** $\{ 0,1 \}^{\infty}\stackrel{\text{def}}=\{ 0,1 \}^{\mathbb{N}}$ nicht abzählbar

Beweis (Widerspruch): Annahme: $\{ 0,1 \}^{\infty}$ abzählbar $\implies$ existiert bijektive $f:\mathbb{N}\to\{ 0,1 \}^{\infty}$ Schreibe $g_{i}=f(i)$ als Funktion $g_{i}:\mathbb{N}\to \{ 0,1 \}$. 

Sei $g:\mathbb{N}\to \{ 0,1 \}$ mit $g(x)=1-g_{x}(x)$. Dann ist $g\in \{ 0,1 \}^{\infty}$, also $g=g_{i^{*}}$ für ein $i^{*}\in \mathbb{N}$. Es gibt aber $g(i^{*})=1-g_{i^{*}}(i^{*})=1-g(i^{*})$. Falsch. 