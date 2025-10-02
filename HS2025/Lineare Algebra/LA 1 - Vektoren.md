#HS2025 #LA

Übungsserien
- Ausgabe am Mittwoch, eine Woche Bearbeitungszeit. Abgabe durch Moodle. 

Bonusaufgaben
- Aufschaltung am Mittwoch, eine Woche Bearbeitungszeit, automatisch korrigiert.
- Viermal im Semester: *schriftliche* Bonusaufgaben

## Vektoren (Kapitel 1)

**Def 1.1** Sei $m \geq 0$ eine natürliche Zahl. Ein m-dimensionaler (Koordinaten-) Vektor ist ein Element von $\mathbb{R}^{m}$. $m \in \mathbb{N}= \{0,1,2,\dots\}$
- Zeichnung als Pfeil oder Punkt

### Vektoraddition: kombiniere die Bewegungen

$$
\begin{pmatrix}
2  \\
3
\end{pmatrix} + \begin{pmatrix}
3 \\
-1
\end{pmatrix}=
\begin{pmatrix}
5 \\
2
\end{pmatrix}
$$
**Def 1.2**: Sei $m \in \mathbb{N}$. Seien:
$$
v = \begin{pmatrix}
v_{1}  \\
v_{{2}} \\
\vdots \\
v_{3}
\end{pmatrix}, w = \begin{pmatrix}
w_{1}  \\
w_{{2}} \\
\vdots \\
w_{3}
\end{pmatrix} \in \mathbb{R}^{m}. \space \text{Der Vektor  } \mathbf{v+w} = \begin{pmatrix}
v_{1} + w_{1} \\
v_{2} + w_{2}  \\
\vdots \\
v_{m} + w_{m}
\end{pmatrix}
\in \mathbb{R}^{3} \text{ ist die Summe von v und w}
$$

Mehr Vektoren. $\mathbf{u} +\mathbf{v} +\mathbf{w}$ ist die Summe von drei Vektoren.

### Skalarmultiplikation: gehe $\lambda$-mal so weit

$$
3 \begin{pmatrix}
2 \\
1
\end{pmatrix} = \begin{pmatrix}
6 \\
3
\end{pmatrix}
\quad (-2)\begin{pmatrix}
2 \\
1
\end{pmatrix} = \begin{pmatrix}
-4 \\
-2
\end{pmatrix}
$$


**Def 1.3** 
$$
\text{Sei: }
v = \begin{pmatrix}
v_{1} \\
v_{2} \\
\vdots \\
v_{m}
\end{pmatrix} \in \mathbb{R}^{m}, \lambda \in \mathbb{R}.
\text{Der Vektor } \lambda \mathbf{v} = \begin{pmatrix}
\lambda \mathbf{v_{1}} \\
\lambda \mathbf{v_{2}} \\
\vdots \\
\lambda \mathbf{v_{m}}
\end{pmatrix}
\in \mathbb{R}^{m} \text{ ist ein skalares vielfaches von v}
$$


### Linearkombination

**Def 1.4**

$$
\text{Seien }v, w\in \mathbb{R}^{m}, \lambda, \mu \in \mathbb{R}. \text{Dann ist } \lambda v+\mu w \in \mathbb{R}^{m} \text{ eine Linearkombination von }v \text{ und }w
$$

$$
\text{Falls } v_{1}, v_{2}, \dots v_{n} \in \mathbb{R}^{m} \text{ und } \lambda_{1}, \lambda_{2}, \dots, \lambda_{n} \in \mathbb{R}, \text{dann ist}
$$
$$
\lambda_{1}v_{1} +\lambda_{2}v_{2} + \dots + \lambda_{n}v_{n} \text{ eine Linearkombination von } v_{1}, v_{2}, \dots v_{n}
$$
#### Beispiel
$$
v = \begin{pmatrix}
2 \\
3
\end{pmatrix}, w = \begin{pmatrix}
3 \\
-1 \\
\end{pmatrix}
$$

| $\lambda$ | $\mu$ | $\lambda$v                             | $\mu w$                               | $\lambda v + \mu w$                    |
| --------- | ----- | -------------------------------------- | ------------------------------------- | -------------------------------------- |
| $-3$      | $2$   | $\begin{pmatrix}-6 \\ -9\end{pmatrix}$ | $\begin{pmatrix}6 \\ -2\end{pmatrix}$ | $\begin{pmatrix}0 \\ -11\end{pmatrix}$ |


**Fakt 1.5** Jeder Vektor $\mathbf{u} \in \mathbb{R}^{2}$ ist eine Linearkombination von $v = \begin{pmatrix}2 \\ 3\end{pmatrix} \text{ und } w \begin{pmatrix}3 \\ -1\end{pmatrix}$.
**Beweis**: Sei $\mathbf{u} = \begin{pmatrix}u_{1} \\ u_{2}\end{pmatrix}$. Ziel: finde $\lambda, \mu$:
$$
\lambda \begin{pmatrix}
2 \\
3
\end{pmatrix}+\mu \begin{pmatrix}
3 \\
-1
\end{pmatrix}=\begin{pmatrix}
u_{1} \\
u_{2}
\end{pmatrix}.
$$
Zwei Gleichungen in zwei Variablen 
$$
\begin{cases}
2\lambda + 3\mu = u_{1} \\
3\lambda-\mu = u_{2}
\end{cases}
$$
Addiere drei mal Gleichung 2 zu Gleichung 1 und löse nach $\lambda$ auf: 

$$
11\lambda = u_{1}+3u_{2} \to \lambda = \frac{u_{1}+3u_{2}}{11}
$$
Löse nach $\mu$ auf:

$$
3\mu = u_{1} - 2\lambda = u_{1}-\frac{2u_{1}+6u_{2}}{11} = \frac{9u_{1}-6u_{2}}{11} \to \mu = \frac{3u_{1}-2u_{2}}{11}
$$

*& see more of affine, conic and convex combinations*