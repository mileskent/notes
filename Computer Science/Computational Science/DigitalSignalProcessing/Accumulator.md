---
date: 2026-06-15
---
The accumulator is a [[Linear Constant Coefficient Difference Equation|LCCDE]] system that computes the running sum of an input [[Computer Science/Computational Science/DigitalSignalProcessing/Signal|signal]]. 
* It is the [[Discrete-Time Signal|Discrete-Time]] equivalent of [[Integral|Integration]]
* It is a [[Feedback]] system
* Its [[Impulse Response]] is the [[Unit Step]] $u[n]$

$$\begin{align}
y[n] &= x[n] + y[n-1]\\
Y &= \frac{1}{1 - z^{-1}}X
\end{align}$$

