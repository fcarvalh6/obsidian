#HS2025 #DM 

**Bemerkung 1:** Menge aller Programme $\sim \mathbb{N}$, jedes Programm berechnet höchstens eine Funktion $\mathbb{N}\to\{ 0,1 \}$. Es existieren Funktionen, die von keinen Programm berechnet werden. 

**Bemerkung 2:** $\mathbb{N}\prec \mathcal{P}(\mathbb{N})\prec \mathcal{P}(\mathcal{P}(\mathbb{N}))\prec\dots$ 

**Bemerkung 3:** Kontinuumshypothese: Es gibt kein $M$ mit $\mathbb{N}\prec M \prec \{ 0,1 \}^{\infty}$ 

## Zahlentheorie - Eigenschaften von $\mathbb{Z}$

**Vorausgesetzt:** Menge $\mathbb{Z},+,\cdot,- (\text{unär)},\text{Assoz.}, \text{Komm.},\text{Distrib.},\le,| |$

Teilbarkeit: $a\mid b \stackrel{\text{def}}\iff \exists c(b=a\cdot c)$

Primzahl: $p \text{ prim} \stackrel{\text{def}}\iff p>1\land \forall d(((d>1)\land (d\mid p))\to d= p)$

**Theorem 4.1:** Für alle $a\in \mathbb{Z}$ und $d\in \mathbb{Z}\setminus \{ 0 \}$ existiert eindeutige $q,r\in \mathbb{Z}$ mit $a=d\cdot q+r$ und $0\le r \le |d|$ 

Schreibweise: $R_{d}(a)$ für $r$ in Theorem 4.1

Für $a,b$ mit $a\not=0$ oder $b\not= 0$ ist ein g. g. T. ein Element $d$ mit $(d\mid a)\land (d\mid b)\land (\forall c (c\mid a)\land(c\mid b) \to (c\mid d))$ 

$\text{gcd}(a,b)$ ist der eindeutige positive  g. g. T. von $a$ und $b$.

**Lemma 4.2:** $\text{gcd}(m,n-q\cdot m)=\text{gcd}(m,n)$

Insbesondere: $\text{gdc}(m,R_{m}(n))=\text{gcd}(m,n)$ 

**Definition:** $(a,b) \stackrel{\text{def}}=\{ u\cdot a+v\cdot b\mid u,v \in \mathbb{Z}\}$ und $(a)\stackrel{\text{def}}=\{ u\cdot a\mid u \in \mathbb{Z}\}$ 

**Lemma:** für $a,b\in \mathbb{Z},a \not=0$ oder $b\not=0$, gilt $(a,b)=(\text{gcd}(a,b))$

Beweisidee: Sei $a,b$ so, dass $a\not=0$ oder $b\not=0,$ und $d\in(a,b)$ das kleinste positive Element in $(a,b)$. Dann $d=u^{*}a+v^{*}b.$ 
Weiter: 
- $d\mid a$ und $d\mid b$ (wenn z.B. $d\not\mid a$, dann $a=q\cdot d+r$ mit $0<r<d$ und $r\in(a,b)$ kleiner als $d$ (Widerspruch)) 
- Für alle $c$ mit $c\mid a$ und $c\mid b$ gilt $c \mid u^{*}a+v^{*}b$. Also $d = \text{gcd}(a,b)$
- $(d)\subseteq(a,b)$ und $d\mid (ua+vb)$ für beliebige $u,v$, also $(a,b)\subseteq(d)$. Also $\text{gcd}(a,b)=(d)=(a,b)$ 

Insbesondere ist $\text{gcd}(a,b)=ua+vb$ für geeignete $u,v\in \mathbb{Z}$

**Theorem  4.6:** Jedes $x\in \mathbb{Z},x>1$, kann eindeutig in der Form $x=\prod_{P_{i}}^{e_{i}}$ mit Primzahlen $p_{1}<p_{2}<\dots<p_{r}$ und $e_{i}\in \mathbb{N} \setminus \{ 0 \}$ geschrieben werden. 

Motivation:

$$
\begin{align}
x^{3}+x^{2}&=y^{4}+y+1 \\
x^{3}-x&=y^{2}+1
\end{align}
$$

Bekannt: $a \equiv_{m} b \stackrel{\text{def}}\iff m\mid(a-b)$ 

Eigenschaften von $\equiv_{m}:$ 
- ÄR auf $\mathbb{Z}$
- $a=b \implies a\equiv_{m}b$
- $a\not\equiv_{m}b \implies a\not=b$ 
- $a\equiv_{m}R_{m}(a)$ 
- $a\equiv_{m}b\iff R_{m}(a)=R_{m}(b)$
- $a\equiv_{m}b$ und $c\equiv_{m}d \implies a+c\equiv_{m}b+d$ und $a\cdot c\equiv_{m}b\cdot d$ 
- für Polynome $f: f(a_{1},\dots,a_{k})\equiv_{m}f(R_{m}(a_{k}))$ 