#HS2025 #AD 

## Sorting

| Algorithmus   | Vergleiche   | Bewegungen   | Extraplatz | Lokalität |
| ------------- | ------------ | ------------ | ---------- | --------- |
| BubbleSort    | $O(n^{2})$   | $O(n^{2})$   | $O(1)$     | gut       |
| SelectionSort | $O(n^{2})$   | $O(n)$       | $O(1)$     | gut       |
| InsertionSort | $O(n\log n)$ | $O(n^{2})$   | $O(1)$     | gut       |
| MergeSort     | $O(n\log n)$ | $O(n\log n)$ | $O(n)$     | gut       |

### Algo 5: QuickSort

MergeSort
- Aufteilen
- Sortiere links und rechts
- Merge (+Arbeit +Extraplatz)

**Idee:** Schiebe Arbeit ins Aufteilen
- Aufteilen und Arbeit
- Rekursion links und rechts

```
QuickSort(A,l,r)
	if l < r
		k = Aufteilen(A,l,r) //wähle p und setze an richtige Stelle
	QuickSort(A,l,k-1)
	QuickSort(A,k+1,r)
	
Aufteilen(A,l,r)
	i = l, j = r-1, p = A[r]
	repeat
		while i < r und A[i] < p : i++
		while j > l und A[j] > p : j++
		if i < j : tausche A[i], A[j]
	until i >= j
	tausche A[i], A[r]
	return i
```

Laufzeit: $T(n)=C\cdot n+T(n)+T(n-k)$, nicht gut analysierbar

- gut: $T(n)=2T\left( \frac{n}{2} \right)+C\cdot n \le O(n\log n)$   (oft)

- schlecht: $T(n)=T(n-1)+C\cdot n\le O(n^{2})$   (selten, wenn bereits sortiert)

### Algo 6: Heap Sort

SelectionSort nochmal von rechts nach links. 

**Problem:** `max(Rest)` finden.

**Idee:** Datenstruktur die `max` billiger macht.

**Hoffnung:** `max` in $O(\log i) \quad \sum_{i=2}^na\log(i)\le O(n\log n)$

**Lösung:** Max-Heap (Heapbedingung: für alle Knoten: Schlüssel Knoten > Schlüssel Kinder.)
- Max ist immer die Wurzel.

Max-Heap im Array: $[87,72,85,10,8,80,3,7,1,2,4,70]$

Heapbedingung: für alle $k\in \{ 1,\dots,n \}:$ 
- $2k \le n \implies A[2k]\le A[k]$
- $2k+1\le n \implies A[2k+1]\le A[k]$

Weitere Eigenschaften: 
- Tiefe = $\lfloor \log_{2}n \rfloor$
- Anzahl Blätter = $\left\lceil  \frac{n}{2}  \right\rceil$
- Voller Binärbaum

**Heapbedingung Herstellen:** Versickere Schlüssel an der Wurzel durch wiederholtes Tauschen mit grösseren Kind bis beide Kinder kleiner sind. $O(\log n)$ Vergleiche, Täuschungen.

```
RestoreHeapCondition(A,k,i)
	versickert k-te Element in A[1...i]
```

```
HeapSort(A)
	for i = floor(n/2)...1
		RestoreHeapCondition(A,i,n)
		
	for i = n...2 //absteigend
		tausche A[1], A[i]
		RestoreHeapCondition(A,1,i-1)
```

$O(n\log n)$ Laufzeit, kein Extraplatz, schlechte Lokalität

## Datenstrukturen

### Abstrakter Datentyp
- ADT: Objekte + Operationen
- Objekte: Daten, bei uns Schlüssel $\in \mathbb{N}$
- Operationen: die die man auf den Daten ausführen will
- Datenstruktur: Implementierung eines ADT

### ADT Liste

Enthält Objekte/Schlüssel in fester Reihenfolge

**Operationen (Auswahl)**
1. `insert(k,L)`: fügt ein neues Objekt mit Schlüssel `k` am ende der Liste `L` ein.
2. `get(i,L)`: gebe `i`-tes Element von `L` aus.
3. `delete(o,L)`: lösche Objekt `o` aus `L`
4. `insertAfter(o,k,L)`: füge neues Objekt mit Schlüssel `k` hinter `o` in `L` ein. 

**Datenstrukturen**
1. Array (falls max. Länge bekannt)
2. Einfach verkettete Liste
3. Doppelt verkettete Liste


| Datenstruktur            | insert      | get         | insertAfter | delete      |
| ------------------------ | ----------- | ----------- | ----------- | ----------- |
| Array                    | $O(1)$      | $O(1)$      | $O(n)$      | $O(n)$      |
| einfach verkettete Liste | $O(n)$      | $O(n)$      | $O(1)$      | $O(n)$      |
| doppelt verkettete Liste | $O(1)$      | $O(n)$      | $O(1)$      | $O(1)$      |
| Suchbaum                 | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ |
