---
date: 2026-05-27
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


The subclass of LTI systems expressible as a finite-order recurrence relation with constant coefficients is described by a [[Linear Constant Coefficient Difference Equation]].

A further property, independent of linearity and time-invariance, is [[Causality]]: the output depends only on current and past inputs.

# Categorical Structure

In [[Category Theory]], an LTI system is an [[Endomorphism]] on the [[Mathematics/Algebra/LinearAlgebra/Space|Space]] of [[Discrete-Time Signal]]s: it is a [[Morphism]] whose [[Domain]] and [[Codomain]] are the same signal space.

Time-invariance is the condition that $T$ commutes with the [[Delay Operator]] $\mathcal{R}$:

$$T \circ \mathcal{R} = \mathcal{R} \circ T$$

This is expressed as a [[Commutative Diagram]]: applying a delay before or after $T$ yields the same result.