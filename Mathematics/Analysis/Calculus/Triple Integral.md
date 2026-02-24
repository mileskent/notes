---
date: 2022-12-15
---
An integral over 3 variables.
$$
\iiint_{E} f(\vec{x})\ dV
$$
# Cartesian
$$
\iiint_{E} f(x, y, z)\ dx\ dy\ dz
$$
where $x$ is the amount a point lies in the positive $x$ direction
where $y$ is the amount a point lies in the positive $y$ direction
where $z$ is the amount a point lies in the positive $z$ direction
# Cylindrical
[[Polar Coordinates]] + $z$
$$
\iiint_{E} f(r, \theta, z)\cdot r\ dr\ d\theta\ dz
$$
* where the [[Jacobian#Jacobian Determinant]] $\det J_{f} = r$
* where $r$ is the distance of a point's $xy$ [[Mathematics/Analysis/Calculus/Projection]] from the origin
* where $\theta$ is the angle of the point from the positive $x$ axis
* where $z$ is the amount a point lies in the positive $z$ direction
* where $x = r\cos \theta,\ y = r\sin \theta,\ z = z$
* where $r^2 = x^2 + y^2$
* where $\theta \in [0, 2\pi],\ r\geq 0$
# Spherical
$$
\iiint_{E} f(\rho, \theta, \phi)\cdot \rho^2\sin(\phi)\ dr\ d\theta\ dz
$$
* where the [[Jacobian#Jacobian Determinant]] $\det J_{f} = \rho^2 \sin(\phi)$
* where $\rho$ is the distance of a point from the origin
* where $\theta$ is the angle of the point from the positive $x$ axis
* where $\phi$ is the angle of the point from the positive $z$ axis
* where $r = \rho \sin \phi$
* where $x = \rho \sin \phi \cos \theta,\ y = \rho \sin \phi \sin \theta,\ z = \rho \cos \phi$
* where $\rho^2 = r^2 + z^2$
* where $\theta \in [0,2\pi],\ \phi \in [0,\pi],\ \rho \geq 0$
