---
date: 2026-06-15
---
The differencer is a [[Linear Constant Coefficient Difference Equation|LCCDE]] system that computes the first difference of an input [[Computer Science/Computational Science/DigitalSignalProcessing/Signal|signal]]. 
* It is the [[Discrete-Time Signal|Discrete-Time]] equivalent of a [[Derivative]]
* This system is [[Feed-Forward]]
* Its [[Impulse Response]] is $\delta[n] - \delta[n-1]$, a difference of the [[Unit Sample]]

$$\begin{align}
y[n] &= x[n] - x[n-1]\\
Y &= (1 - z^{-1})X
\end{align}$$

