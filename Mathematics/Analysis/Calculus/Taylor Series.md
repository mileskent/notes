---
date: 2026-01-11
---
![[Pasted image 20251225190208.png|200]]
An infinite [[Series]] representing a [[Computer Science/Architecture/Function]], expressed in terms of the function's derivatives at a single point. It allows complex functions to be approximated by [[Polynomial]]s.

If a function $f(x)$ is infinitely differentiable at a point $a$, the Taylor series centered at $x = a$ is the following:
$$
f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x - a)^{n}
$$
Expanded, this looks like:
$$
f(x) = f(a) + \frac{f'(a)}{1!}(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \dots
$$

![[Maclaurin Series]]

# Common Series
$$
e^x = \sum^{\infty}_{n = 0} \frac{x^n}{n!}
\quad\quad x \in \mathbb{R}
$$
$$
\sin(x) = \sum^{\infty}_{n = 0} (-1)^n\frac{x^{2n + 1}}{(2n + 1)!}
\quad\quad x \in \mathbb{R}
$$
$$
\cos(x) = \sum^{\infty}_{n = 0} (-1)^n\frac{x^{2n}}{(2n)!}
\quad\quad x \in \mathbb{R}
$$
$$
\ln(x) = \sum^{\infty}_{n=1} \frac{(-1)^{n+1}}{n} (x-1)^n
\quad\quad x \in (0,2]
$$
