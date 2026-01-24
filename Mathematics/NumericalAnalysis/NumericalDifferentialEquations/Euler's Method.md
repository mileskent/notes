---
date: 2025-10-15
---
A numerical method for approximating the values of a solution $y(t)$ of a [[Differential Equation]], by discretizing the differential equation into a difference equation that can be used to find the approximate solution $y_n$ through recursive definition. Similar methods include [[Heun's Method]] and [[Runge-Kutta Method]]

$$
y' = f(t, y),\ y(t_{0}) = y_{0}
$$
$$
t_{n}, y_{n} \rightarrow t_{n+1},y_{n+1}
$$
![[Pasted image 20251206173529.png|300]]
* $t_{n+1} =t_{n} + h$
* $y_{n+1} = y_{n} + hk_{n}$
* where $k_{n} = f(t_{n}, y_{n})$
* Local Truncation Error: $O(h^2)$
* Global Truncation Error: $O(h)$

# Discrete Derivative
$$
(Dy)(t_{n}) = \frac{y_{n+1} - y_{n}}{h} = \frac{y(t_{n + 1}) - y(t_{n})}{h}
$$
# Example
$$
\begin{gathered}
y' = 2y - 1\\
y(0) = 1
\end{gathered}
$$
This is the differential equation we are starting with.
Let $h$ be the time step between approximations. It will be $\frac{1}{10}$ in this example.
Use the initial condition to find $y_{0}$
$$
y(0) = 1 \implies y(t_{0}) = y_{0} = 1
$$
Equate the discrete derivative and the true derivative
$$
\begin{gather}
\frac{y_{n+1} - y_{n}}{h} = y'\\
\frac{y_{n+1} - y_{n}}{h} = 2y_{n} - 1 \\
y_{n+1} = h(2y_{n} - 1) + y_{n} \\
y_{n+1} = (2h + 1)y_{n} - h \\
\end{gather}
$$
We have a recursive definition of $y_n$ for arbitrary $n$
Now let's find the error at $t_{1}$
Find the discrete $y_{1}$
$$
\begin{gathered}
y_{1} = \left( 2 \frac{1}{10} + 1 \right)y_{0} = \frac{1}{10} \\
y_{1} = \left( 2 \frac{1}{10} + 1 \right)\cdot {1} - \frac{1}{10} \\
y_{1} = \frac{11}{10} \\
\end{gathered}
$$
Find the exact solution $\phi(t)$ to the original system
$$
\begin{gathered}
\phi' = 2\phi - 1\\
\frac{\phi'}{2\phi - 1} = 1\\
\int \frac{\phi'}{2\phi - 1} dt = \int 1 dt\\
\int \frac{d\phi}{2\phi - 1} = t + C\\
\int \frac{d\phi}{2\phi - 1} = t + C\\
\text{Let } u = 2\phi - 1 \implies du = 2 d \phi\\
\frac{1}{2}\ln(2\phi - 1) = t + C\\
\ln(2\phi - 1) = 2t + C\\
2\phi - 1 = Ce^{2t}\\
\phi = Ce^{2t} + \frac{1}{2}\\
\phi(0) = 1 \implies C + \frac{1}{2} = 1 \implies C = \frac{1}{2}\\
\therefore \phi(t) = \frac{1}{2} e^{2t} + \frac{1}{2}
\end{gathered}
$$
$E_{1} = \phi_{1} - y_{1} = \frac{1}{2}e^2 + \frac{1}{2} - \frac{11}{10} \approx 3.095$

Find $E_{n} = \phi_{n} - y_{n}$
$$
\phi_{n} = \frac{1}{2} \exp(2 t_{n}) + \frac{1}{2}
$$
$$
y_{n} = (2h + 1)y_{n-1} - h
$$
$$
\frac{1}{2} \exp(2t_{n}) + \frac{1}{2} - (2h + 1) y_{n-1} +h
$$
some taylor series stuff happens here
$$
E_{n} = \frac{1}{2} h^2 \phi''_{n}
$$