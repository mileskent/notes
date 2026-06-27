---
date: 2026-01-11
---

Linear Algebra is the study of [[Vector Space|Vector Spaces]]
# Vectors and Vector Spaces
![[Vector Space]]

![[Vector]]

## Subspaces of $\mathbb{R}^n$
![[Subspace]]

![[Columnspace]]

![[Rowspace]]

![[Nullspace]]

![[Basis]]

![[Rank]]

![[Nullity]]

![[Fundamental Theorem of Linear Algebra]]

![[Invertibility Theorem]]

![[Determinant]]

![[Cofactor Expansion]]

![[Eigenstuff]]



![[Characteristic Equation]]

![[Similar]]

# Systems of Linear Equations
![[Linear System]]

![[Linear Equation]]

![[Row Reduction]]

# Vector Equations
![[Vector Equation]]

![[Real Number]]

![[Linear Combination]]

![[Span]]

$$
\begin{bmatrix}
2 & 3 & 7 \\
1 & -1 & 5
\end{bmatrix}

\begin{bmatrix}
5 & 0 & 22 \\
1 & -1 & 5
\end{bmatrix}

\begin{bmatrix}
1 & 0 & 22/5 \\
0 & 1 & 22/5-5
\end{bmatrix}
$$
![[Homogenous]]

![[Linear Independence]]
# Intro to Linear Transformations
![[Linear Transformation]]
# Matrix of Linear Transformations
## The standard (basis) vectors
![[Basis]]

![[Basis Vector]]

![[Standard Matrix]]

![[Zero Matrix]]

![[Identity Matrix]]

![[Zero Matrix]]

![[Identity Matrix]]

![[Matrix]]

![[Elementary Matrix]]

![[Singular Matrix]]

![[Block Matrix]]

![[LU Decomposition]]
# Markov chains
![[Pasted image 20241002094128.png|500]]

![[Probability Vector]]

![[Stochastic Matrix]]

![[Markov Chain]]


# Diagonalization
![[Diagonalization]]

![[Diagonalizable]]

# Complex Eigenvalues
![[Complex Number]]

![[Complex Number]]
### Complex Eigenvalues
![[Fundamental Theorem of Algebra#Complex Eigenstuff]]

#### Example
4 of the eigenvalues of a 7 x 7 matrix are -2, 4 + i, -4 - i, and i
- Because there are 3 nonconjugate complex pairs, we know that the remaining eigenvalues are the conjugates of the given complex values
- What is the characteristic polynomial?
- $p(\lambda) = (\lambda + 2)(\lambda - (4+i))(\lambda - (-4-i))(\lambda - i) (\lambda-(4-i))(\lambda - (-4 + i))(\lambda + i)$ 
#### Example
The matrix that rotates vectors by $\frac{\pi}{4}$ radians about the origin and then scales vectors by $\sqrt{2}$ is:
$$
\begin{bmatrix}
1 & -1 \\
1 & 1
\end{bmatrix}
$$
What are the eigenvalues of $A$? Find an eigenvector for each eigenvalue

$det(A - \lambda I) = (1 - \lambda)^2 = \lambda^2 - 2\lambda +2$
$\lambda = \frac{2 \pm \sqrt{4 - 8}}{2} = \frac{2 \pm 2i}{2} = 1 \pm i$
$\lambda^{+}$:
$$
\begin{gathered}
A - \lambda^{+} I\\
\begin{bmatrix}
1-(1+i) & -1 \\
1 & 1-(1+i)
\end{bmatrix}
\\
\begin{bmatrix}
-i & -1 \\
1 & -i
\end{bmatrix}
\\
\begin{bmatrix}
1 & -i\\
-i & -1
\end{bmatrix}
\\
\begin{bmatrix}
1 & -i\\
0 & 0
\end{bmatrix} \rightarrow \vec{v_{+}} = \begin{bmatrix}
i \\
1
\end{bmatrix}
\end{gathered}
$$

$\lambda^{-}$:
$$
\begin{gathered}
""""""\rightarrow \vec{v_{-}} = \begin{bmatrix}
-i \\
1
\end{bmatrix}
\end{gathered}
$$
Could reason the eigenvalue for $\lambda^{-}$ by the fact that eigenvalues and their eigenvectors come in complex conjugate pairs.


# Orthogonal Sets
![[Orthogonal]]

![[Orthogonal Set]]

![[Orthogonal Projection]]

 ![[Orthogonal Decomposition]]
 ![[Best Approximation]]
 ![[Gram-Schmidt Process]]
 ![[QR Decomposition]]
![[Least Squares]]

![[Google Page Rank]]

![[Symmetric Matrix]]

![[Spectral Decomposition]]

![[Orthogonal Diagonalization]]
![[Quadratic Form]]

![[Constrained Optimization]]

![[Singular Value Decomposition]]
