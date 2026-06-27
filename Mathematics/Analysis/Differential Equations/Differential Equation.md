---
date: 2025-10-15
---
An [[Equation]] in which the unknowns are functions. Solve for $y(t)$ in the below. 
$$
y'(t) = 3y(t) + t^3
$$
# Types
[[Ordinary Differential Equation]]
[[Partial Differential Equation]]
[[Linear Differential Equation]]
[[Homogeneous Differential Equation]]
[[Separable Differential Equation]]
[[Systems of Differential Equations]]
# Properties
## Order
The order of a differential equation is the maximum derivative degree of the function of interest, e.g. $y(t)$, in the equation. 

# Techniques
[[First Order Linear Differential Equation#Integrating Factor]]
[[Separable Differential Equation#Separation of Variables]]

# Special Examples
## Population Dynamics
### Linear Model
$$
y' = ry \iff y(t)=y_0e^{rt}
$$
where $k$ is the net rate of change [per capita](https://en.wikipedia.org/wiki/Per_capita)

### Nonlinear Logistic Model
Do not assume growth rate $g$ to be constant, but that it depends on $y$
Assume that when $y \approx 0, g \approx r > 0$
Assume that when $y \approx k, g < 0$
Where $r$ is the intrinsic rate
Where $k$ is the carrying capacity 
$$
g = r\left( 1-\frac{y}{k} \right)
$$
$$
y=\frac{Ky_{0}}{y_{0}+(k-y_{0})\exp(-rt)}
$$

## [Newton's Law of Cooling](https://www.sciencefacts.net/newtons-law-of-cooling.html)
$$
T'(t) = -k(T(t) - T_\text{ambient})
\iff
T(t)=(T_0  -  T_\text{ambient})e^{-kt} +  T_\text{ambient}
$$

# Maximum Interval of Existence
The maximal interval of existence refewrs to the largest interval over which a solution to an initial value problem (IVP) of a differential equation is defined and unique.

## Case 1
For both [[Linear Differential Equation]] and [[Nonlinear Differential Equation]], if $f(t,y)$ has discontinuities, solutions for $y(t)$ may not exist beyond the discontinuities of $f$, and the $t$ intervals of existence have become limited.
$$
\frac{dy}{dt} = f(t,y) = \frac{t-y}{t-7}
$$
General Solution
$$
y(t) = \frac{t^2 + C}{2(t-7)}
$$

| (t,y(t)) | Maximal Interval of Existence |
| -------- | ----------------------------- |
| (-6,2)   | $(-\infty, 7)$                |
| (11,10)  | $(7, \infty)$                 |
 Basically, the given point determines $C$, and depending on what $C$ is, the [[#Maximum Interval of Existence]] of the solution changes.

## Case 2
For some [[Nonlinear Differential Equation]], even if $f(t,y)$ is differentiable everywhere, solutions for $y(t)$ may not exist beyond some limited $t$ intervals.
$$
\frac{dy}{dt} = \frac{y^2}{6}
$$
$$
y(t) = \frac{-6}{t+C}
$$
The [[#Maximum Interval of Existence]] follows the same pattern here. The point of case 2 is that even if your starting equation is continuous everywhere, your solution may not be, thus limiting the domain of $t$