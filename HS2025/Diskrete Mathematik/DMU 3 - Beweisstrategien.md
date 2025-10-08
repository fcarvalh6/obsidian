#HS2025 #DM 

## Case Distinction
- Beweise, dass $3n^{2}+n+14$ für alle $n\in \mathbb{Z}$ gerade ist.
	- wir betrachten zwei Fälle, $n$ gerade und $n$ ungerade
	- **Case 1:** $n$ ist gerade, also $n = 2k$ für ein $k\in \mathbb{Z}$
	- $3n^{2}+n+14=3(2k)^{2}+2k+14=12k^{2}+2k+14=2(6k^{2}+k+7)$
	- Also ist $3n^{2}+n+14$ gerade.
	- **Case 2:** $n$ ist ungerade, also $n=2k+1$ für ein $k\in \mathbb{Z}$
	- $3n^{2}+n+14=3(2k+1)^{2}+2k+1+14=12k^{2}+14k+18=2(6k^{2}+7k+9)$
	- Also ist $3n^{2}+n+14$ auch gerade.
	- Da $3n^{2}+n+14$ in beiden Fällen gerade ist, ist $3n^{2}+n+14$ somit für alle $n\in \mathbb{Z}$ gerade

## Soundness of a Proof Pattern
- Wir beweisen eine Aussage S in 3 Schritten
	1. Finde eine passende mathematische Aussage U
	2. Beweise, dass U falsch ist
	3. Beweise U unter der Annahme, dass S falsch ist
- Formuliere eine Aussage in der Form $F\vDash G$, welche die Korrektheit des proof patterns beschreibt. 
- $\neg B\land(\neg A\to B)\vDash A$
- Beweise oder widerlege die Korrektheit des *proof Pattern*.

## Proof by Contradiction
- Es gibt keine kleinste positive rationale Zahl
- Wir nehmen an, dass es eine kleinste positive rationale Zahl $q\in \mathbb{Q}$ gibt.
- Aber $\frac{q}{2}$ ist positiv, rational und kleiner als $q$. Also haben wir einen Widerspruch.