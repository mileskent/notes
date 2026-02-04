---
date: 2025-02-03
---
A generalization of [[Special Relativity]] that expands it to non-[[Inertial Reference Frame]]s, i.e. accelerated frames.
The idea that [[Gravity]] bends [[Spacetime]], acceleration and gravity are indistinguishable. 
# Principle of Equivalence
## Inertial Mass
*Intertial mass* measures how strongly an object resists a change in its motion
$$
m_{\text{intertial}} = \frac{F}{a}
$$
## Gravitational Mass
*Gravitational mass* measures how strongly an object attracts and is attracted by other objects
$$
m_{\text{gravitational}} = \frac{F}{g}
\quad\quad \text{where } g = \frac{GM}{r^2}
$$
## Realization
Combining the two equations
$$
a = \frac{m_{\text{gravitational}}}{m_{\text{inertial}}}g
$$
In order to say that the acceleration is equal $g$, both masses must be equivalent. 
This equivalence is important, as the resistance to change in motion and the attraction to other bodies aren't obviously related. 
Consider the experience of a person on the surface of the earth. They experience an acceleration of $g$ into the ground. They drop an object and it falls to the floor, accelerating at $g$.
Consider the experience of a person in a rocket in space, accelerating at $g$. They experience an acceleration of $g$ into the floor of the rocket. They drop an object and it falls to the floor, accelerating at $g$.
A person cannot tell the difference between the two situation.
*There is no experiemnt that can be done in a small confined space that can detect the difference between a uniform gravitational field and an equivalent uniform acceleration*
Therefore, acceleration and gravitation are indistinguishable.
# Curvature of Spacetime
The modeling of the above effects as to the curvature of [[Spacetime]], due to matter. 
![[6a0df9c4ce8fa08bcf57a56d1d3348df-3876655267.gif|300]]
![[gr-238051487.gif|300]]

[[Light]], for example, travels straight from its frame. However, because spacetime may be curved, this straight line would also be curved. 
See [https://en.wikipedia.org/wiki/Geodesic](https://en.wikipedia.org/wiki/Geodesic)
A good example of visualizing what this could look like is: imagine a commerical flight traveling from New York to London. Ignore currents in the earth's atmosphere. In order to minimize costs, we want to fly in a straight line directly from one city to another. However, because our space is curved, on account of being spherical, the path is not straight in the layman sense, but it minimizes the path length between the two points on the globe so it *is* by definition a straight line.
![[Pasted image 20250421114242.png|800]]
# Consequences
## Light Bending
Consider traveling in a spaceship at acceleration $g$ where gravity is negligible. There is some incident light. This light takes time to travel, so it will pass the closer side of the ship higher than the farther side of the ship.
![[Pasted image 20250421112840.png|350]]
From the accelerated frame, the light apparently curves down.
![[Pasted image 20250421113011.png|350]]
The [[#Principle of Equivalence]] implies that at rest on Earth, the light must also bend downward in this way.
![[Pasted image 20250421113044.png|350]]
## Gravitational Doppler Effect
[[#Principle of Equivalence]] implies a Doppler shift of light, proportional to Earth's gravity. A light pulse shone vertically upward will lose energy as it travels up, just as a rock thrown up would, due to gravity. Because $E = h \nu$ ([[Planck's Radiation Law]]), the frequency of the light is shifted due to gravity.
Light shone towards the Earth is blue-shifted, and light shone away from the earth is red-shifted.
In the case of a typical rock being thrown, it will probably not reach escape velocity, while light generally will. However, the case of light failing to reach espace velocity would be that of a [[Black Hole]]. See [[Schwarzschild Radius]]

# Spacetime Metric
For [[Special Relativity]] first
By Einstein Notation, there is implicit summation over the whole range
$$
\Delta s^2 
= \eta_{\mu \nu}\Delta x^\mu \Delta x^\nu
\equiv \sum_{\mu=0}^3\sum_{\nu=0}^3 \eta_{\mu \nu}\Delta x^\mu \Delta x^\nu
$$
For General Relativity
$$
\Delta s^2 = g_{\mu \nu}\Delta x^\mu \Delta x^\nu
$$
# Eistein Tensor
$$
G_{\mu \nu} = R_{\mu \nu} - \frac{1}{2} R g_{\mu \nu}
$$
See [[Ricci Tensor]], [[Christoffel Symbol]]

# Einstein's Field Equations
$$
G_{\mu \nu} = \frac{8\pi}{c^4} G T_{\mu \nu}
$$
## Correspondence Principle
Einstein's Field Equations reduce to Newton's Law of Gravity in the weak-field and slow-motion limit.
# See also
[[Einstein's Field Equations]]
[[Inertial Reference Frame]]
