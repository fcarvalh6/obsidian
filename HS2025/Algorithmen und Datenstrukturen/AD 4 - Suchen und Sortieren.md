#HS2025 #AD 

**Input:** ein Array $[1,\dots,n]$ von ganzen Zahlen und ein element $b$

**Output:** Index $k$ falls $b=A[k]$ sonst "nicht gefunden"

## Fall 1: nicht sortiert

### Algo 1: Lineare Suche

```
LinearSearch(A,b)
	for i = 1 ... n
		if A[i] = b : return i
	return "nicht gefunden"
```

$\leq O(n)$

- geht nicht besser
- jedes Element muss in einem Vergleich vorkommen
- $\geq \frac{{n+1}}{2} \geq \Omega(n)$

## Fall 2: A sortiert

$A[1]\leq A[2]\leq \dots \leq A[n]$

### Algo 2: Binäre Suche

```
BinarySearch(A,b)
	if A is empty : return nicht gefunden
	m = floor((n+1)/2)
	if A[m] = b : return m
	if b < A[m] : 
		BinarySearch(A[1...m-1],b)
	else
		BinarySearch(A[m+1...n],b)
```

**Laufzeit:** $(n=2^{k})$

$$
\begin{align}
T(1)  & =   C   & \text{konstant} \\
T(n)  & = T\left( \frac{n}{2} \right)+d & \text{d konstant} \\
\implies T(n) & = C + d\cdot \log_{2}n \le O(\log n)
\end{align}
$$

**geht es besser?**
- Idee: betrachte einen beliebigen Suchalgorithmus als Entscheidungsbaum.
- Vergleiche *worst case* = n
- Anzahl Blätter $\geq n+1$
- kleinstes $h$ (Tiefe) sodass $\geq n+1$ Blätter
- Tiefe $h \implies \leq 2^{h}$ Blätter
- $n+1 \leq 2^{h}$
- $h\geq \log_{2}(n+1)\geq \Omega(\log n)$

## Sortieren

**Input:** Array $A$ der Länge $n$

**Output:** Umordnung (Permutation) $A'$ von $A$ sodass $A'$ sortiert ist. ($i<j \implies A'[i]\leq A'[j]$ für $1\leq i,j\leq n$)

### Algo 0: Prüfe Sortierheit

```
IsSorted(A)
	for i = 1...n
		if A[i]>A[i+1]
			return false
	return true
```

$\leq O(n)$

### Algo 1: BubbleSort

```
BubbleSort(A)
	for j=1...n-1
		for i=1...n-1
			if A[i] > A[i+1] : tausche A[i], A[i+1]
```

$O(n^{2})$ Vergleiche, $O(n^{2})$ Vertauschungen

### Wie beweisen wir Korrektheit?

- **Idee:** finde eine geeignete Invariante und beweise per Induktion.
- **Invariante:** $I(j)=$ Nach $j$ Iterationen sind die letzten $j$ Elemente richtig.

$$
\begin{align}
I(0) & \\
I(j-1) & \to I(j) \\
I(n-1)  & \implies \text{Korrektheit}
\end{align}
$$

**Von der Invariante zum Algorithmus:**
- gleiche Invariante 
- $I(j-1)\to I(j)$
- grösstes Element finden und tauschen
- SelectionSort

### Algo 2: SelectionSort

```
SelectionSort(A)
	for j = 1...n-1
		k = Index(Max(A[i...n-j+1]))
		tausche A[k], A[n-j+1]
```

$O(n^{2})$ Vergleiche, $O(n)$ Vertauschungen

### Algo 3: Insertion Sort

**Idee:** andere Invariante

$I(j): \mid A=[1\dots j] \mid A[j+1\dots n]$ Sortiert aber nicht unbedingt an richtiger Stelle

- Am Anfang gilt: $I(1)$
- $I(j)\to I(j+1)$
- setze $A[j+1]$ an richtige Stelle in $A[i\dots j]$

```
InsertionSort(A)
	for j = 1...n-1
		BinarySearch A[j+1] in A[1...j]
		x = A[j+1] -> Stelle k
		schiebe A[k...j] -> A[k+1...j+1]
		A[k] = x
```

$O(n\log n)$ Vergleiche, $O(n^{2})$ Vertauschungen

### Algo 4: MergeSort

**Idee:** *Divide-and-conquer*

```
MergeSort(A,left,right) //Am Anfang: left = 1, right = n
	if left < right
		middle = floor((left + right)/2)
		MergeSort(A,left,middle)
		MergeSort(A,middle+1,right)
		Merge(A,left,middle,right)
		
Merge(A,l,m,r)
	i = l
	j = m + 1
	k = l
	while i <= m und j <= r
		if A[i] < A[j]
			B[k] = A[i]
			i++
			k++
		else
			B[k] = A[j]
			j++
			k++
	end while
	
	
	//need to complete
```

$O(n\log n)$ Vergleiche, $O(n\log n)$ Bewegungen, aber $O(n)$ Extraplatz 

