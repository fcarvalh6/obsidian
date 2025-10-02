#HS2025 #DM

Übungsblätter immer am Freitag, eine von der Übungen kann Bonuspunkte geben.

## Aussagen

S = "101 ist eine Primzahl" 
- diese Aussage **gilt** oder **gilt nicht**
T = "Es gibt unendlich viele Primzahlzwillinge"
- diese Aussage **gilt** oder **gilt nicht**
- man weiss nicht, ob sie gilt

### Implikation

$T \implies S$

- Wenn die linke Seite gilt, gilt auch die rechte Seite.
- S ist immer wahr
- T weiss man nicht
- daraus folgt, dass die Implikation wahr ist, wegen diese zwei Möglichkeiten
	- T ist wahr, und daraus folgt, dass S auch wahr ist
	- T ist nicht wahr, und es gibt keine Implikation

### Schachbrett-Beispiel

**P(k)** = "Ein Schachbrett auf dem ein Beliebiges Feld blockiert ist, kann vollständig mit L-förmigen Bausteinen überdeckt werden ohne Überlappung"

Was wäre P(8)?

#### Strukturieren

- Wenn die Anzahl der verbleibende Felder durch 3 nicht teilbar ist, ist die Aussage falsch. **Theorem:** $k^{2}-1 \not\equiv_{3} 0 \implies P(k) = 0$
	- **Bessere Formulierung:** $3 | k \implies P(k) =0$
- P(n)
	- P(1) = 1, es gibt nur ein Feld und es wird blockiert
	- P(2) = 1, egal welches Feld man blockiert, sind 3 Felder übrig die ein L formieren. 
	- P(3) = 0, laut das Theorem
	- P(4) = 1, 4 Quadranten, das Quadrant des blockierten Feldes wird überdeckt wie in der Aussage P(2) und einen Baustein wird gelegt, sodass ein Quadrat liegt auf einem Quadrant, die übrige Quadranten werden überdeckt wie in P(2).
- **Theorem:** $P(k) = 1 \implies P(2k) = 1$ (gilt für jedes K)
	- **Beweisskizze:** %

### Schokolade-Beispiel
%

&Vollständige Induktion
## Ungültige Beweise

- **Theorem:** Wenn in einer Menge P von n Planeten ein Planet bewohnt ist, so sind es alle Planeten in P. 
- **Beweis:** vollständige Induktion
	- n = 1, gilt
	- n $\to$ n+1. Seien n Planeten $p_{1}, p_{2}, \dots, p_{n}$ gegeben, wobei $p_{1}$ bewohnt sei. Dann sind nach Voraussetzung $p_{1}, p_{n}$ und $p_{1},p_{3},p_{4},\dots p_{n+1}$.
