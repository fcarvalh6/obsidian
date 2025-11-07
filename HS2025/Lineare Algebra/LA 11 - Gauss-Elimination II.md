#HS2025 #LA 

**Zeilenvertauschungen** (falls Pivot = 0): auch umkehrbar, Lösungen bleiben gleich. Falls alle weitere Pivots = 0, dann keine Vertauschungen helfen. 

## Zeilenoperationen

**Lemma 3.2 (Invarianz der Lösungen):** sei $A$ eine $m\times n$ Matrix, $M$ eine invertierbare $m\times m$ Matrix, $\mathbf{b}\in \mathbb{R}^{m}$. Dann haben die Systeme $A\mathbf{x}=\mathbf{b}$ und $MA\mathbf{x}=M\mathbf{b}$ die gleichen Lösungen $\mathbf{x}$ 

Beweis: für alle $\mathbf{x}\in \mathbb{R}^{n}$:
- $A\mathbf{x}=\mathbf{b}\implies MA\mathbf{x}=M\mathbf{b}$
- $MA\mathbf{x}=M\mathbf{b}\implies \underbrace{M^{-1}M}_{I}A\mathbf{x}=\underbrace{M^{-1}M}_{I}\mathbf{b}$

**Lemma 3.3 (Invarianz des Nullraums):** sei $A,M$ wie vorher. Dann haben $A$ und $MA$ den gleichen Nullraum: $N(A)=N(MA)$

Beweis: Benutze Lemma 3.2 mit $\mathbf{b}=0$.

**Lemma 3.4 (Invarianz linearer Unabhängigkeit):** $A,M$ wie vorher. $A$ hat unabhängige Spalten $\iff MA$ hat linear unabhängige Spalten. 

Beweis: Spalten linear unabhängig $\iff$ Nullraum $=\{ 0 \}$ (Beobachtung 2.5). Aussage folgt aus Lemma 3.3.

**Lemma 3.5 (Invarianz der Zeilenraums):** $A,M$ wie vorher. Dann haben $A$ und $MA$ den gleichen Zeilenraum, $R(A)=R(MA).$ Im allgemeinen gilt aber $C(A)\not=C(MA).$

**Lemma 3.6 (Invarianz unabhängiger Spaltenindices und des Rangs):** $A,M$ wie vorher. Für alle $j\in[n]:$ Spalte $j$ ist unabhängig in $A\iff$ Spalte $j$ ist unabhängig in $MA$. Also haben $A$ und $MA$ die gleiche Anzahl unabhängiger Spalten und somit den gleichen Rang.

## Erfolg und Scheitern

**Theorem 3.7:** Sei $A\mathbf{x}=\mathbf{b}$ ein System mit $m$ Gleichungen in $m$ Variablen. Die Folgenden zwei Aussagen sind äquivalent:
1. Gauss-Elimination (Algo. 2) ist erfolgreich
2. Die Spalten von $A$ sind linear unabhängig

Beweis: $1.\implies 2.$ : Wenn Gauss Erfolg hat: $A\to U$, obere Dreiecksmatrix, mit allen $u_{jj}\not=0.$
U hat unabhängigen Spalten nach Korollar 1.23.3: keine Spalte ist Linearkombination der vorherigen. 

$2.$ folgt mit Lemma 3.4 (Invarianz linearer Unabhängigkeit), wiederholt angewendet $(A\to A' \to \dots \to U)$ 

$2.\implies 1.$ : Beweis durch Kontraposition: zeige (logisch gleichbedeutend) $\neg (1.) \implies \neg( 2.)$

$\neg(1.):$ Gauss scheitert (in Spalte $j$); dann haben wir eine Matrix $U$ mit $u_{11},u_{22},\dots,u_{j-1j-1}\not=0$. Spalte $j$ ist Linearkombination der vorherigen Spalten. Spalten von $U$ sind linear abhängig und damit auch die Spalten von $A$ (Lemma 3.4). Das ist $\neg(2.)$. 

