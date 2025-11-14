#HS2025 #DM 

## Monoide und Gruppen

$\langle \mathbb{R};\cdot \rangle$ Monoid (Assoziativität, neutrales Element), keine Gruppe (0 hat kein Invers)

$\langle \mathbb{Q}\setminus\{ 0 \} ; \cdot\rangle$ Monoid und Gruppe

$\langle P(\mathbb{N});\cap \rangle$ Monoid, aber keine Gruppe

$\langle \mathbb{Z};- \rangle$ kein Monoid und keine Gruppe

Lemma 5.3 (i): Sei $\langle G,*,\hat{},e \rangle$ eine Gruppe, $a\in G:\hat{\hat{a}}=a$

$$
\hat{\hat{a}}=\hat{\hat{a}}*e = \hat{\hat{a}}*(\hat{a}*a)=(\hat{\hat{a}}*\hat{a})*a=e*a=a
$$

## Group Proof

Zeige $\langle M;*,\hat{},e \rangle$ ist eine Gruppe

**Neutrales Element:** Sei $x\in M$ beliebig, zeige $x*e=x$ und $e*x=x$

**Assoziativität:** Seien $x,y,z\in M$ beliebig, Zeige $(x*y)*z=x*(y*z)$

**Inverses:** Sei $x\in M$ beliebig. Zeige es gibt $\hat{x}\in M$ mit $x*\hat{x}=e$ und $\hat{x}*x=e$

Beispiel: Sei $M=\mathbb{Q}\times(\mathbb{Q}\setminus\{ 0 \}),$ zeige $\langle M;* \rangle$ mit $(a,b)*(c,d)=(a+b,b\cdot d)$ ist eine Gruppe. 
- **NE:** Das neutrale Element ist $e=(0,1)$. Sei $(x,y)\in M$ beliebig. Wir haben $(x,y)*e=(x,y)*(0,1)=(x+0,y\cdot 1)=(x,y)$ 
- **A:** Seien $(a,b),(c,d),(e,f)\in M$ beliebig. Dann 
$$
((a,b)*(c,d))*(e,f)=(a+c,b\cdot d)*(e,f)=(a+c+e,b\cdot d\cdot f)
$$
und
$$
(a,b)*((c,d)*(e,f))=(a,b)*(c+e,d\cdot f)=(a+c+e,b\cdot d\cdot f)
$$
- **I:** Sei $(x,y)\in M$ beliebig. Sei $(a,b)=\left( -x, \frac{1}{y} \right)$
$$
(x,y)*(a,b)=(x,y)*\left( -x, \frac{1}{y} \right)=\left( x+(-x),y\cdot \frac{1}{y} \right)=(0,1)=e
$$

## Isomorphismus

Ist $\langle \mathbb{Z}_{4};\oplus_{4} \rangle \simeq \langle \mathbb{Z}_{2}\times \mathbb{Z}_{2};\oplus_{4} \rangle$ ?

## Homomorphismus

$\varphi:\mathbb{Z}\to\mathbb{Z}_{2}$ 

$\varphi(a+b)=\varphi(a)\oplus_{2}\varphi(b)$ 

$\varphi(x)=\begin{cases}0,\text{ falls }x\text{ gerade} \\ 1,\text{ falls }x\text{ ungerade}\end{cases}$        $\varphi(x)=R_{2}(x)$ 

$\varphi(x+y)=R_{2}(x+y)=R_{2}(R_{2}(x)+R_{2}(y))=\varphi(x)\oplus\varphi(y)$ 

**Aussage:** alle Funktionen $\varphi:G\to G$ sind homomorph (falsch).
- Gegenbeispiel: $|x|:\mathbb{R}\to\mathbb{R}$ 

## Teilgruppen

Zeige: $H$ ist Teilgruppe von $G$
1. Abgeschlossen unter Operation $x,y\in H\implies x*y\in H$
2. Neutrales Element $e\in H$
3. Inverses $x\in H\implies \hat{x}\in H$

Sei $\langle G;*,\hat{},e \rangle$ eine Gruppe und sei $H=\{ a\in G\mid \forall b\in G\ a*b=b*a \}$. Zeige $H$ ist Teilgruppe. 

1. Seien $a,a'\in H$ und $b\in G$ beliebig. 
$$
(a*a')*b=a*(a'*b)=a*(b*a')=(a*b)*a'=(b*a)*a'=b*(a*a')
$$
Also haben wir $(a*a')\in H$

2.  Sei $b\in G$ beliebig
$$
e*b=b=b*e
$$
Also haben wir $e\in H$

3. Seien $a\in H,b\in G$ beliebig. 
$$
\hat{a}*b=(\hat{a}*b)*(a*\hat{a})=\hat{a}*(b*a)*\hat{a}=\hat{a}*(a*b)*\hat{a}=e*b*\hat{a}
$$
Also $\hat{a}\in H$ 