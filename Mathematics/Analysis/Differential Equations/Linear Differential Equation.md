---
date: 2025-10-15
---
A [[Differential Equation]] is linear if terms appear only as
$$
f(t) \cdot y^{(n)}(t)
$$
Note that $y^{(n)}(t)$ is the $n^\text{th}$ derivative of $y(t)$ in Lagrange notation.

 Linear equations can usually be solved completely and explicitly

| Linear                        | Nonlinear           |
| ----------------------------- | ------------------- |
| $y'+2y=0$                     | $y'+y^2 = 0$        |
| $y'+2y=t^2$                   | $y'+y^2 = t^2$      |
| $y'+t^3y=0$                   | $y'+ty^3 = 0$       |
| $t^2 y''' - \cos(t)y''+y = 0$ | $y''+3yy'=7\cos(t)$ |

# First Order
A [[Linear Differential Equation]] of [[Differential Equation#Order|Order]] 1. We are assuming it to be a [[Ordinary Differential Equation]].
## Homogeneity
### [[Nonhomogenous Differential Equation]]
$$
\boxed{\frac{dy}{dt} + a(t)\ y = b(t)}  \quad \quad \text{Nonhomogenous}\\
$$
**Solution Method**
* [[#Integrating Factor]]
* [[Separable Differential Equation#Separation of Variables]]
**General Solution**
$$
y(t) = Cy_{1}(t)
$$
where $C$ is a free parameter
where $y_1(t)$ is a nonzero solution
### [[Homogeneous Differential Equation]]
$$
\boxed{\frac{dy}{dt} + a(t)\ y = 0} \quad \quad \text{Homogenous}
$$
**Solution Method**
* [[#Integrating Factor]]
**General Solution**
$$
y(t) = y_{p}(t) + Cy_{1}(t)
$$

where $y_p(t)$ is a particular solution of the nonhomogeneous equation
where $C$ is a free parameter
where $y_1(t)$ is the "complementary solutions" of the corresponding homogenous equation

## Integrating Factor
This method only works for [[First Order Linear Differential Equation]], and the coefficient of the derivative must be 1. Works for both [[Homogeneous Differential Equation]] and [[Nonhomogenous Differential Equation]]. This example will use [[Nonhomogenous Differential Equation]].
$$
\begin{align}
\frac{dy}{dt} + a(t)\ y = b(t) \\
\text{Let } A'(t) = a(t) \quad \text{Let } e^{A(t)}y \text{ be the integrating factor}\\
e^{A(t)}y\ \frac{dy}{dt} + e^{A(t)}y\ a(t)\ y = e^{A(t)}y\ b(t) \\
\frac{d}{dt} \left(e^{A(t)}y \right) = e^{A(t)}y\ b(t) \\
e^{A(t)}y = \int e^{A(t)}y\ b(t)\ dt \\
y = e^{-A(t)} \int e^{A(t)}y\ b(t)\ dt + Ce^{-A(t)}\\
\end{align}
$$

# Second Order
### Homogenous with Constant Coefficients
$$
ay'' + by' + cy = 0
$$
Specifically with this form
Recall that we know how to solve [[2D Homogeneous Linear Systems with Constant Coefficients]]
$$
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}' = A
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
$$
Let $x_{1} = y,\ x_{2}=y'$
$$
\begin{bmatrix}
y \\
y'
\end{bmatrix}' = A
\begin{bmatrix}
y \\
y'
\end{bmatrix}
$$
$$
\begin{bmatrix}
y' \\
y''
\end{bmatrix} = A
\begin{bmatrix}
y \\
y'
\end{bmatrix}
$$
So if we can find [[Linear Combination]] of y and y' that yield y' and y'', then we have transformed our 2nd order, 1 dimensional ODE into a 1st order, 2 dimensional ODE.
Well we can do this.
$y' = 0 \cdot y + 1 \cdot y'$
$y'' = -\frac{c}{a}y -\frac{b}{a}y'$
$$
\begin{bmatrix}
y' \\
y''
\end{bmatrix} =
\begin{bmatrix}
0 & 1 \\
-\frac{c}{a} & -\frac{b}{a}
\end{bmatrix}
\begin{bmatrix}
y \\
y'
\end{bmatrix}
$$
Great! Now we can solve this. When you're done you can just use the first component of the vector solution and you will get $y(t)$

Also...
The [[Characteristic Equation]] for this system looks very similar to the initial equation for $a = 1$
$$
y'' +by'+cy = 0 \quad \implies \quad \lambda^2 + b\lambda+c=0
$$
But you can just do it the normal way too if you want.

[[2D Homogeneous Linear Systems with Constant Coefficients#Distinct Real & Nonzero Eigenvalues]]
$$
y(t) = C_{1}\exp(\lambda_{1} t) + C_{2}\exp(\lambda_{2} t)
$$
[[2D Homogeneous Linear Systems with Constant Coefficients#Repeated Real Eigenvalues]]
$$
y(t) = C_{1} \exp(\lambda t) + C_{2}\ t \exp(\lambda t)
$$
[[2D Homogeneous Linear Systems with Constant Coefficients#Complex Eigenvalues]]
$$
y(t) = \exp(\alpha t)\left(C_{1}\cos(\beta t) + C_{2}\sin(\beta t)\right)
$$

### Spring Mass Problem
![[Pasted image 20251013151429.png|400]]