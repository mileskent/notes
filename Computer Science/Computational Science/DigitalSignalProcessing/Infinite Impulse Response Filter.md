---
date: 2026-05-31
aliases:
  - IIR Filter
---
An *Infinite Impulse Response Filter* is a [[Linear Time-Invariant System]] [[Filter]] whose [[Impulse Response]] never becomes zero, or in other words, the duration of response to the [[Impulse|Impulse Signal]] is **infinite**. This property is due to such filters being recursively defined, i.e. having [[Feedback]] (technically you could get the same recursive effect in a [[Feed-Forward]] system if it was infinitely long, but practically speaking, IIR means Feedback; its kind of like [[Compiler Optimization#Loop Unrolling|loop unrolling]] a [[Recursion|Recursive]] function and calling it non-recursive). 

$$
\begin{matrix}
\mathcal{H}:\mathbb{R}^\mathbb{Z} \times \mathbb{R}^\mathbb{Z} \times \mathbb{Z} \to \mathbb{R} \\
 \mathcal{H}(x, y, n) = y[n] \\
y[n] = \sum^M_{k=0} b_{k}\ x[n - k] - \sum^N_{k=1} a_{k} \cdot y[n-k] \\ \\
\end{matrix}
$$
* Because IIR Filters are Feed-Back
	* They are is inherently iterative and thus better suited for the [[CPU]], rather than [[GPU]] which is where [[Finite Impulse Response Filter|FIR]] belongs
		* High order systems can be decomposed into parallel low order systems, however.
	* [[Caching]] becomes even more important
	* They can be [[Divergent]], which can lead to [[Overflow]]. Thus, [[Stability]] needs to be considered

# Z Transform
$$
\begin{align}
H(z) &= \frac{\sum^M_{k=0}b_{k}z^{-k}}{\sum^N_{k=0} a_{k}z^{-k}},\ a_{0} = 1 \\
&= \frac{b_{0}\prod^M_{k=1}(1-c_{k}z^{-1})}{\prod^N_{k=1}(1-d_{k}z^{-1})} \\ \\
\end{align}
$$
* See [[Z Transform]]
## Divergence
For a system with poles $d_{k}$
* [[Stability#Asymptotically Stable]] $\iff\forall k, \ |d_{k}| < 1$
* Marginally Stable $\iff \forall k,\ |d_{k}| \leq 1$ and all poles with $|d_{k}| = 1$ are [[Characteristic Equation#Algebraic Multiplicity]] of 1
* Unstable $\iff \exists k, |d_{k}| > 1$ or $\exists k,\ |d_{k}| = 1$ with [[Characteristic Equation#Algebraic Multiplicity]] greater than 1
# Impulse Response
$$
h[n] = \sum^N_{k=1} A_{k}(d_{k})^n\ u[n]
$$
* See [[Impulse Response]]

