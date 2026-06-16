---
date: 2025-12-12
---
The Complex Numbers are a [[Number]] [[Set]] denoted by $\mathbb{C}$ that extends the [[Real Number|Real Numbers]] via the [[Imaginary Unit]] $i = \sqrt{ -1 }$
* $\mathbb{C}$ is a [[Vector Space]] [[Isomorphism]] of $\mathbb{R}^2$
* Like $\mathbb{R}^2$, the complex numbers can be represented within the [[Cartesian Plane]].
* $\mathbb{C}$ is a closed [[Algebraic Field]]

Complex numbers are of the form
$$
a + bi
$$
* where $a, b \in \mathbb{R}$
* where $i$ is the [[Imaginary Unit]]

![[Euler's Formula]]
# Operations
## Binary
### Addition
Like adding [[Vector]]s in $\mathbb{R}^2$
$$
\begin{align}
z_{1} + z_{2} &= \\
(a+bi) + (c+di) &= \\
(a+c) + (b+d)i
\end{align}
$$
### Subtraction
Like subtracting [[Vector]]s in $\mathbb{R}^2$
$$
\begin{align}
z_{1} - z_{2} &= \\
(a+bi) - (c+di) &= \\
(a-c) + (b-d)i
\end{align}
$$
### Multiplication
$$
z_{1} \cdot z_{2}=(a+bi) \cdot (c+di) = ac - bd + (ad+bc)i
$$
### Division
$$
\frac{z_{1}}{z_{2}} = 
\frac{z_{1}\overline{z_{2}}}{|z_{2}|^2} = \frac{(a+bi)(c-di)}{c^2 + d^2}=
 \frac{ac+bd+(bc-ad)i}{c^2 + d^2}
$$

## Unary
### Real Component Function
### Imaginary Component Function
### Argument
$$
z = |z|e^{i\phi} \implies
\text{arg}\ z = \phi
$$
![[Pasted image 20251222173155.png|100]]
### Complex Conjugate
$$
\overline{a + bi} = (a+bi)^* = a - bi
$$
$$
\overline{(z_{1}+z_{2})} = \overline{z_{1}} + \overline{z_{2}}
$$
$$
\overline{(z_{1}z_{2})} = \overline{z_{1}} \overline{z_{2}}
$$
$$
\overline{A\vec{z}} = A \overline{\vec{z}}
$$
$$\text{Im}(z\overline{z}) = 0$$
$$z\overline{z} = |z|^2$$
Reflects across the Real axis.
![[Pasted image 20251222172911.png|100]]
### Magnitude
Also called "Modulus"
$$
|a + bi| = \sqrt{a^2 + b^2} = \sqrt{(a+bi)(a-bi)}
$$
![[Pasted image 20251222173155.png|100]]
The magnitude is the $r$ in the figure.