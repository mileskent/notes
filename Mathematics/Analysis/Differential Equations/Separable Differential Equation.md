---
date: 2025-10-15
---

$$
\frac{dy}{dt} = f(t)\cdot g(y)
$$
# Techniques
## Separation of Variables
Given a separable differential equation, it is guaranteed that a n [[Implicit Solution]] formula can be derived. An [[Explicit Solution]] for $y$ may be possible.
$$
\begin{align}
\frac{dy}{dt} =& f(t)\cdot g(y)\\
\frac{1}{g(y)}\ dy =& f(t)\ dt\\
\int \frac{1}{g(y)}\ dy =& \int f(t)\ dt\\
\end{align}
$$

### Example 1
$$
\begin{align}
\frac{dy}{dt} =&\ e^{2y} \cos(t) \\
\int e^{-2y} \ dy =&\int \cos(t)\ dt\\ 
-\frac{1}{2} e^{-2y} =&\ \sin(t) + C_1 \quad\leftarrow\quad \text{implicit sol.}\\ 
e^{-2y} =&\ -2\sin(t) + C\\ 
y(t) =&\ -\frac{1}{2}\ln(-2\sin(t) + C)\quad\leftarrow\quad \text{explicit sol.}\\ 
\end{align}
$$
