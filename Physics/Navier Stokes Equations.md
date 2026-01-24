The Navier-Stokes equations are a set of [[Partial Differential Equation]]s that describe almost all fluid dynamics. They describe how the velocity, pressure, temperature, and density of a moving fluid are related.
# Incompressible Navier Stokes Equations
For incompressible fluids; if one part of the fluid is displaced, the opposite side is also displaced equally and instantly. Incompressibility means constant density $\rho$.
$$
\begin{gathered}
\frac{\partial}{\partial t}\vec{u} =
- (\vec{u} \cdot \nabla)  \vec{u}
- \frac{1}{\rho} \nabla p 
+ \nu \nabla^2 \vec{u} 
+ \vec{F}_{\text{external}}\\
\nabla \cdot \vec{u} = 0
\end{gathered}
$$
* where $\vec{u}$ is the velocity vector
* where $t$ is time
* where $\rho$ is the density of the fluid
* where $p$ is the pressure of the fluid
* where $\nu$ is the kinematic viscosity
* where $\vec{F}_{\text{external}}$ is the external force
---
* The **first equation** is the moment equation.
	* The **Advection** term
		* $-(\vec{u} \cdot \nabla) \vec{u}$
		* Says that the fluid moves on its own, and moves faster in regions of higher velocity. Shocker.
	* The **Pressure** term
		* $- \frac{1}{\rho} \nabla p$
		* Says that the fluid flow is along a pressure gradient. 
		* This term causes divergence, which is illegal is zero-divergence land, and can be omitted. 
		* We can correct for this omission through **Projection**, which uses [[Helmholtz-Hodge Decomposition]] to isolate the zero-divergence component for a given point in the field. This involves solving the [[Poisson Equation]] and then subtracting the [[Gradient]].
	* The **Diffusion** term
		* $\nu \nabla^2  \vec{u}$
		* Says that the fluid flow tends to diffuse along the velocity gradient, and that the more the fluid diffuses, the smooth the velocity field gets.
	* The **External Force** term
		* $\vec{F}_{\text{external}}$
		* Says "Hello, I am external force"
* The **second equation** is the continuity equation, which enforces incompressibility.
	* At any point, the velocity flow into that point and out of that point must net to zero, i.e. the [[Divergence]] is zero.
* These equations generally cannot be solved [[Analytic Function|analytically]], and instead require [[Numerical Analysis|Numerical Methods]]
