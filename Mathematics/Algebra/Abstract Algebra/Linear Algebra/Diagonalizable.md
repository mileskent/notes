---
date: 2026-01-11
---

$A \in \mathbb{R}^{n \times n} \land A = PDP^{-1} \implies A$ is diagonalizable, where $D$ is a diagonal matrix

$A$ is diagonalizable $\iff$ $A$ has $n$ linearly independent eigenvectors.
i.e.

$$
A = PDP^{-1}\\ \iff \\ A = [\vec{v_1}, ..., \vec{v_n}] 
\begin{bmatrix}
\lambda_1 &  &  \\
 & ... &  \\
 &  & \lambda_n
\end{bmatrix}
[\vec{v_1}, ..., \vec{v_n}]^{-1}
$$


where $\vec{v}$ vectors are linearly independent eigenvectors, and $\lambda_1, ..., \lambda_n$ are the corresponding eigenvalues, in order.

#### Distinct Eigenvalues
If $A \in \mathbb{R}^{n \times n}$ and has $n$ distinct eigenvalues, then $A$ is diagonalizable

#### Non-distinct Eigenvalues
You check that the sum of the geometric multiplicities is equal to the size of the matrix.
e.g. for

$$
\begin{bmatrix}
1 &  & -1 \\
 & 2 &  \\
 &  & 1
\end{bmatrix}
$$

Find the eigenvalues:

$$
\begin{vmatrix}
1-\lambda &  & -1 \\
 & 2-\lambda &  \\
 &  & 1-\lambda
\end{vmatrix} = (1-\lambda)^2 (2-\lambda) = 0
$$
$$
\therefore \lambda = 1,1,2
$$

We know that geomult <= algmult. Therefore $\lambda = 2$ has 1 distinct eigenvector.
This means $\lambda = 1$ has to have 2 distinct eigenvectors to form a basis, so if it doesn't then the matrix is not diagonalizable.

$$
A - I = \begin{bmatrix}
0 &  & -1 \\
 & 1 &  \\
 &  & 0
\end{bmatrix}
$$

There is only one free columns here. Therefore, the dimension of the Nullspace is one, not two, which means the matrix is not diagonalizable.

#### Basis of Eigenvectors
$$
\begin{gathered}
\text{Express the vector $\vec{x}_0 =$}
\begin{bmatrix}
4 \\
5
\end{bmatrix}
\text{ as a linear combination of the vectors }\\
\vec{v}_1 = \begin{bmatrix}
1 \\
1
\end{bmatrix}
\text{ and }
\vec{v_2} =\begin{bmatrix}
1 \\
-1
\end{bmatrix}
\text{ and find the coordinates of } \vec{x_0} \text{ in the basis}\\
\mathcal{B} = \{\vec{v_1}, \vec{v_2}\}\\
\\
[\vec{x_0}]_{\mathcal{B}} = ?\quad\quad\quad
[\vec{x_0}]_{\mathcal{B}} = \begin{bmatrix}
4.5 \\
-0.5
\end{bmatrix}\\
\\
\sim \\
\\
\text{Let } P = [\vec{v_1}\ \vec{v_2}],\ D = \begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}\\
\\
[A^k\ \vec{x}_0]_{\mathcal{B}} =\ ? \quad\quad\text{where } A = PDP^{-1},\ k\in \mathbb{Z}^{+}\\
\\
A^k = PD^k P^{-1} = [\vec{v_1}\ \vec{v_2}]
\begin{bmatrix}
 1^k &  \\
 & (-1)^k
\end{bmatrix}  
[\vec{v_1}\ \vec{v_2}]^{-1}\\
[A^k\ \vec{x}_0]_{\mathcal{B}} =\ ?
\end{gathered}
$$

#### Misc.
$$
\begin{gathered}
\text{Let d(x) be "x is diagonalizable"}\\
\text{Let i(x) be "x is invertible"}\\
d(A) \land i(A) \iff d(A^{-1})\land i(A^{-1})
\end{gathered}
$$
