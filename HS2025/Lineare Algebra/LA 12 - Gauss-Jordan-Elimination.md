#HS2025 #LA 

## Gauss-Jordan-Elimination

$A\mathbf{x}=\mathbf{b}\to R\mathbf{x}=\mathbf{c}$, $R$ in reduzierte Zeilenstufenform, funktioniert für alle Systeme.

**Lemma 3.14:** $R$ in $\text{RREF}(j_{1},j_{2},\dots j_{r})$ hat die unabhängigen Spalten $j_{1},j_{2},\dots,j_{r}$ und somit Rang $r$.

Elimination: wenn $A$ nicht in $\text{RREF}$ ist (Fokus auf $A\to R$), wie Gauss, aber pivot auf 1 bringen und obere Werte eliminieren.

Sehr nützlich: Variante mit $m$ rechten Seiten (Spalten einer $m\times m$ Matrix B) %

**Theorem 3.17** Sei $A$ eine $m\times m$ Matrix und $(R,j_{1},j_{2},\dots,j_{r},M)$ die Ausgabe von Algorithmus 6 bei Eingabe $(A,I)$. Dann ist $M$ invertierbar, $R=MA$ und $R$ in $\text{RREF}(j_{1},j_{2},\dots,j_{r})$ 

Beweis: $C=\underbrace{M_{l}M_{l-1}\dots M_{1}}_{\text{Zeilenoperationen}}B, \quad R=M_{l}M_{l-1}\dots M_{1}A$
Da alle $M_{i}$ invertierbar, ist auch das Produkt $M$ invertierbar (Lemma 2.59) 

$R$ ist die $\text{RREF-}$Standardform von $A$ und gibt uns die $CR-$Zerlegung

**Theorem 3.18:** Sei $A$ eine $m\times n$ Matrix. Es gibt genau eine $m\times n$ Matrix $R$ (nämlich die aus Theorem 3.17) mit Folgenden Eigenschaften:
1. $R=MA$ mit einer invertierbaren Matrix $M$
2. $R$ ist in $\text{RREF}$ 

Genauer: $R$ ist in $\text{RREF}(j_{1},j_{2},\dots,j_{r})$, wobei $j_{1},j_{2},\dots,j_{r}$ die Indices der unabhängigen Spalten in A sind, und

$$
R=\begin{bmatrix}
\underbrace{R'}_{r\times n} \\
\underbrace{0}_{(m-r)\times n}
\end{bmatrix},
$$

mir $R'$ der eindeutigen Matrix sodass $A=CR'$ in Theorem 2.46($CR-$Zerlegung).

Berechnung der Inversen: $(A,I)\stackrel{\text{G.-Jordan}}\to(R,M)$

**Theorem 3.19:** $A$ invertierbar $\iff R=I$ (und dann ist $M=A^{-1}$)

Lösen von $A\mathbf{x}=\mathbf{b}$ (für möglicherweise viele b's).  $(A,I)\to(R,M)$

**Theorem 3.20:** Setze $\mathbf{c}=M\mathbf{b}$ und löse $R\mathbf{x}=\mathbf{c}$ direkt. 


