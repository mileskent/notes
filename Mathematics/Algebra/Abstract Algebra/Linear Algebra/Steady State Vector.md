---
date: 2024-12-08
---
A steady state vector for [[Stochastic Matrix]] $P$ is a [[Vector]] $\vec{q}$ such that $P \vec{q} = \vec{q}$. 
* It is where the [[Markov Chain]] of $P$ converges after a sufficient amount of time. 
* Solve for $(P-I)\vec{q} = 0$ to find the steady state vector for $P$.
* $\vec{q}$ is defined as $\lim_{k\rightarrow \infty} \left(P^k \vec{x_0}\right) = \vec{q}$, also $P\vec{q} = \vec{q}$
* When you repeatedly apply $P$, the [[Subspace]] will approach the [[Span]] of...
	* An [[Eigenstuff#Eigenvector]], if $P$ is [[Stochastic Matrix#Regular]]
	* A [[Set]] of [[Eigenstuff#Eigenvector]] with non-one [[Cardinality]], if $P$ is irregular
		* If the cardinality is greater than 1, points in the subspace will converge to the nearest [[Eigenstuff#Eigenspace]]

# Example
Determine the steady state vector for 
$$
P = \begin{bmatrix}
.8 & .3 \\
.2 & .7
\end{bmatrix}
$$
Goal: solve $P\vec{q} = \vec{q}$
$(P-I)\vec{q} = 0$
$$
\begin{gathered}
\begin{bmatrix}
.8-1 & .3 & 0 \\
.2 & .7-1 & 0
\end{bmatrix}\\
\begin{bmatrix}
-.2 & .3 & 0 \\
.2 & -.3 & 0
\end{bmatrix}\\
\begin{bmatrix}
1 & -\frac{3}{2} & 0 \\
0 & 0 & 0
\end{bmatrix}
\end{gathered}
$$
$$
\therefore \vec{q} = t\begin{bmatrix}
\frac{3}{2} \\
1
\end{bmatrix}
$$
$$
\frac{3}{2}t + t = 1
$$
$$
\therefore t = \begin{bmatrix}
\frac{3}{5} \\
\frac{2}{5}
\end{bmatrix}
$$