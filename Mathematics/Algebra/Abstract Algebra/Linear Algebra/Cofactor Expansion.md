---
date: 2026-01-11
---

Cofactor expansion is a method used to calculate the [[Determinant]] of an $n \times n$ matrix $A$. It works by reducing the determinant of the $n \times n$ matrix to a sum of determinants of $(n-1) \times (n-1)$ submatrices. It is a recursive definition.

$$C_{ij} = (-1)^{i+j} \det(M_{ij})$$
where $M_{ij}$ is the determinant of the submatrix of $A$ obtained by deleting the $i$-th row and $j$-th column

The $\pm$ signs for each term of the expansion are determined solely by the position $(i, j)$ and follow a checkerboard pattern, starting with $+$ in the top-left corner

$$
\begin{bmatrix}
+ & - & + & \cdots \\
- & + & - & \cdots \\
+ & - & + & \cdots \\
\vdots & \vdots & \vdots & \ddots
\end{bmatrix}
$$

The determinant of a matrix $A$ can be calculated by **cofactor expansion** along any **single row $i$** or any **single column $j$**.

Expansion Along Row $i$:
$$\det(A) = a_{i1}C_{i1} + a_{i2}C_{i2} + \cdots + a_{in}C_{in}$$

Expansion Along Column $j$:
$$\det(A) = a_{1j}C_{1j} + a_{2j}C_{2j} + \cdots + a_{nj}C_{nj}$$

**Strategy:** To simplify calculations, it is generally best to choose the row or column with the **most zeros**.
