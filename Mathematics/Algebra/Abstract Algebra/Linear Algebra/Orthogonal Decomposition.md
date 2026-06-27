---
date: 2024-12-08
---

I proceed to define the orthogonal decomposition for some vector $y$, where $y \in \mathbb{R}^n$, where $W$ is a subspace of $\mathbb{R}^n$, where $W^{\perp}$ is the [[Orthogonal Complement]] of $W$, where $\hat{y}$ is the orthogonal projection of $\vec{y}$ onto $W$, and $\vec{z}$ is a vector orthogonal to $\hat{y}$. This is a [[Vector Decomposition]].
$$
y = (\hat{y} \in W) + (\vec{z} \in W^{\perp})
$$
![[Pasted image 20241028135920.png]]
- Every $y \in \mathbb{R}^n$ has a **unique** sum in the form above, so long as $W$ is a subspace of $\mathbb{R}^n$
- $dim(W) + dim(W^{\perp}) = n$

### Concerning $\hat{y}$
If $\vec{u_1}, \cdots, \vec{u_p}$ is an [[Orthogonal Basis]] for $W$, then $\hat{y}$, the orthogonal projection of $\vec{y}$ onto $W$ is given by:
$$
\begin{gathered}
\hat{y} =  proj_{W}\vec{y} = proj_{\vec{u_1}}\vec{y} + \cdots + proj_{\vec{u_p}}\vec{y} = proj_{W} \vec{y{}}
\end{gathered}
$$
See [[Best Approximation]], but in essence $\hat{y}$ is the closest vector in $W$ to $\vec{y}$

#### Examples:
[HW 6.3 Q1](https://www.desmos.com/calculator/ftgmcqydnn)
[HW 6.3 Q5](https://www.desmos.com/calculator/oofhrittrc)
[HW 6.3 Q6](https://www.desmos.com/calculator/qy62zcsg65)
