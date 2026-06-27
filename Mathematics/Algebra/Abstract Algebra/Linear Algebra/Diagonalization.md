---
date: 2026-01-11
---


#### Diagonal Matrix
A matrix is **diagonal** if the only non-zero elements, if any, are on the main diagonal.
- If $A$ is diagonal, then $A^k$ is very easy to compute because you simply exponentiate every diagonal element by $k$

Diagonal matrices cannot have $\lambda = 0$
#### Strang
Consider a matrix $A$ with some eigenvalues and eigenvectors.
$A\vec{v_0} = \lambda_0 \vec{v_0}$
...
$A\vec{v_n} = \lambda_n \vec{v_n}$

$$
\begin{gathered}
A\ [\vec{v_0}\ ,\ ...\ ,\ \vec{v_n}] = [\lambda_0 \vec{v_0}\ ,\ ...\ ,\ \lambda_n \vec{v_n}]\\

A\ [\vec{v_0}\ ,\ ...\ ,\ \vec{v_n}]= [\vec{v_0}\ ,\ ...\ , \vec{v_n}]\begin{bmatrix}
\lambda_0 &  &  \\
 & ... &  \\
 &  & \lambda_n
\end{bmatrix}\\

A\ = [\vec{v_0}\ ,\ ...\ , \vec{v_n}]\begin{bmatrix}
\lambda_0 &  &  \\
 & ... &  \\
 &  & \lambda_n
\end{bmatrix} [\vec{v_0}\ ,\ ...\ ,\ \vec{v_n}]^{-1}
\end{gathered}
$$


# [[Diagonalizable]]
# [[Orthogonal Diagonalization]]