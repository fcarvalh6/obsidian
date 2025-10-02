#HS2025 #AD

## Multiplikationen
- Zwei n-stellige ganze Zahlen multiplizieren: $n^{2}$ Multiplikationen.
- Es kann aber besser sein (Karatsuba-Algorithmus).
- Analyse: M(n) = Anzahl der Ziffermultiplikationen
	- Annahme: $n = 2^{2}$
	- M($2^0$) = 1
	- M($2^{k}$) = $3 \cdot M(n^{k-1})$ (Rekurrenz)
	- das ist kein Beweis

## Pasture Break
- Kurzsichtige Kuh sucht Lücke im Zaun.
- Ziel: in möglichst wenig Schritte die Lücke zu finden (k ist bekannt).
	- Eine Methode: k-Schritte nach links und dann 2k-Schritte nach Rechts (falls die Lücke nicht links war)
	- *Best Case*: Lücke wird nach k-Schritte gefunden. 
	- *Worst Case*: Lücke wird nach 3k-Schritte gefunden (am Wichtigsten).
- Ziel: in möglichst wenig Schritte die Lücke zu finden (k ist nicht bekannt).
	- Eine Methode: "Zick-zack"
	- *Worst Case*: Anzahl der Schritte $2(1+2+3+\dots+k)+k$
	- $k(k+1)+k = k(k+2)$
	- Eine andere Methode: neue Idee, die Kuh sollte mehr neue Stellen in jedem Schritt kontrollieren.
	- *Worst Case* (Annahme: $2^{i-1} < k \leq 2^{i}$ im letzten Schritt): Anzahl der Schritte = $2(1+2+2^{2}+\dots+2^{i})+k = 2(2^{i+1}-1)+k < 9k$
	- **geht es besser?**

## Algorithmus
	Vollständige Beschreibung einer Abfolge von elementaren Operationen zur Lösung eines Problems. 

## A&D 
	Entwurf und Analyse von Algorithmen, algorithmische Denkweise, wichtige Algorithmen kennenlernen.

## Beweisprinzip: Induktion

$1+2+2^{2}+\dots+2^{k-1} = 2^{k}-1$ für alle $k \in \mathbb{N}$
- Induktionsanfang: $S_{1} = 1=2^{1}-1$
- Induktionsschritt: $k \to k+1$ (was gilt für k, gilt für k+1)
	- $S_{k+1} = 1+2+2^{2}+\dots+2^{k-1}+2^{k}$
		- $= S_{k}+2^{k}$
		- =$2^{k}-1+2^{k} = 2^{k+1}-1$
- Allgemein
	- Beweise A(k) für alle $k \in \mathbb{N}$
	- Induktionsanfang (IA): zeige A(1)
	- Induktionsschritt (IS): zeige dass A(k+1) gilt falls A(k) gilt
	- Induktionshypothese: Zuhilfenahme von A(k)

## Bernoulli-Ungleichung

Für alle $x\geq-1$ und $n\in \mathbb{N}$, $(1+x)^{n}\geq1+nx$.

IA: $n=1 \quad (1+x)^{1}\geq1+1x$, die Induktionsanfang gilt.

IS: $n\to n+1\quad$
$(1+x)^{n+1}=(1+x)^{n}(1+x)$, rechte Seite kürzen
$=(1+x)^{n}\cdot(1+x)^{1}$           IH: $(1+x)^{n}\geq 1+nx$ 
$\geq (1+nx)\cdot(1+x)$            es funktioniert, weil 1+x positiv ist
$= 1+nx+x+nx^{2}$
$=1+x(n+1)+nx^{2}$         $nx^{2}\geq 0$, ohne es wird es immer kleiner
$\geq 1+x(n+1)$

## Starsuche

**Problem:** finde einen Star unter $n$ Personen $P_{1},\dots,P_{n}$

**Definition:** $P_{s}$ ist ein Star, wenn all $P_{i} \ P_{s}$ kennen und $P_{s}$ kennt keinen. 

**Elementare Operation:** frage $P_{i}$ über $P_{j}$

- Kann es sein, dass es keinen Star gibt? Ja. 
- Kann es sein, dass es genau einen Star gibt? Ja. 
- Kann es sein, dass es mehr als einen Star gibt? Nein. 

**Algorithmus (naiv):** frage Jeden über Jeden. Anzahl Fragen: $n^{2}-n$

**Algorithmus (rekursiv):**
- Idee: finde Lösung für n basierend auf einer Lösung für n-1 Personen (induktiv)
- Schritt 0: schicke eine Person raus (z.B. $P_{n}$)
- 1: finde Star $P_{s}$ unter $P_{1},\dots,P_{n-1}$ 
- 1-Ja: $P_{s}$ ist Star (gehe zu Schritt 2)
- 2: Ist $P_{S}$ auch Star unter $P_{1},\dots,P_{n}$ ($P_{s}$ und $P_{s}$ gegenseitig abfragen)
- 2-Nein: $Ps$ ist kein Star (gehe zu Schritt 3)
- 3: Ist $Pn$ Star unter Allen?
- 1-Nein: $P_{S}$ ist kein Star (gehe zu Schritt 3)
- 2-Ja: Fertig.

**F(n) = Anzahl Fragen**
- Schritt 0: 0
- 1: F(n-1)
- 2: 2
- 3: 2(n-1)

**Analysis:**
- Best Case: nie Schritt 3
	- $F(n) = F(n-1)+2$
	- $F(2)=2$