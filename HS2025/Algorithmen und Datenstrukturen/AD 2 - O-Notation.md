#HS2025 #AD 

## Starsuche
- Naiver-Algorithmus
- Induktiver-Algorithmus

**Idee:** stelle sicher keinen Star rauszuschicken. 
- Neues Schritt 0 ($Pi$ fragt $Pj$)
	- Ja, $Pi$ ist kein Star
	- Nein, $Pj$ ist kein Star
- dann Schritt 3 löschen

$F(n) = F(n-1)+3$
$= 3n -4$

- viel besser als $n^{2}-n$
## Algorithmen Vergleichen

- Korrektheit (braucht Beweis)
- Laufzeit, hängt ab von
	- Eingabegrösse
	- Computer
	- Implementierung
- Wir brauchen ein Laufzeitmodell, dass davon abstrahiert
	1. Unit-cost Random Access Machine (RAM) Modell
	2. Asymptotische Notation

### RAM-Modell

- Speicher mit Zellen
- Prozessor (führt elementare Operationen aus)
	- lesen/schreiben einer Zahl
	- Arithmetik
	- Vergleiche
	- und viele mehr
- Laufzeit = Anzahl elementarer Operationen
	-  Unterschied zwischen Laufzeit in Praxis ist ein konstanter Faktor

**Universelle Laufzeitanalyse**
- ignoriere Konstante Faktoren
- betrachte nur Wachstum (z.B. $n^{2}$ statt $n$)
$$
n^{2}-n \to n^{2} \qquad 7n+\log n \to n
$$
### Asymptotische Notation 

$N=\{ n_{0},n_{0} +1,\dots\}$ Menge möglicher Eingabegrössen

**Definition:** für $f: \mathbb{N}\to \mathbb{R}^{+}$, $O(f) = \{ g: N\to \mathbb{R}^{+}| \text{ es gibt } C>0 \text{ sodass }g(n)\leq C\cdot f(n) \text{ für alle }n\in N \}$

$O(f)$: "Ordnung von f"

$g\in O(f) \iff \frac{g(n)}{f(n)}\leq C$ (beschränkt)

Warum $N$ und nicht $\mathbb{N}$?

$f(n)=n^{2}-3n \qquad n_{o}=4$
$f(n)=\log \log n\qquad n_{0}=1$ geht nicht 
Anfang ist egal!

#### Beispiele:

1. 
$f(n)=n^{2}, g(n)= 4n^{2}$

$f\in O(g)?$
$n^{2}\leq 4n^{2}$ gilt für $C=1$

$g\in O(f)?$
$4n^{2}\leq 4n^{2}$ gilt für $C=4$

**allgemein:** $a\in \mathbb{R^{+}}$ konstant
$O(f(n))=O(a\cdot f(n))$

2. 
$f(n)=100n, g(n)=n^{2}, n_{0}=1$
$f\in O(g): 100n \leq n^{2}, n\geq 1$

$O(n):$ "Menge aller Funktionen die höchstens quadratisch wachsen"

**Nützliches Werkzeug**

Grenzwerte: 
$$
\lim_{ n \to \infty } \frac{g(n)}{f(n)}= \infty \implies g\not\in O(f) 
$$
$$
\lim_{ n \to \infty } \frac{g(n)}{f(n)}\in \mathbb{R^{+}}\implies g\in O(f)
$$

3. 
$f(n)=n^{1.6}+3n+4\in O(n^{1.6})?$
$$
\frac{f(n)}{g(n)}= 1+3n^{-0.6} +4n^{-1.6} \to_{n\to \infty} 1
$$
$$
\frac{f(n)}{g(n)}\leq 1+3+4 = 8
$$
4. 
$0.001n^{2}\in O(n)?$
$$
\lim_{ n \to \infty } \frac{0.001n^{2}}{n}=\infty 
$$
5. 
Sei $a>0$
$\ln n\in O(n^{a})$
$$
\lim_{ n \to \infty } \frac{{\ln n}}{n^{a}}=\lim_{ n \to \infty } \frac{{\frac{1}{n}}}{an^{a-1}} = \lim_{ n \to \infty } \frac{1}{an^{a}}=0
$$

**allgemein:** $n^{a}\in O(e^{n}), a>0$
$$
\lim_{ n \to \infty } \frac{{n^{a}}}{e^{n}} = \lim_{ n \to \infty } \frac{an^{a-1}}{e^{n}} = \dots = 0
$$
