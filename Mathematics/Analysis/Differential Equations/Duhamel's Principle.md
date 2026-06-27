---
date: 2025-10-15
---
$$
y'' + ay' + by = f(t)
$$
Find homogenous solution
$$
y_{h}'' + ay_{h}' + by_{h} = 0
$$
Solve for $h(t)$, using the [[Laplace Transform]]
$$
h'' + ah' + bh = \delta(t)
$$
$$
y_{p}(t) = h * f
$$
where $h * f$ is the [[Convolution]] of $h$ and $f$
$$
y(t) = y_{h}(t) + y_{p}(t)
$$
* $y_{p}$ is called the *Forced Response*
	* It is the solution that arises with the forcing function $f(t)$
	* It typically describes the steady-state behavior of the system
* $y_{h}$ is called the *Natural Response*
	* It is the solution that arises as a result of just the internal dyanmics of the system.
	* In a stable system, the natural response decays to zero, so it is also called the *Transient Response*
