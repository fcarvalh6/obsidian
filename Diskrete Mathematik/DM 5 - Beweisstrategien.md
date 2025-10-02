#HS2025 #DM 

**Wichtig:** wenn die Interpretation klar ist, dann kann die Prädikatlogische-Formel als Aussage interpretiert werden.

**Schon gesehen:** Modus Ponens (begründet durch $\vDash (F\land(F\to G))\to G$)

## Beweise für Implikationen $S\implies T$

**Durch Transitivität:** finde $R$ mit $S\implies R$ und $R\implies T$
- Begründung: $(F\to G)\land (G\to H)\vDash F\to H$
- Variante: finde $R_{1},R_{2}$ mit $S\implies R_{1}$ und $S\implies R_{2}$ und $R_{1} \text{ und } R_{2}\implies T$

**Direkter Beweis** (von $S\implies T$): nimm $S$ als wahr an, beweise $T$ unter dieser Annahme.
- Beispiel - Lemma: wenn $a,b$ Quadratzahlen sind ($S$), dann ist $ab$ auch Quadratzahl ($T$).
	- Beweis: es existieren $u,v$ mit $a=u\cdot u$ und $b=v\cdot v$ (Annahme $S$)
		- $\dot\implies a\cdot b = (u\cdot u)(v\cdot v)$
		- $\dot\implies a\cdot b = u(u\cdot v)v$             (Assoziativität)
		- $\dot\implies a\cdot b=u(v\cdot u)v$             (Kommutativität)
		- $\dot\implies a\cdot b=(u\cdot v)(u\cdot v)$        (Assoziativität)
		- $\dot\implies$ es existiert $w$ mit $a\cdot b=w\cdot w\dot\implies a\cdot b$ ist Quadratzahl

**Indirekter Beweis** (von $S\implies T$): nimm $T$ als falsch an, zeige, dass S falsch ist.
- Begründung: $(\neg G \to \neg F) \vDash F\to G$
- Beispiel - Lemma: die Wurzel einer irrationalen Zahl $x>0$ ist irrational
	- Beweis - S: $x>0$ irrational - T: $\sqrt{ x }$  irrational
		- $\sqrt{ x }$  rational $\dot\implies$ es existiert $m,n\in \mathbb{Z}$ mit $\sqrt{ x }=\frac{m}{n}$        ($\neg T$)
		- $\dot\implies x=\frac{m^{2}}{n^{2}}$                                                                       ($\neg S$)

**Beweise für allgemeinere Aussagen**
- Modus Ponens
- Fallunterscheidung (Verallgemeinerung von Modus Ponens)
	- finde $R_{1},\dots, R_{n}$, beweise, dass $R_{1}$ oder $R_{2}$ oder $R_{n}$ gilt, beweise, dass für alle i gilt: $R_{i}\implies S$.
	- $n=1$: Modus Ponens
- Beweis durch Widerspruch: finde $T$, beweise, dass $T$ falsch ist, beweise dass $S$ falsch $\implies$ T wahr
	- Begründung: $(\neg F \to G)\land \neg G \vDash F$
	- Beispiel - Lemma $\sqrt{ 2 }$ irrational
		- Beweis: $\sqrt{ 2 }$ rational $\dot\implies \sqrt{ 2 }=\frac{m}{n} \text{ mit } ggT(m,n)=1 \dot\implies 2 = \frac{m^{2}}{n^{2}}$
		- $\dot\implies m^{2}=2n^{2}\dot\implies 2 |m^{2} \dot\implies 2|m\dot\implies4|m^{2}\dot\implies 4|2n^{2}$
		- $\dot\implies 2|n^{2}\dot\implies 2|n\dot\implies ggT(m,n) \geq 2$, falsch

**Beweise für Aussagen der Form** $\forall n \; P(n) (\text{Universum } U=\mathbb{N})$
1. Beweise $P(0)$ wahr
2. Beweise für alle $n$, dass $P(n)\implies P(n+1)$ 
- Begründung: für $U=\mathbb{N}$ und beliebiges Prädikat $P$ gilt:
	- $P(0)\land \forall n(P(n)\to P(n+1))\vDash\forall nP(n)$
	- 