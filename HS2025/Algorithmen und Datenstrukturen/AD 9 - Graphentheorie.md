#HS2025 #AD 

## Königsberger Brückenproblem

Königsberg wird durch einen Fluss in 4 Teile geteilt, $n$ Brücken, wäre es möglich, alle Brücken nur einmal zu überqueren? 

Problem abstrahieren: Stadtteile $A, \ B, \ C, \ D$, Brücken als Linien zwischen den Buchstaben. Das ist ein Graph mit Knoten $A,B,C,D$ und Kanten (Knotenverbindung). 

Eulerweg: durchlaufe jede Kante genau einmal.

**Knotengrad:** Anzahl anliegender Kanten. 

**Behauptung:** falls ein Eulerweg existiert, dann $\le 2$ Knoten ungerade.

\# hin + \# weg = Knotengrad

Ausser für Start- oder Endknoten: \# hin = \# weg 

## Haus vom Nikolaus

Zeichnen mit 8 Linien ohne absetzen. 

## Eulerweg finden

**Brute-force:** alle Kantenreihenfolgen probieren, Laufzeit $\ge\Omega(m!)$ 

Geht es besser? Ja, $O(n+m)$.

### Hamiltonpfad

Durchlaufe jeden Knoten genau einmal.

**Brute-force:** alle Knotenreihenfolgen probieren, Laufzeit $\ge \Omega(n!)$

Geht es besser? Polynomielle Laufzeit ist unmöglich unter $P\not=NP$ Vermutung.

## Definition von einem Graph

$G:(V,E)$
- Knotenmenge $V$
- Kantenmenge $E$, jede Kante ist ungeordnetes Paar zweier Knoten $u,v\in V, u\not=v$ 

**Begriffe:** benachbart/adjazent; anliegend/inzident 

$\text{deg}(u)=\text{Knotengrad von } u$

**Handschlaglemma:**

$$
\sum_{u\in V} \text{deg}(u)=2|E|
$$

**Weg:** Folge von benachbarten Knoten

**Pfad:** Wege ohne wiederholte Knoten

**Zyklus:** Weg mit $V_{0}=V_{e}$ und $l\ge 2$

**Beobachtung:** Weg ist Zyklus $\iff$ Endknoten inzident zu geraden Anzahl Kanten im Weg

$u$ **erreicht** $v$: $\exists$ Weg zwischen $u$ und $v$. Äquivalenzrelation. Zusammenhangskongruenten (Äquivalenzklassen)

**Graph Zusammenhängen:** genau eine ZHK jeder Knoten erreicht jeden anderen.

**Euler Zyklus:** Zyklus mit allen Knoten genau einmal. 

**Behauptung:** in zusammenhängenden Graph: $\exists$ Eulerzyklus $\iff$ alle Knotengrade gerade

Beweis: "$\implies$" wie für Eulerweg. "$\impliedby$" per Algorithmus

## Algorithmus

**Ansatz:** berechne Zyklen, mit jeder Kante genau einmal. 