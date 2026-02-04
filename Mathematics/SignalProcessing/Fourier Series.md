---
date: 2025-02-03
---
* e.g. plotting a [[Square Wave]] as a sum of sinusoids
* Any function can be composed of a sum of [[Even Function]]s and [[Odd Function]]s
	* [[Fourier Cosine Series]]
	* [[Fourier Sine Series]]
$$
f(t) = \mathbb{E}(t) + \mathbb{O}(t)
$$
$$
f(t) = \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{E}_{m}\cos(mt)\ +\ \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{O}_{m}\sin(mt)
$$
$$
\text{where } \mathbb{E}_{m} = \int \mathbb{E}(t) \cos(mt) dt = \int f(t) \cos(mt) dt
$$
$$
\text{where } \mathbb{O}_{m} = \int \mathbb{O}(t) \sin(mt) dt = \int f(t) \sin(mt) dt
$$
The $f_{\mathbb{E}}$ in the odd integral and the $f_{\mathbb{O}}$ in the even integral both integrate to zero, which is why we just simplify to $f(t)$
