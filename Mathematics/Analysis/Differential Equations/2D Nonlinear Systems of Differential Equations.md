---
date: 2025-10-15
---
$$
\begin{bmatrix}
x' \\
y'
\end{bmatrix}
= \vec{F}(x, y)
= \begin{bmatrix}
f(x,y) \\
g(x,y)
\end{bmatrix}
$$

# Equilibria
Find the equilibria by solving for all $(x, y)$ that satisfy $\vec{F} = \vec{0}$
# Linearization
Find the [[Linearization]] of the system.
$$
\begin{bmatrix}
x' \\
y'
\end{bmatrix}
= \begin{bmatrix}
f(x,y) \\
g(x,y)
\end{bmatrix}
\quad \implies \quad
\begin{bmatrix}
x' \\
y'
\end{bmatrix} = \vec{F}(\text{EP}) + J_{\vec{F}(\text{EP})} \begin{bmatrix}
x - \text{EP.x} \\
y - \text{EP.y}
\end{bmatrix}
$$
where $J_{\vec{F}(EP)}$ is the [[Jacobian]] matrix at a particular equilibrium point

where EP is each [[Equilibrium Point]], where EP.x and EP.y are the x and y components

By definition at an equilibrium point, the function is equal to $\vec{0}$. See [[#Equilibria]].

Therefore the linearization becomes this:
$$
\begin{bmatrix}
x' \\
y'
\end{bmatrix} = 
J_{\vec{F}(\text{EP})} 
\begin{bmatrix}
x - \text{EP.x} \\
y - \text{EP.y}
\end{bmatrix}
$$
$$
J_{\vec{F}(\text{EP})} = \begin{bmatrix}
f_x & f_y \\
g_x & g_y
\end{bmatrix} @\ \text{EP}
$$
The final expression for the linearization looks like this.
$$
\begin{bmatrix}
x' \\
y'
\end{bmatrix} = 
\left(
\begin{bmatrix}
f_x & f_y \\
g_x & g_y
\end{bmatrix} @\ \text{EP}
\right)
\begin{bmatrix}
x - \text{EP.x} \\
y - \text{EP.y}
\end{bmatrix}
$$
This is a [[Shifted Systems of Linear Differential Equations]]
## Linearization in 1D with Complex Polynomials
$$
\text{Let }y' = f(y) = -\frac{1}{16}(y+1)^3(y-2)^2y(y-3)(y-3)
$$
The equilibrium points of this equation are $y = -2,-1,0,2,3$
The linearization at an equilibrium point is
$$
y'=J_{f(\text{EP})}(y-\text{EP}) = f'(\text{EP})(y-\text{EP})
$$
$$
y'=J_{f}(y-\text{EP}) = f'(y-\text{EP})
$$
In short, if you have a polynomial of order 1, the linearization is just f, but you drop the EP term.
If the order is greater than 1, then the linearization is 0.
$$
\begin{gathered}
\textbf{Case: } y = -2\\
    f(y) = -\frac{1}{16} \cdot (y+1)^3 \cdot (y-2)^2 \cdot y \cdot (y-3) \cdot (y+2)\\
    \text{Define a function with every factor, besides the -2 term.} \\
    \text{Let } G(y) = -\frac{1}{16} \cdot (y+1)^3 \cdot (y-2)^2 \cdot y \cdot (y-3)\\
    f(y) = G(y) \cdot (y+2)\\
    f'(y) = G'(y) \cdot (y+2) + G(y)\\
    f'(-2) = G'(-2) \cdot (-2+2) + G(-2) = G(-2)\\
    y' = f'(-2)(y+2) = G(-2)(y+2) = 10(y+2)\\
    \text{Linearization: } \boxed{y' = 10(y+2)}\\
     \\
    \textbf{Case: } y = -1\\
    f(y) = -\frac{1}{16} \cdot (y+1)^3 \cdot (y-2)^2 \cdot y \cdot (y-3) \cdot (y+2)\\
    \text{Define a function with every factor, besides the -1 term.} \\
    \text{Let } H(y) = -\frac{1}{16}\cdot (y-2)^2 \cdot y \cdot (y-3) \cdot (y+2)\\
    f(y) = H(y) \cdot (y+1)^3\\
    f'(y) = H'(y) \cdot (y+1)^3 + H(y) \cdot 3(y+1)^2\\
    f'(-1) = H'(-1) \cdot (-1+1)^3 + H(-1) \cdot 3(-1+1)^2 = 0\\
	y' = f'(-1)(y+1) = 0\\
    \text{Linearization: } \boxed{y' = 0}\\
\end{gathered}
$$
## Perterbation
Given
$$
\vec{v}' = A \vec{v}
$$
Which is the exact form of the homogenous part of our [[#Linearization]], except we have
$$
\vec{v} = J_{\vec{F}(\text{EP})} (\vec{v} - \text{EP})
$$
Neutral [[Eigenstuff#Eigenvalue]]s ($\mathrm{Re}\ \lambda = 0$) lead to structural instability, e.g. a perterbation leads to signficant change.

# Approximating Dynamics
Given 
$$
\vec{v} = J_{\vec{F}(\text{EP})} (\vec{v} - \text{EP})
$$
We approximate the dynamics of the original system, by finding the dynamics of the [[#Linearization]]
* TLDR: We find the [[Eigenstuff]] of the [[Jacobian]], and use that to construct our [[Phase Portrait]]
* If the eigenvalues of the Jacobian lead to Unstable or Asymptotically Stable, then the approximation is sufficient to determine the dynamics of the original system
* If Stable, we consider the approximation "degenerate", and conclude that the approximation is insufficient.
# Lotka-Volterra Competition Model
$$
\frac{d🐺}{dt} = g_{🐺} 🐺 \left(1 - \frac{🐺}{K_{🐺}} - \alpha_{🐺🐯} \frac{🐯}{K_{🐺}}\right) 
$$
$$
\frac{d🐯}{dt} = r_{🐯} 🐯 \left(1 - \frac{🐯}{K_{🐯}} - \alpha_{🐯🐺} \frac{🐺}{K_{🐯}}\right)
$$

where $🐺$, $🐯$ are population sizes

where $g_{🐺}$, $r_{🐯}$ are intrinsic per capita growth rates

where $K_{🐺}$, $K_{🐯}$ are carrying capacities.

where $\alpha_{🐺🐯}$, $\alpha_{🐯🐺}$ are competition coefficients
* where $\alpha_{🐺🐯}$ measures the negative effect tigers have on wolves
* where $\alpha_{🐯🐺}$ measures the native effect wolves have on tigers
# Lotka-Volterra Predator-Prey Model
$$
\frac{d🐰}{dt} = \alpha 🐰 - \beta 🐰 🐺
$$
$$
\frac{d🐺}{dt} = \delta 🐰 🐺 - \gamma 🐺
$$
where🐰 is the prey population size

where 🐺 is the predator population size

where $\alpha$ is the prey growth rate (birth rate)

where $\beta$ is the predation rate/interaction rate

where $\gamma$ is the predator death rate

where $\delta$ is the conversion efficiency of prey into new predators.