---
date: 2026-06-17
aliases:
  - System Functional
  - System Function
---
The *Transfer Function* $H(z)$ of an [[Linear Time-Invariant System|LTI]] system is the [[Z Transform]] of the [[Impulse Response]]

$$
H(z) = \mathcal{Z}\{h[n]\} = \frac{Y(z)}{X(z)} = \frac{B(z^{-1})}{A(z^{-1})} \\
$$

where $B$ and $A$ are polynomials with coefficients determined by the system's [[Discrete-Time Linear Time-Invariant System|DT LTI System]]. It completely characterizes the system's input-output relationship in the z-domain. The [[Pole|poles]] of $H(z)$ determine the system's fundamental modes.

# Intuition
For a system $Y=HX$, where $H$ represents the operator the describes the entire discrete system between $X$ and $Y$, you can also express said relationship as $H=\frac{Y}{X}$. For example, for an [[Accumulator]], you have $(1 - \mathcal{R})Y = X$, so $H=\frac{1}{1-\mathcal{R}}$, and the equation in terms of $H$ is $H = \frac{1}{1- \mathcal{R}} = \frac{Y}{X}$. We care about the Transfer Function because it describes the entire system; how the system *transfers* the input signal to the output signal. The impulse response does too, but it and the transfer function are [[Isomorphism|isomorphic]] via the [[Z Transform]], so this naturally follows. 

$$
\begin{align}
h[n]&:\mathbb{Z}\rightarrow \mathbb{C}\\
H(z)&:\mathbb{C}\rightarrow \mathbb{C}
\end{align}
$$

* When you use the impulse response function, you use [[Discrete Convolution]], whereas with the transfer function, you use multiplication.
* The order of the polynomial of the transfer function tells you the order of the system
* If the polynomial is in the numerator, you have a [[Feed-Forward]] system. If the polynomial is in the denominator, then you have a [[Feedback]] system. 
	* Sometimes you can compute the [[Linear Unary Operator#Operator Reciprocals|Operator Reciprocal]] of a denominator polynomial as equivalent to a numerator polynomial infinite series, meaning that some feedback systems are equivalent to infinitely large feedforward systems. This is reminiscent of [[Compiler Optimization#Loop Unrolling]] / [[Compiler Optimization#Tail Call Optimization]] on a [[Recursion|Recursive]] function.


