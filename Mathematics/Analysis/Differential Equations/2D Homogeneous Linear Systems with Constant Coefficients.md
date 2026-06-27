---
date: 2025-10-15
---

$$
\frac{d \vec{x}}{dt} = A \vec{x}
\quad\quad \text{where } \vec{x}(t) = \begin{bmatrix}
x_1(t) \\
x_2(t)
\end{bmatrix},\ A \text{ is a } 2 \times 2 \text{ real constant matrix}
$$
## Distinct Real & Nonzero Eigenvalues
> [!faq]- Loosey goosey explanation
Recall $u' = \lambda u \implies u = ce^{\lambda t}$
"Think of matrices as a generalization of the number system"
Well it turns out that $\vec{x}' = A \vec{x} \implies \vec{x} = \vec{c}e^{At}$, where $\dim A = 2$
A is diagonalizable $\iff \vec{x} = c_{1} e^{\lambda_{1} t} \vec{x}_{1} + c_{2} e^{\lambda_{2} t} \vec{x}_{2}$ where $\lambda_{n}$ are A's eigenvalues, and $\vec{v}_{n}$ are $A$'s eigenvectors. See [[Eigenstuff]].

Find the eigenvalues of $A$ by solving the [[Characteristic Equation#Characteristic Polynomial]]
We assume that $\lambda = \lambda_{1}, \lambda_{2} \in \mathbb{R} \not = 0 \quad \lambda_{1} \not = \lambda_{2}$
$$
\begin{align}
\det(A - \lambda I) = 0
\end{align}
$$
We find $\lambda_1$'s eigenvector $\vec{u}_{1}$ by solving $(A-\lambda_{1} I) \vec{x} = 0$
We find $\lambda_2$'s eigenvector $\vec{u}_{1}$ by solving $(A-\lambda_{2} I) \vec{x} = 0$
The general solution for $\vec{x}$ is
$$
\vec{x}(t) = C_{1} \exp(\lambda_{1}t) \vec{u}_{1} + C_{2} \exp(\lambda_{2}t) \vec{u}_{2} \quad \quad \text{where } C_{1},\ C_{2} \text{ are free parameters}
$$
If an initial condition is given, then there is a unique solution.
### [[Stability]] & [[Phase Portrait]]
> [!col]
> ![[Pasted image 20250905173724.png|$\lambda_{1}, \lambda_{2} < 0 \implies$Stable Nodal Sink, Asymptotically Stable]]
> 
> ![[Pasted image 20250905173930.png|$\lambda_{1}, \lambda_{2} > 0 \implies$ Nodal Source, Unstable]]
>
> ![[Pasted image 20250905180026.png|$\lambda_{1} > 0\ \ \lambda_{2} < 0 \implies$ Saddle, Unstable]]

## A Zero Eigenvalue
This is a specific case of the previous section.
This is the same as the previous section [[#Distinct Real & Nonzero Eigenvalues]], except
We assume $\lambda = \lambda_{1}, \lambda_{2},\text{WLOG } \lambda_{1}=0, \lambda_{2} \not = \lambda_{1}$, which implies
$$
\vec{x} = C_{1} \vec{u}_{1} + C_{2} \exp(\lambda_{2} t) \vec{u}_{2}
$$
This is a simplification of the general formula from [[#Distinct Real & Nonzero Eigenvalues]]
On the eigenspace of the zero eigenvalue $\lambda_{1}$, the solutions are time independent; i.e., the eigenspace of the zero eigenvalue is a line of equilibrium. The other eigenvalue determines the behavior of the phase space outside of the equilibrium line.
### [[Stability]] & [[Phase Portrait]]
Both cases have $\lambda_{1} = 0$
> [!col]
> ![[Pasted image 20250912160920.png|$\lambda_{2} < 0$, Attractive line of equilibirum, strictly stable|225]]
> 
> ![[Pasted image 20250912160948.png|$\lambda_{2} > 0$, Repulsive line of equilibrium, unstable|200]]
## Repeated Real Eigenvalues
This is the same as the previous sections except
We assume $\lambda = \lambda_{1}, \lambda_{2} \in \mathbb{R},\ \lambda_{1}=\lambda_{2}$
### Easy Case
where $A = \lambda_{1} I$
$$
\vec{x} = \exp(\lambda_{1} t)\ \vec{C}
$$
This is a simplification of the general formula from [[#Distinct Real & Nonzero Eigenvalues]], where $\vec{C}$ is formed by $C_1$ and $C_2$, and we chose the [[Standard Basis Vectors]] for our eigenvectors, because any linearly independent pair of vectors in $\mathbb{R}^2$ would be satisfactory.
### Hard Case
where $A \not = \lambda_{1} I$
$$
\vec{x} = C_{1} \exp(\lambda_{1} t) \vec{u} + C_{2} \exp(\lambda_{1} t) \left(\vec{v} + t \vec{u}\right)
$$
We get the first term for this general solution from the typical method of finding eigenvectors, but because we have multiplicity of 2, our result is only one eigenspace, i.e. a partial solution. 
In order to get a full solution, we have to find a generalized eigenvector as well (the eigenvector for the second term). We get this eigenvector $\vec{v}$ by solving $(A - \lambda_{1}I) \vec{x} = \vec{u}$, where $\vec{u}$ was the eigenvector from the first term.
## Stability and Phase Portrait
![[Pasted image 20250912162925.png|400]]
## Complex Eigenvalues
This is the same as the previous sections except
We assume $\lambda = \lambda_{1}, \lambda_{2} \in \mathbb{C},\ \lambda_{1} = \alpha + \beta i, \lambda_{2} = \alpha - \beta i,\ \beta \not = 0$
$$
\text{Complex-valued: }\quad\vec{x} = C_{1} \exp(\lambda_{1} t)\vec{u}_{1} + C_{2} \exp(\lambda_{2} t)\vec{u}_{2}
$$
$$
\text{Real-valued: }\quad\vec{x} = C_{1} \mathrm{Re} (\exp(\lambda_{1} t)\vec{u}_{1}) + C_{2} \mathrm{Im} (\exp(\lambda_{1} t)\vec{u}_{1}) = 
C_1 \exp(\alpha t) \left(\cos(\beta t) \vec{a} - \sin(\beta t) \vec{b}\right) + C_2 \exp(\alpha t) \left(\sin(\beta t) \vec{a} + \cos(\beta t) \vec{b}\right)
$$
where $\exp(\lambda_{1} t)\vec{u}_{1}$ is a complex solution to the system
where $\alpha = \mathrm{Re} \lambda_{1}$ gives the growth/decay rate
where $\beta = \mathrm{Im} \lambda_{1}$ is the frequency of the oscillation of the system
where $\vec{a} = \mathrm{Re}\ \vec{u_{1}}$ 
where $\vec{b} = \mathrm{Im}\ \vec{u_{1}}$ 

When finding eigenvectors, for $A \in \mathbb{C}^{2 \times 2}$ and $\det A \not = 0$, ignore the second row, because it can be eliminated by definition. See [[#Misc]].
When you get $\lambda = \alpha \pm \beta i$, you can use either eigenvalue-eigenvector pair for the general equation. They will both give you the same solution, as the sign change will get absorbed in the $C$s
### Stability and Phase Portrait
Apply matrix $A$ once, to get the initial velocity, to determine the direction of rotation
$\exp \alpha t$ scales the whole solution
![[Pasted image 20250912163741.png|400]]