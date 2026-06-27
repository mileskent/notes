---
date: 2024-12-08
---
A standard matrix $A$ is a [[Matrix]] that represents a [[Linear Transformation]], where the transformation can be expressed as $T(\vec{x}) = A \vec{x}$. It is found by applying the transformation to the [[Standard Basis Vectors]]s and using the results as the columns of the matrix $A$
# Theorem
Let $T: \mathbb{R}^n \rightarrow \mathbb{R}^m$ be a Linear Transformation. Then there is a unique Matrix $A$ such that
$T(\vec{x}) = A\vec{x}, \vec{x} \in \mathbb{R}^n$
In fact, $A$ is a $m \times n$ and its $j^{th}$ column is a vector $T(\vec{e_j})$
$A = [T(\vec{e_1}), T(\vec{e_2}), ... T(\vec{e_n})]$

# Example
$$
T(\vec{e_1}) = \begin{bmatrix}
5 \\
 -7\\
2
\end{bmatrix}, T(\vec{e_2})=\begin{bmatrix}
-3 \\
 -8\\
0
\end{bmatrix}
$$
$$
A = \begin{bmatrix}
T(\vec{e_1}) & T(\vec{e_2}) 
\end{bmatrix} = \begin{bmatrix}
5 & -3 \\
-7 &  -8\\
2 & 0
\end{bmatrix}
$$

Find standard matrix A for T(x) = 3$\vec{x}$ for x in $\mathbb{R}^2$
$A \in \mathbb{R}^2$

$$
A = \begin{bmatrix}
T(\vec{e_1}) & T(\vec{e_2}) 
\end{bmatrix} = \begin{bmatrix}
\begin{bmatrix}
3 \\
0
\end{bmatrix} & \begin{bmatrix}
0 \\
3
\end{bmatrix}
\end{bmatrix} = \begin{bmatrix}
3 & 0 \\
0 & 3
\end{bmatrix}
$$
