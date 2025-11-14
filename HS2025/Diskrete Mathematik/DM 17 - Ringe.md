#HS2025 #DM 

**Definition:** Ring $\langle R;+,-,0,\cdot,1 \rangle$ erfüllt:
1. $\langle R;+,-,0 \rangle$ kommutative Gruppe
2. $\langle R;\cdot,1 \rangle$ Monoid
3. $\forall a,b\in R\qquad a(b+c)=ab+ac\land (b+c)a=ba+ca$ 

Beispiele: $\mathbb{Z},\mathbb{Q},\mathbb{R},\mathbb{C},\mathbb{Z}^{2\times2}(\text{nicht kommutativ})$ $\langle \mathbb{Z}_{m};\oplus_{m},\ominus_{m},0,\odot_{m},1 \rangle$

**Lemma 5.17:** Für jeden Ring $\langle R;+,-,0,\cdot,1 \rangle$ und beliebige $a,b\in R$ gilt:
1. $0\cdot a=a\cdot 0 = 0$
2. $(-a)b=-(ab)$ 
3. $(-a)(-b)=ab$ 
4. $|R|=1\iff 1 = 0$ 

**Def.:** Charakteristik von Ring $R$ ist $\operatorname{min}\{ i \in \mathbb{N} \mid i>0 \land \underbrace{1+1+\dots+1}_{i-mal}=0 \}$ oder $0$ 
Beispiel: Char. von $\mathbb{Z}$ ist $0$, Char. von $\mathbb{Z}_{m}$ ist $m$.

**Def.:** In Ring $R$ ist $a \in R$ eine Einheit, falls ein $b\in R$ existiert mit $a\cdot b=b\cdot a=1$. Schreibe $b=a^{-1}$ 

Beispiel: $\mathbb{Z}_{m}$ hat Einheiten $\{ a \in R\setminus\{ 0 \}\mid \operatorname{gcd}(a,m)=1 \}$ 

Def.: $R^{*}\stackrel{\text{def}}=\{ a \in R \mid a \text{ Einheit} \}$. 

**Lemma:** $\langle R^{*};\cdot,(\cdot)^{-1},1 \rangle$ Gruppe.

### Beispiele für Konstruktion von Ringen (aus gegebenen Ringen)

$R'=\langle R\times R;+,-,(0,0),*,(1,0)\rangle$
- $(a,b)+(c,d)=(a+c,b+d)$
- $(a,b)*(c,d)=(ac-bd,ad+bc)$
- Komplexe Zahlen

$R''=\langle R^{*}\text{ (endliche Folgen)};+,-,\varepsilon,*,(1)\rangle$
- $(f_{0},\dots,f_{n})+(g_{0},\dots,g_{m})\stackrel{\text{def}}=(f_{0}+g_{0},\dots,f_{n}+g_{n},g_{n+1},\dots)(n\le m)$ 
	- wobei 0-Einträge am Ende weggelassen werden
- $(f_{0},\dots,f_{n})*(g_{0},\dots,g_{m})\stackrel{\text{def}}=(f_{0}g_{0},f_{1}g_{0}+f_{0}g_{1},+\dots)$
- Polynome

**Bemerkung:** Teilbarkeit wie üblich definiert. 
- **Definition:** Ein $a \in R\setminus \{ 0 \}$ heisst Nullteiler, falls $b \in R\setminus \{ 0 \}$ existiert mit $a\cdot b=0$
- Beispiel: 2 in $\mathbb{Z}_{2m}$ ist Nullteiler
- Enthält $R$ keine NT, so heisst $R$ Integritätsbereich ($\mathbb{Z},\mathbb{Q},\mathbb{R},\mathbb{C}$)