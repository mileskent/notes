---
date: 2025-02-03
---
$$
E(x',y') \propto \int \int t(x,y) \cdot \exp(-ik\frac{x x' + y y'}{z})\ dx\ dy
$$
$$
E(k_{x},k_{y}) \propto \mathcal{F}^{(2)}(t(x,y)) = 
 T(k_{x}, k_{y}) = 
\int \int t(x,y) \exp(-i(k_{x}x + k_{y}y))\ dx\ dy
$$
See [[2D Fourier Transform]], [[Fourier Transform]]

> [!tip]- Derivation [[Fresnel Diffraction]]
> Recall [[Fresnel Diffraction]], which will be our starting point.
> $$
> E(x',y') \propto \int \int \underbrace{t(x,y)}_{\text{Aperature Fn}} \cdot \underbrace{E(x,y)}_{\text{Electric Field}} \cdot \underbrace{\frac{\exp(ikr)}{r}}_{\text{Spherical Wave}}
> dx\ dy
> $$
> $$
> \text{where } r = \sqrt{ z^2 + (x' - x)^2 + (y' - y)^2 }
> $$
> 
> $z$ being signficantly larger than the other distances allows a useful approximation for the denominator of the [[Spherical Wave]]
> $$
> z \gg x', x, y', y \implies r = z
> $$
> However, small changes in $r$ will lead to big changes in the exponential function of the equation so we can't apply the approximation there.
> Instead,
> 
> Overall we end up with
> **Equation 1**
> $$
> E(x',y') \propto \int \int t(x,y) \cdot \exp(-ik\frac{x x' + y y'}{z})\ dx\ dy
> $$
> Let $k_{x} = \frac{kx'}{z}$, $k_{y} = \frac{ky'}{z}$
> Allowed due to $z \gg \dots$ assumption 
> See [[2D Fourier Transform]]
> **Equation 2**
> $$
> \therefore E(k_{x},k_{y}) \propto
> \mathcal{F}^{(2)}(t(x,y))
> $$
> 

	
#### Examples
> [!Example]- Fraunhofer Diffraction from a Slit
> Fraunhofer Diffraction from a slit is just the [[Fourier Transform]] of the $\text{rect}$ function, which is the [[sinc]] function. The [[Irradiance]] is $\text{sinc}^2$
> $t(x) = \text{rect}\left( \frac{x}{w} \right)$
> $E(k_{x}) \propto \mathcal{F}\left(t(x)\right)$
> $$
> E(k_{x}) \propto \text{sinc}\left( \frac{wk_{x}}{2} \right)
> \quad
> E(x') \propto \text{sinc}\left( \frac{wk_{x'}}{2z} \right)
> $$
> $$
> I(k_{x}) \propto \text{sinc}^2\left( \frac{wk_{x}}{2} \right)
> \quad
> I(x') \propto \text{sinc}^2\left( \frac{wk_{x'}}{2z} \right)
> $$
> Also, through a square hole, would just be the same idea, but for $x'$ and $y'$
