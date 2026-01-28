---
date: 2026-01-28
---
A [[Limit]] that is approximated using [[Numerical Analysis|Numerical Methods]]

Any kind of limit is applicable, but consider the one for a single-variable [[Derivative]], because it comes up in [[Computational Physics]].
$$
\lim_{ \delta \to 0 }  \frac{f(x+\delta) - f(x)}{\delta}
=
\frac{df}{dx}
$$

# Optimal Step Size
A smaller delta DOES NOT equal higher precision. In fact, the relationship is parabolic, i.e. there is a Goldilocks zone.

## The Two Opposing Forces at Play
### Truncation Error
* [[Truncation Error]] is the error the turns up when $\delta \neq 0$; the numerical limit is approximated from one side.
* It is minimized as $\delta \rightarrow 0$
### Floating Point Error
* [[Round-off Error|Floating Point Error]] is the error that is caused by the inherent imprecision of [[Floating Point]]
* It is maximized as $\delta \rightarrow 0$
	* The smaller $\delta$ becomes as a continuous [[Real Number]], the more significant figures of that number are truncated due to the limited precision of the representation
## The Happy Medium
Somewhere between these two extremes, there is an optimal step size of maximum precision, and minimum error.

Total Error vs Delta for approximating the derivative of $e^x$ (Log-Log Scale)
![[optimal_step_size_demo.png|400]]