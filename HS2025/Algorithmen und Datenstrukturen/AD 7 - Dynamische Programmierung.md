#HS2025 #AD 

**Sortieren:** Invarianten zum Bearbeiten von Daten

**DP:** selbe Idee für Berechnungen $\to$ Rekursion

## Rekursion

**Beispiel:** Fibonacci-Zahlen $F_{n}=1,1,2,3,5,\dots$

```
Fib(x)
	if n <= 2 : f <- 1
	else f <- Fib(n-1) + Fib(n-2)
	return f
```

**Laufzeit:**

$T(1),T(2)=c$ und $T(n)=T(n-1)+T(n-2) \stackrel{\text{Induktion}}\implies T(n)\ge c\cdot F_{n}=\Omega(1.5^{n})$  

### Lösung 1: Memoization + Rekursion

```
Fib(x)
	if schon berechnet then : return memo[n]
	if n <= 2 : f <- 1
	else f <- Fib(n-1) + Fib(n-2)
	memo[n] <- f
	return f
```

### Lösung 2: iterativ, induktiv, bottom-up

```
Fib(n) 
	F[1] <- 1
	F[2] <- 1
	for i = 3...n
		F[i] <- F[i-1]+F[i-2]
	return F[n]
```

**Lösung 1 und 2:** Laufzeit $O(n)$ 

## Kernidee von DP

- Definiere Teilproblem
- Löse Teilproblem rekursiv oder induktiv

### Problem 1: Maximum Subarray Sum

Randmaxima (Teilproblem)
- $R_{j}$ = max $S_{ij} \ , \ S_{ij}=a_{i}+\dots+a_{j}$ 

Rekursion: $R_{j}=\text{max}\{ a_{j},a_{j}+R_{j} \}$

Auslesen der Lösung: $S^{*}=\text{max}\{ R_{1},R_{2},\dots,R_{n},0\}$

### Problem 2: Jump Game

Input: Array $A[1\dots n]$ von positiven ganzen Zahlen

Spiel:
- Starte am Position 1
- von Position $i$ dürfen wir zu $i+1,i+2,\dots,i+A[i]$ springen

Ziel: Erreiche Position $n$ mit möglichst wenig Sprüngen

#### Versuch 1

Teilproblem: $S[i]=$ Mindestzahl Sprünge, um Pos. $i$ zu erreichen

Rekursion: $S[i]=\text{min}\{ S[j]+1\mid1\le j<i\text{ und } j+A[j]\ge i\}$ 

```
S[1] <- 0
for i = 2...n 
	S[i] = INT_MAX
	for j = 1...i-1
		if j + A[j] >= i : S[i] <- min{S[i],S[j]+1}
```

**Laufzeit:** $\theta\left( \sum_{i=2}^n (i-1) \right)=\theta(n^{2})$ 

#### Versuch 2

Teilproblem: $M[k]=$ maximalen Index, den wir mir $k$ Sprüngen erreichen können. 

Rekursion:$M[k]=\text{max}\{ j+A[j] \mid M[k-2] \le j \le M[k-1] \}$ 

```
k <- 0, M[0] = 1, M[1] <- 1 + A[1]
while M[k] < n
	k <- k + 1
	M[k] <- max{j + A[j] | M[k-2] <= j <= M[k-1]}
return k
```

**Laufzeit:** $O(n)$, da jedes $j=1\dots n$ nur für eine der Maxima angeschaut werden muss.

Alternativ: Zeit zur Berechnung von $M[k]$ ist $O(M[k-1]-M[k-2])$
- Gesamtzeit: $O((M[1]-M[0])+(M[2]-M[1])+\dots+(M[k-1]-M[k-2]))\le O(M[k+1]-M[0])\le O(n)$ 
Es geht nicht besser (als $O(n)$), denn für manche Inputs müssen wir alles anschauen. Worst-case Laufzeit ist $\Omega(n)$ 

### Problem 3: längste gemeinsame Teilfolge

Teilfolge: Reihenfolge muss stimmen, Lücken sind ok. 

T I G E R / Z I E G E $\to$ I _ G E

**Allgemein:** Wie lang is die LGT von $A[1\dots n]$ und $B[1\dots m]$ 

#### Versuch 1

Teilproblem: LGT von $A[1\dots i]$ und $B[1\dots i]$ (Rekursion funktioniert nicht)

#### Versuch 2

Teilproblem: $L(i,j)=$ Länge einer LGT von $A[1\dots i]$ und $B[1\dots j]$

Rekursion: 
- $i=0$ oder $j=0:$ $L(i,j)=0$
- $i,j>0:$ 
	1. Möglichkeit: Benutze $A[i]$ und $B[j]$, nur falls $A[i]=B[j]$
	2. Möglichkeit: Benutze $A[i] / B[j]$ nicht

Rekursion: Falls $A[i]=B[j]$, dann $L(i,j)=\text{max}\{ 1+L(i-1,j-1), L(i-1,j) , L(i,j-1)\}$. Sonst $L(i,j)=\text{max}\{ L(i-1,j),L(i,j-1) \}$

Laufzeit: $O(n\cdot m)$ Extraplatz: $O(n\cdot m)$ (es geht nicht besser)

### Problem 4: Editierdistanz

Input: $A[1\dots n]$ und $B[1\dots m]$ String

Wir wollen $A$ in $B$ umwandeln durch
- Zeichen einfügen
- Zeichen löschen
- Zeichen ändern

Gesucht: minimale Zahl an Operationen

Teilproblem: $ED(i,j)=$ Editierdistanz zwischen $A[1\dots i]$ und $B[1\dots j]$

Rekursion: Was passiert in der optimalen Lösung mit $A[i]$? 
- Fall 1: $A[i]$ wird irgendwann gelöscht $\to$ sofort löschen
- Fall 2: $A[i]$ endet in $B[1\dots j-1]$
	- $B[j]$ wird irgendwann eingefügt $\to$ sofort machen
	- $ED(i,j)=1+ED(i,j-1)$
- Fall 3: $A[i]$ endet $B[j]$ 
	- $ED(i,j)=ED(i-1,j-1)+\begin{cases}0,\text{ falls }A[i]=B[j] \\ 1,\text{ falls }A[i]\not=B[j]\end{cases}$

Also für $i,j>0$

$ED(i,j)=\text{min}{ ED(i-1,j)+1,ED(i,j-1)+1,ED(i-1,j-1)+ \begin{cases}0,\text{ falls }A[i]=B[j] \\ 1,\text{ falls }A[i]\not=B[j]\end{cases} }$
