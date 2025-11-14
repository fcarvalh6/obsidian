#HS2025 #DM 

**Schreibweise:** $a^{n}\stackrel{\text{ def.}}= \underbrace{a*a*\dots*a}_{n}, \quad a^{0}\stackrel{\text{ def.}}= e, \quad a^{-1}=\hat{a},\quad a^{-n}=(a^{-1})^{n}$ 

$|G|$ - Ordnung von Gruppe $\langle G;* \rangle$ (in $\mathbb{N}$ oder $\infty$) 

Für $a\in G$ ist $\operatorname{ord}(a)=\operatorname{min}\{ n\ge 1\mid a^{n}=e\}\cup \{ \infty \}$

**Beispiele:** $|\mathbb{Z}_{7}|=7, \ \operatorname{ord}(1)=7, \ \operatorname{ord}(2)=7$

$|\mathbb{Z}_{6}|=6, \ \operatorname{ord}(2)=3$

$|\mathbb{Z}_{7}^{*}|=6, \ \operatorname{ord}(1)=1, \ \operatorname{ord}(2)=3, \ \operatorname{ord}(3)=6$ 

$|\mathbb{Z}_{2}\times \mathbb{Z}_{2}|=4 \ \operatorname{ord}((1,1))=2$

$|\mathbb{Z}|=\infty, \  \operatorname{ord}(1)=\infty$

**Lemma 5.6:** In endlicher Gruppe $G$ hat jedes $a\in G$ endliche Ordnung

Beweisidee: Betrachte $a,a^{2},a^{3},\dots$ . Es existieren $r,s\in \mathbb{N}$ mit $a^{r}=a^{s}$ und $r<s$. Dann gilt $a^{-r}*a^{r}=a^{-r}*a^{s}$. Also $\operatorname{ord}(a)\le s-r.$ 

**Beobachtung:** $a^{m}=a^{m+\operatorname{ord}(a)}$, also $a^{m}=a^{R_{\operatorname{ord}(a)}(m)}$, falls $\operatorname{ord}(a)<\infty$ 

**Schreibweise:** $\langle a \rangle\stackrel{\text{ def.}}= \{ a^{n}\mid n\in \mathbb{Z} \}$ 

**Beispiele:** $\mathbb{Z}=\langle 1 \rangle,\ \mathbb{Z}_{m}=\langle 1 \rangle, \ \mathbb{Z}_{7}^{*}=\langle 3 \rangle$ 

$G$ zyklisch, falls $G=\langle a \rangle$ für geeignetes $a\in G$

$|G|=n<\infty$ und $G=\langle a \rangle\implies \Psi: \mathbb{Z}_{m}\to G$ Isomorphismus $1\mapsto a$ 

**Theorem 5.8:** Für Gruppe $G$ mit $|G|=n<\infty$ mit Untergruppe $H,|H|=m$, gilt $m\mid n$ 

$\mathbb{Z}_{p}, p\text{ prim }$ wird von jedem $a\in \mathbb{Z}_{p}\setminus \{ 0 \}$ erzeugt (d.h. $\mathbb{Z}_{p}=\langle a \rangle$). 

Beweis: betrachte $H_{0}=H=\{ h_{1},\dots,h_{m} \}$. Falls $m=n$, fertig. Sonst wähle $g_{1}\in G\setminus H_{0}$, und setze $H_{1}=H_{0}\cup \{ g_{1}*h_{1},g_{1}*h_{2},\dots,g_{1}*h_{m} \}$. $|H_{1}|=|H_{0}|+m$, weil $g_{1}*h_{i}\not= g_{1}*h_{j}$ für $h_{i}\not=h_{j}$ und $g_{1}* h_{i} \not\in H_{0}$ weil $g_{1}\not\in H_{0}$. 

Falls $H_{1}=G$, fertig (dann wäre $n=2m$ und $m\mid n$). Sonst wähle $g_{2}\in G\setminus H_{1}$ und fahre fort. Es folgt (nach $k$ Schritten) dass $n=k\cdot m$ 

**Beobachtung:** $|G|$ prim $\implies G$ zyklisch

**Def.** $\varphi(m)=|\mathbb{Z}_{m}^{*}|$

Beispiel: $\varphi(11)=10, \ \varphi(12)=4$. $p$ prim $\implies \varphi(p)=p-1,\ \varphi(p^{i})=p^{i}-\frac{p^{i}}{p}=p^{i-1}(p-1)$ 

$\operatorname{gcd}(p,q)=1 \implies \varphi(p\cdot q)=\varphi(p)\cdot\varphi(q)$ 

**Korollar:** für $m\ge 2$ und $\operatorname{gcd}(a,m)=1$ gilt $a^{\varphi(m)}\equiv_{m}1$ 

**RSA:** Betrachte $n=p\cdot q$, beide prim und $d,e=\mathbb{Z}^{*}_{\varphi(n)}$ mit $d\cdot e\equiv_{\varphi(n)} 1$. Es gilt $a^{e\cdot d}\equiv_{n}a^{k\cdot\varphi(n)-1}\equiv_{n} a$.

Idee: nutze $n,e$ für die Verschlüsselung, $n,d$ für Entschlüsselung. 