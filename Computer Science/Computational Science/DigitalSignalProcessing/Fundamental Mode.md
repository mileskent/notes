---
date: 2026-06-17
aliases:
  - Fundamental Modes
---
A *Fundamental Mode* is the geometric sequence $p_k^n\, u[n]$ associated with a [[Pole]] $p_k$ of a system's [[Transfer Function]] $H(z)$. The [[Impulse Response]] of any [[Linear Time-Invariant System|LTI]] system with a rational $H(z)$ is a superposition of fundamental modes weighted by their [[Residue|residues]] $A_k$:

$$
h[n] = \sum_{k=1}^{N} A_k\, p_k^n\, u[n]
$$

The residues are obtained from the partial fraction decomposition of $H(z)$:

$$
H(z) = \sum_{k=1}^{N} \frac{A_k}{1 - p_k z^{-1}}, \quad A_k = \operatorname{Res}(H(z),\, z = p_k)
$$

The behavior of each mode is determined solely by $|p_k|$. See [[Pole#Convergence]].
