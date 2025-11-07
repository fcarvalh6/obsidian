#HS2025 #DM 

$f:A\to B'$ injektiv $\iff \forall a \forall b(f(a)=f(b)\to a=b)$

$g: A \to B$ surjektiv $\iff \forall b\exists a(f(a)=b)$ 

Sei $f: \mathbb{N}\to\mathbb{N}$ eine Funktion
- $f$ injektiv $\not\implies f$ surjektiv, Gegenbeispiel $f(x)=x+1$
- $f$ surjektiv $\not\implies f$ injektiv, Gegenbeispiel $f(x)=\left\lfloor  \frac{x}{2}  \right\rfloor$ 

## Gleichmächtigkeit

Zeige, dass die Mengen $A$ und $B$ gleichmächtig sind.
- Ansatz 1: Suche eine Bijektion $f: A\to B$
- Ansatz 2: Zeige $A\preccurlyeq B$ und $B\preccurlyeq A$. Theorem 3.16

Zeige, dass $\mathbb{N}$ und $M=\{ x\in \mathbb{N} \mid x \text{ gerade}\}$ gleichmächtig sind
- Da $M\subseteq \mathbb{N}$, haben wir nach Lemma 3.15(iii) $M\preccurlyeq \mathbb{N}$. 
- Wir zeigen, dass auch $\mathbb{N}\preccurlyeq M$ gilt. Wir definieren die Funktion $f:\mathbb{N}\to M$ mit $f(x)=2x$
- Offensichtlich haben wir $f(x)\in M$ für alle $x \in \mathbb{N}$. 
- Wir zeigen, dass $f$ injektiv ist. Seien $a,b \in \mathbb{N}$ beliebig. Wir haben $f(a)=f(b)\implies 2a = 2b \implies a = b$ 
- Also ist $f$ injektiv und somit haben wir $\mathbb{N}\preccurlyeq M$ (def. 3.42(ii))
- Nach Theorem 3.16 haben wir also $\mathbb{N}\sim M$. 

## Abzählbarkeit

Zeige Menge $A$ ist abzählbar.
- Ansatz 1: Suche eine Injektion $f:A \to \mathbb{N}$.
- Ansatz 2: Suche eine Injektion $f:A\to B$ und $\preccurlyeq$ transitiv. (Wir wissen $B$ ist abz.)

Zeige $\bigcup_{i=1}^n A_{i}$ ist abzählbar, wenn alle $A_{i}$ abzählbar sind.
- **Induktion:** Basis Schritt: Seien $A_{1}$ und $A_{2}$ beliebige Abzählbare Mengen. 
	- Da $A_{1}$ abzählbar ist, gibt es eine Injektion $f_{1}:A_{1}\to \mathbb{N}$
	- Da $A_{2}$ abzählbar ist, gibt es eine Injektion $f_{2}:A_{2}\to\mathbb{N}$ 
	- Wir definieren die Funktion $f:(A_{1}\cup A_{2})\to \mathbb{N}$
	- $f(x)=\begin{cases}2f_{1}(x) & \text{falls }x\in A_{1} \\ 2f_{2}(x)+1&\text{falls }x\not\in A_{1}\end{cases}$
	- $f(x)=\begin{cases}2^{f_{1}(x)+1}&\text{falls }x\in A_{1} \\ 3^{f_{2}(x)+1}&\text{falls }x\not\in A_{1}\end{cases}$
	- Wir zeigen, dass $f$ injektiv ist. Seien $a,b\in(A_{1}\cup A_{2})$ beliebig. Wenn $f(a)=f(b)$, dann haben wir entweder $f(a)=f(b)=2^{x}$ für ein $x\in \mathbb{N}$ (und $a,b\in A_{1}$) oder $f(a)= f(b)=3^{y}$ für ein $y\in \mathbb{N}$ (und $a,b\not\in A_{1}$) (def $f$. Theorem 4.6)
	- Nehme o. B. d. A. an, dass $f(a)=f(b)=2^{x}$ für ein $x$ (und $a,b\in A_{1}$) (1)
		- (1) $\implies f_{1}(a)+1=f_{1}(b)+1$ (def $f$, Theorem 4.6)
		- $\implies f_{1}(a)=f_{1}(b)$
		- $\implies a=b$ (injek. $f_{1}$)
	- Also ist $f$ injektiv
- **IH:** $\bigcup_{i=1}^m A_{i}$ ist abzählbar, wenn alle $A_{i}$ abzählbar sind.
- **IS:** $\bigcup_{i=1}^{m+1}A_{i}=\left( \bigcup_{i=1}^{m} A_{i} \right)\cup A_{m+1}$. 
	- $A_{m+1}$ ist nach Annahme abzählbar.
	- $\bigcup_{i=1}^{m}A_{i}$ ist nach IH abzählbar
	- Also ist $\bigcup_{i=1}^{m+1}A_{i}=\left( \bigcup_{i=1}^{m} A_{i} \right)\cup A_{m+1}$ abzählbar, da es die Vereinigung von zwei abzählbaren Mengen ist (Basis Schritt). 

$g:\mathbb{N}^{n}\to\mathbb{N}$
- $g(x_{1},\dots,x_{n})=p_{1}^{x_{1}}\cdot p_{2}^{x_{2}}\cdot \; \dots \;  \cdot p_{n}^{x_{n}}$, wobei $p_{i}$ die $i$-te Primzahl ist.

## Unabzählbarkeit

Zeige menge $C$ ist nicht abzählbar (wir wissen $D$ ist unabzählbar)
- Ansatz 1: Gegenbeispiel (Diagonalisierung)
- Ansatz 1.2: Suche eine Injektion $f: D\to C\quad (D\preccurlyeq  C)$ und Beweis durch Widerspruch (Nehme an $C\preccurlyeq \mathbb{N}$)