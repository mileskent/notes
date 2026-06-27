---
date: 2025-10-15
---
An [[Integral Transform]] that converts a function $f(t)$ with $t \in \mathbb{R}$ (usually time domain) to a function $F(s)$ with $s \in \mathbb{C}$ (frequency domain)
$$
F(s) = \mathcal{L}\{f(t)\}(s) = \int^{t = \infty}_{t = 0} e^{-st}f(t)\ dt
$$
The Laplace Transform is useful because it can convert nth order derivatives into nth order polynomials. Therefore, it can be used to simplify complicated [[Linear Differential Equation]]s into *complicated* equations of polynomials. 
$$
\mathcal{L}\left\{ \frac{d^n}{dx^n} y(x)\right\}
= s\mathcal{L}\left\{\frac{d^{n-1}}{dx^{n-1}} y(x)\right\} - \frac{d^{n-1}}{dx^{n-1}} y(0)
$$


The discrete-time analog is the [[Z Transform]], related by $z = e^{sT}$ where $T$ is the [[Sampling|sampling interval]].

The Laplace transform is an integral transform, so it abides by all the properties of integrals.
$$
\mathcal{L}\{Cf(t)\} = 
C \mathcal{L}\{f(t)\}
$$
$$
\mathcal{L}\{f(t) + g(t)\} = 
\mathcal{L}\{f(t)\} +
\mathcal{L}\{g(t)\}
$$
$$
\mathcal{L}\{f(t) * g(t)\} = \mathcal{L}\{f(t)\} \cdot \mathcal{L}\{g(t)\}
$$
# Common Transforms

| $f(t)$         | $\mathcal{L}\{f(t)\}(s)$      |
| -------------- | ----------------------------- |
| $e^{at}$       | $\frac{1}{s-a}$               |
| $\cos(at)$     | $\frac{s}{s^2+a^2}$           |
| $\sin(at)$     | $\frac{a}{s^2+a^2}$           |
| $t^n e^{at}$   | $\frac{n!}{(s-a)^{n+1}}$      |
| $t^n f(t)$     | $(-1)^n \frac{d^n}{ds^n}F(s)$ |
| $H(t-a)f(t-a)$ | $e^{-as}F(s)$                 |
| $\delta(t-a)$  | $e^{-as}$                     |
# Example [[Ordinary Differential Equation|ODE]]
$$
y''+y'-6y = 50e^t, y(0) = c_{1}, y'(0) = c_{2}
$$
Apply Laplace transform to both sides
$$
\text{Let } Y(s) = \mathcal{L}\left\{y(t)\right\}(s)
$$
$$
Y(s) (s^2+s-6) - (s+1)c_{1} - c_{2} = \frac{50}{s-1}
$$
$$
Y(s) = \frac{\frac{50}{s-1} + (s+1)c_{1}+c_{2}}{s^2+s-6} = \frac{50 + (s-1)(c_{1}s + c_{1}+c_{2})}{(s-1)(s-2)(s+3)} = \frac{A}{s-1} + \frac{B}{s-2} +\frac{C}{s+3}
$$
$$
\mathcal{L}\{Y(s)\} = \mathcal{L}\{\frac{A}{s-1} + \frac{B}{s-2} +\frac{C}{s+3}\}
$$
$$
y(t) = Ae^t + Be^{2t} + Ce^{-3t}
$$
You would do [[Partial Fractions]] to get the values of the coefficients here. 
Though [[Method of Undetermined Coefficients]] or [[Variation of Parameters]] will be faster in most situations, the Laplace Transform can have its place as a solution method for these kind of problems.
For example, the [[Characteristic Equation]] for the homogenous equation gives $\lambda = 2,-3$, so we instantly get 2/3 of the terms for the solution with minimal effort. Whereas with this method, it takes forever.

# [[Ordinary Differential Equation|ODE]] with [[Step Function]]
$$
y''+4y'+4y = f(t), \quad y(0) = -1, y'(0) = 2
$$
$$
f(t) 
= \begin{cases}
16e^{2t},  & t < 3 \\
0,& t \geq 3
\end{cases}
$$
$$
f(t) = (1-H(t-3)) 16e^{2t} = 16e^{2t} - H(t-3) \cdot 16e^{2t}
$$
where $H$ is the [[Heaviside Step Function]]
Apply [[Laplace Transform]] to both sides.
$$
\mathcal{L}\left\{y''+4y'+4y\right\} = (s^2 + 4s + 4) \cdot Y(s) + s + 2
$$
$$
\mathcal{L}\left\{16e^{2t} - H(t-3) \cdot 16e^{2t}\right\}=
\mathcal{L}\left\{16e^{2t}\right\} - \mathcal{L}\left\{H(t-3) \cdot 16e^{2t}\right\}
$$
$$
\mathcal{L}\left\{16e^{2t}\right\} - \mathcal{L}\left\{H(t-3) \cdot e^6 \cdot 16e^{2(t-3)}\right\} = 
\mathcal{L}\left\{16e^{2t}\right\} - e^6 \cdot 16 \cdot\mathcal{L}\left\{H(t-3) \cdot g(t-3)\right\}
$$
$$
\frac{16}{s-2} - 16e^6 \cdot e^{-3s} G(s) = 
\frac{16}{s-2} - 16e^6 \cdot e^{-3s} \frac{1}{s-2} = \frac{16}{s-2}(1 - e^{6-3s})
$$
$$
Y(s) = \left(\frac{16-16e^{6-3s}}{s-2}-s-2\right) \cdot \frac{1}{s^2+4s +4}
$$
$$
Y(s) = \frac{16-16e^{6-3s} - (s+2) \cdot (s-2)}{(s-2)(s+2)^2} = \frac{A}{s-2} + \frac{B}{s+2} + \frac{C}{(s+2)^2}
$$
Solve the [[Partial Fractions]]
Take inverse Laplace of both sides.
$$
y(t) = Ae^{2t} + Be^{-2t} + Cte^{-2t}
$$
