#FS2026 #A 

### Square Root of 2
- There is a proof for its existence in $\mathbb{R}$ in the SW2 Mitschrift.

### Vectors
- Scalar product, norm, euclidean distance
- Triangle inequality: $\|x-z\|\le \|x-y\| + \|y-z\|$

### Complex Numbers
- $i^{2}=\sqrt{ -1 }$
- Normal form: $z = a+bi$
- Operations:
	- Addition and multiplication proceed as usual
	- Division is performed using the conjugate, $\bar{z}$
	- $\bar{z}=\overline{x+iy}=x-iy$ (just swap the sign)
	- $\frac{z}{w}=\frac{z\cdot\bar{w}}{w\cdot \bar{w}}$
	- Using the conjugate takes the complex part out of the denominator. 
- We can represent the exponential function as the series:

$$
e^{x}=1+x+\frac{x^{2}}{2}+\frac{x^{3}}{3!}+\dots=\sum ^{\infty}_{k=0} \frac{1}{k!}x^{k}
$$

- Setting $x=it$ gives us $e^{it}=\cos(t)+i\sin(t)$, which is the **eulerian formula**. 
- This gives us alternative ways to write the $\sin$ and $\cos$ functions:

$$
\cos(t)=\frac{e^{it}+e^{-it}}{2} \quad \sin(t)=\frac{e^{it}-e^{-it}}{2i}
$$

- Polar form: $x = r\cdot e^{i\phi}$
- The square root of a complex number has two answers, cubic has three, etc. 
- Complex zeros of a function always come in conjugate pairs.