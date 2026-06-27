---
date: 2025-10-15
---

# Stable
An [[Equilibrium Solution|equilibrium point]] is said to be **stable** if for some initial value close to the equilibrium point, the solution will eventually stay close to the equilibrium point
![[Pasted image 20250907173524.png]]
And vice versa
![[Pasted image 20250907173545.png]]
## Asymptotically Stable
An equilibrium point is said to be **asymptotically stable** if for some initial value close to the equilibrium point, the solution will not only eventually stay close, but also converge to the equilibrium point.

# N-Dimensional Homogenous System Identification
e.g. for $\vec{x}' = A \vec{x}$, where [[Eigenstuff]] comes from matrix $A$
$$
\begin{align}
\vec{x}' = A \vec{x} &\implies \vec{x} = \vec{0} \text{ is equilbrium}\\

(\exists\ \mathrm{Re}\ \lambda > 0) \lor\\ (\forall \lambda\ \mathrm{Re}\ \lambda \leq 0\ \land\\ \exists \mathrm{Re}\ \lambda = 0 \ \land \\ \forall \mathrm{Re}\ \lambda = 0,\ \lambda \equiv \neg \text{Defective})&\implies \text{Unstable}\\

\forall\ \mathrm{Re}\ \lambda < 0 &\implies \text{Asymptotically Stable}\\

\text{Else} &\implies \text{Stable}
\end{align}
$$
See [[Eigenstuff#Defective]]
# Misc
For first order [[Differential Equation]]s, the motion of a point in a [[Phase Portrait]] won't cross a [[Equilibrium Point]]
