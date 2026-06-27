---
date: 2026-05-27
aliases:
  - LTI System
---
A *Linear Time-Invariant* (LTI) [[System]] is a [[Linear Transformation]] that has [[Shift-Invariance|Time Invariance]]

**Linear Transformation**

$$
\begin{align}
T(x_{1}[n] + x_{2}[n]) &= T(x_{1}[n]) + T(x_{2}[n])\\
T(\lambda x_{1}[n]) &= \lambda T(x_{1}[n])
\end{align}
$$

**Time Invariance**

$$
T(x[n-n_{0}]) = y[n-n_{0}]
$$


# Categorical Structure

In [[Category Theory]], an LTI system is an [[Endomorphism]] on the [[Mathematics/Algebra/Abstract Algebra/Linear Algebra/Space|Space]] of [[Discrete-Time Signal]]s: it is a [[Morphism]] whose [[Domain]] and [[Codomain]] are the same signal space.

Time-invariance is the condition that $T$ commutes with the [[Delay Operator]] $\mathcal{R}$:

$$T \circ \mathcal{R} = \mathcal{R} \circ T$$

This is expressed as a [[Commutative Diagram]]: applying a delay before or after $T$ yields the same result.

# Discrete-Time LTI System
![[Discrete-Time Linear Time-Invariant System|Discrete-Time LTI System]]


# Continuous-Time LTI System
![[Continuous-Time Linear Time-Invariant System]]