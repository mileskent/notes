---
date: 2025-10-15
---


$$
\vec{x}'=A(\vec{x} - \vec{a})
\quad\text{and}\quad
\vec{x}'=A\vec{x} + \vec{b}
$$
## Transient Method
Substitute a variable into the system, so that we have a problem we know how to solve. Similar idea to [[U Substitution]]. 
Solution: Equilibrium + Transient

## Type 1
$\vec{x}'=A(\vec{x} - \vec{a})$, where A is a constant square matrix, $\vec{a}$ is a constant vector
Set $\vec{y} = \vec{x} - \vec{a}$, as $\vec{a}$ is an equilibrium, and $\vec{y}$ is the transient solution
Solve for $\vec{y}(t)$ from $\vec{y}' = A \vec{y}$. See [[2D Homogeneous Linear Systems with Constant Coefficients]]
Solution is $\vec{x}(t) = \vec{a} + \vec{y}(t)$
> [!Example]-
> $$
> \begin{bmatrix}
> x_1' \\
> x_2'
> \end{bmatrix}
> =
> \begin{bmatrix}
> 3 & -3 \\
> -1 & 5
> \end{bmatrix}
> \begin{bmatrix}
> x_1 - 2 \\
> x_2 - 3
> \end{bmatrix}
> $$
(a) Find all equilibria
(b) Find general solutions
(c) Solve with the initial condition $\vec{x} = \begin{bmatrix}1 \\ 0\end{bmatrix}$
(d) Sketch the phase portrait
(e) Determine the stability of each equilibrium
> 
>
> (a) This ODE is of the form $\vec{x}' = A(\vec{x}-\vec{a})$, i.e. [[#Type 1]], so the equilbrium is $\vec{a} = \begin{bmatrix}2 \\ 3\end{bmatrix} \implies (2,3)$
> (b) Let $\vec{y} = \vec{x} - \vec{a}$, so we have $\vec{y}' = A\vec{y}$, which we know how to solve because it is a [[2D Homogeneous Linear Systems with Constant Coefficients]]. 
> Eigenvalues = $\det(A - \lambda I) = 0 \implies \lambda = 2,6$
> Eigenvectors = $(A-\lambda_{i}I)\vec{u}_{i} = \vec{0} \implies  \vec{u}=\begin{bmatrix}3\\1\end{bmatrix}, \begin{bmatrix}-1\\1\end{bmatrix}$
> $$
> \therefore \vec{y}(t) = C_{1} \exp(2t)\begin{bmatrix}3\\1\end{bmatrix} + C_{2} \exp(6t)\begin{bmatrix}-1\\1\end{bmatrix}
> $$
> $$
> \implies \boxed{\vec{x}(t) = \begin{bmatrix}2 \\ 3\end{bmatrix} + C_{1} \exp(2t)\begin{bmatrix}3\\1\end{bmatrix} + C_{2} \exp(6t)\begin{bmatrix}-1\\1\end{bmatrix}}
> $$
> (c) 
> $$
> \vec{x}(0) = \begin{bmatrix}1 \\ 0\end{bmatrix}= \begin{bmatrix}2 \\ 3\end{bmatrix} + C_{1} \exp(2(0))\begin{bmatrix}3\\1\end{bmatrix} + C_{2} \exp(6(0))\begin{bmatrix}-1\\1\end{bmatrix}
> $$
> $$
>  \begin{bmatrix}1 \\ 0\end{bmatrix}= \begin{bmatrix}2 \\ 3\end{bmatrix} + C_{1} \begin{bmatrix}3\\1\end{bmatrix} + C_{2} \begin{bmatrix}-1\\1\end{bmatrix} \implies C_{1}=-1,C_{2}=-2
> $$
> $$
> \vec{x}(t) = \begin{bmatrix}2 \\ 3\end{bmatrix} - \exp(2t)\begin{bmatrix}3\\1\end{bmatrix} -2 \exp(6t)\begin{bmatrix}-1\\1\end{bmatrix}
> $$
> (d) Center the portrait at the equilibrium point $(2,3)$
> Both eigenvalues are postitive, so the eigenspace arrows all go out. Because they have the same sign, the curves off of the eigenspaces are parabolas.
> ![[Pasted image 20250924202352.png|300]]
> (e) The equilibrium is unstable.

## Type 2
$\vec{x}'=A\vec{x} + \vec{b}$, where A is a constant square matrix, $\vec{b}$ is a constant vector
 Essentially, convert into [[#Type 1]] by finding an equilibrium $\vec{a}$ by solving $A \vec{x} + \vec{b} = \vec{0}$ for $\vec{x}$.
 If no equilbrium exists, you must use [[Variation of Parameters]] instead. 
Transient solution $\vec{y} = \vec{x} - \vec{a}$ that satisfies $\vec{y}' = A \vec{y}$, solve for $\vec{y}(t)$. See [[2D Homogeneous Linear Systems with Constant Coefficients]]
Solution is $\vec{x}(t) = \vec{a} + \vec{y}(t)$
