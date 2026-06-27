---
date: 2026-01-11
---

### Given
Given many data points, construct a matrix equation in the form of a linear equation (this matrix equation will be overdetermined). The matrix equation below is $A\vec{x} = \vec{b}$
This equation is linear but it doesn't have to be, just adjust accordingly to represent the equations as a matrix equation.
$$
\begin{bmatrix}
1 & x_0 \\
1 & x_1 \\
1 & x_2 \\
1 & x_3 \\
1 & x_4 \\
1 & x_5
\end{bmatrix}\begin{bmatrix}
b \\
m
\end{bmatrix} = \begin{bmatrix}
y_0 \\
y_1 \\
y_2 \\
y_3 \\
y_4 \\
y_5
\end{bmatrix}
$$
### Goal
Using [[Best Approximation]], find a vector in subspace $Col\ A$ closest to $\vec{b}$

$Col\ A$ is a subspace of $\mathbb{R}^n$, $\vec{b} \in \mathbb{R}^n$
$\forall \vec{x},\ \vec{a} = A\vec{x}$, i.e. $\vec{a} \in Col\ A$
$\hat{b} = A\hat{x} = proj_{Col\ A} \vec{b}$
Note: Can only use [[Orthogonal Decomposition]] for $\hat{b}$ when the columns of A form an orthogonal basis, by definition
$\implies$
$$
\begin{gathered}
\forall \vec{a}\in Col\ A,\ \vec{a} \not = \hat{b} \quad \quad ||\vec{b} - \hat{b}|| < ||\vec{b} - \vec{a}||\\
\forall A\vec{x} \in Col\ A,\ A\vec{x} \not = A\hat{x} \quad \quad ||\vec{b} - A\hat{x} || < ||\vec{b} - A\vec{x}||\\
\end{gathered}
$$

In other words, $\hat{b} = A\hat{x} = proj_{col\ a} \vec{b}$ is closest vector in $Col\ A$ to $\vec{b}$
Note: $\hat{x}$ is a unique vector, a special $\vec{x}$ that minimizes the above equation.
Note: If the columns of $A$ are orthogonal, then you can just use the scalar projection of $\vec{b}$ onto each column of $A$.

![[Pasted image 20241030094647.png|400]]
# Normal Equations
The least squares solutions to $A\vec{x} = \vec{b}$ corresponds to the solution to 
$$
A^T A\vec{x} = A^T \vec{b}
$$
- Turns the $A\vec{x} = \vec{b}$ equation from above and transforms it into a square matrix equation

### Derivation
![[Pasted image 20241030095559.png|400]]
- $(Col A)^{\perp} = Null(A^T)$
- $\hat{x}$ is the Least Squares Solution to $A\vec{x} = \vec{b}$ $\iff b - A\hat{x} \perp Col\ A$
- $\vec{b} - A\hat{x} \perp Col\ A \implies \vec{b} - A\hat{x} \in (Col\ A)^{\perp}$
- $\vec{b} - A\hat{x} \in (Col\ A)^{\perp} \implies \vec{b} - A\hat{x} \in Nul\ A^T$
- $\vec{b} - A\hat{x} \in Nul\ A^T \iff A^T (\vec{b} - A\hat{x}) = 0$
- $A^T (b - A\hat{x}) = 0$
- $A^T b - A^T A\hat{x} = 0$
- $A^T A\hat{x} = A^T \vec{b}$
##### Normal Equation Usage
- Use when non-square matrix
	- Over/Under determined
- Regression

### Theorem (Unique Solutions for Least Squares)
If A is m x n
- Ax = b has a unique least squares solution for each b in Rm
- Cols of A are linearly independent
- The matrix A^T A is invertible
If the above hold, the **unique** least square solution is
$$
\hat{x} = (A^T A)^{-1} A^T \vec{b}
$$
If the above conditions are not true, there may be infinitely many solutions, or some other nonunique amount of solutions, in which case you should consider $[A^T A\ A^T \vec{b}]$ instead.

Note: $A^T A$ plays the role of the "length squared" of the matrix A

### Theorem (Least Squares and QR)
$$
\begin{gathered}
A \in \mathbb{R}^{m \times n} = QR\\
\implies\\
\text{Least Squares Solution }
\hat{x} = R^{-1} Q^T \vec{b}
\end{gathered}
$$
## Examples
$$
\begin{gathered}
A = \begin{bmatrix}
4 & 0 \\
 0&2  \\
1 & 1
\end{bmatrix}, \quad \vec{b} = \begin{bmatrix}
2 \\
0 \\
11
\end{bmatrix}\\
\\
A^T A = \begin{bmatrix}
17 & 1 \\
1 & 8
\end{bmatrix}\\
A^T \vec{b} = \begin{bmatrix}
19 \\
11
\end{bmatrix}\\
\text{Now setup the Normal Equations:}\\
A^T A \vec{x}= A^T \vec{b}\\

\begin{bmatrix}
17 & 1 \\
1 & 8
\end{bmatrix}\vec{x} = \begin{bmatrix}
19 \\
11
\end{bmatrix}\\

\vec{x} = \begin{bmatrix}
17 & 1 \\
1 & 8
\end{bmatrix}^{-1}
\begin{bmatrix}
19 \\
11
\end{bmatrix}\\

\hat{x} = 
\begin{bmatrix}
1 \\
2
\end{bmatrix}
\end{gathered}
$$

### Hampton Explanation for Least Squares
Let $A \in \mathbb{R}^{m \times n}$. $\hat{x}$ is the unique, minimizing solution to the equation $A\vec{x} = \vec{b}$ such that
$$
\forall \vec{x} \in \mathbb{R}^n \quad\quad ||\vec{b} - A\hat{x}|| \leq ||\vec{b} - A \vec{x}||
$$
- Essentially, minimize $\vec{b} - A\hat{x}$
	- $||\vec{b} - \hat{b}||$ is the minimal distance between the different solutions
- $\forall x \in \mathbb{R}^n,\ A\vec{x} \in Col\ A,\ \vec{b} =^{?} Col\ A$
- Goal: Find $\hat{x}$ s.t. $A\hat{x} \in Col\ A$ is closest to $\vec{b}$
- $\hat{x}$ in this context just denotes the special/unique $x$ that minimizes the distances between $\vec{b}$ and $A\hat{x}$
![[Pasted image 20241030094647.png]]
b is closer to Axhat than to Ax for all other x in Col A
- If b in Col A, then xhat is...
- Seek $\hat{x}$ so that $A\hat{x}$ is as close to $\vec{b}$ as possible, i.e. $\hat{x}$ should solve Axhat = bhat
	- $\hat{b} = A\hat{x}= proj_{Col(A)} \vec{b}$

