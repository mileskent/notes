---
date: 2026-01-11
---

A matrix is a rectangular array of [[Number]]s
# Operations
## Matrix Addition
* Add elementwise
* Operand matrices must have the same dimensions
## Matrix Multiplication
Let $A \in \mathbb{R}^{m \times n},\ B \in \mathbb{R}^{n \times p}$
* Then, the $(i, j)$ entry of $AB$ is $\text{A.row}(i) \cdot\text{B.col}(j)$, where we are performing many [[Dot Product]]s to calculate the matrix product
* Then $AB \in \mathbb{R}^{m \times p}$
### Multiplication Properties
* $AB \not \equiv BA$
* $AB = AC \not \implies B = C$
* $AB = 0 \not \implies A = 0 \lor B = 0$
* $AB = [Ab_1\ Ab_2]$
## Transpose
$$ 
A=\begin{bmatrix}
a & b \\
c & d \\
e & f
\end{bmatrix}, A^T = \begin{bmatrix}
a & b & c \\
d & e & f
\end{bmatrix}
$$
## Transpose Properties
* $(A^T)^T = A$
* $(A + B)^T + A^T + B^T$
* $(sA)^T = s(A^T)$
* $(AB)^T = B^T A^T$
## Inverse
* Row reduce $(A | I_n)$ until you get $I_n$ for A
* Keep track of the [[Elementary Matrix]] for each [[Row Reduction#Row Operation]]
* The product of all of the elementary matrices is the inverse of $A$, by definition
$$
\begin{gathered}
(E_n E_{n-1} ... E_1) A = I_n
\\ \implies \\
(E_n E_{n-1} ... E_1) = A^{-1}
\end{gathered}
$$
* $A$ may not be invertible. In this case, you won't be able to row reduce it to the [[Identity Matrix]]
### Invertible
You cannot always take the inverse of a matrix. Whether or not it is possible is called *Invertibility*. See also [[Invertible Matrix Theorem]], [[Invertibility Theorem]].

**Invertibility Definition**:
$A \in \mathbb{R}^{n \times n}$ is invertible if $\exists C \in \mathbb{R}^{n \times n} s.t. AC = CA = I_n$

* A is invertible $\implies$ A is square
* A is invertible $\iff$ it is row equivalent to the identity
* Linearly dependent $\iff$ Singular
- Mnemonic: After the trial, Johnny Depp was Single
* Linearly independent $\iff$ Invertible
- This is just the inverse of the above
- $A \in \mathbb{R}^{n \times n}$ is invertible $\iff \forall \vec{b}\ \exists ! \vec{x}\ (A \vec{x} = \vec{b})$
	- Basically means that A is [[Bijective]]
- $\det(A) \not = 0 \iff$ invertible  
### Inverse Properties
* $(A^{-1})^{-1} = A$
* $(AB)^{-1} = B^{-1} A^{-1}$
* $(A^T)^{-1} = (A^{-1})^T$
* $\det A = \frac{1}{\det A^{-1}}$
### $2 \times 2$ Inverse Shortcut
$$
\text{Let }A = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
$$
\text{then }
A^{-1} = 
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}^{-1} = \frac{1}{det(A)}
\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
$$
