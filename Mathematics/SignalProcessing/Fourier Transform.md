---
date: 2025-02-03
---
An approach for computing what frequencies are present in a [[Wave]], in particular the [[Spectrum]], entirely from its dependence on time.
Allows us to transform a function between time an frequency domains.
Allows us to quantitivatively define the [[Spectrum]] of a [[Wave]]
A [[Gaussian]]'s transform is another Gaussian.
* Frequency is conjugate to time
* Spatial frequency is conjugate to position
Anytime the Fourier Transform is involved, so is the [[Scale Theorem]], and the [[Uncertainty Principle]]
##### Equation
$$
F(\omega) = \int^{\infty}_{{-\infty}} f(t)\ e^{-i \omega t} dt
$$
* Where $F(\omega)$ is called the [[Fourier Transform]] of $f(t)$, containing equivalent information to that in $f(t)$
* $f(t)$ lives in the time domain
* $F(\omega)$ lives in the frequency domain

> [!tip]- With respect to space
A spatial fourier transform. Spatial frequency $k$ is the conjugate of position $x$. 
> $$
> F(k) \equiv \int^{\infty}_{-\infty} f(x) \exp(-ikx)\ dx
> $$

> [!tip]- Derivation from [[Mathematics/SignalProcessing/Fourier Series]]
> Let $F(m) \equiv \mathbb{E}_m - i\ \mathbb{O}_{m}$ 
> where these values are defined in [[Even Function]] and [[Odd Function]] and also [[Mathematics/SignalProcessing/Fourier Series]]
> $$
> \begin{align} \\
> F(m) \equiv
> \mathbb{E}_m - i\ \mathbb{O}_{m} = \\
> \int f(t) \cos (mt) dt - i\ \int f(t) \sin(mt) dt = \\
> \int f(t) e^{-imt} dt
> \end{align}
> $$
> Allow t to range from $-\infty$ to $\infty$, $m$ to be continuous [[Frequency]] $\omega$, i.e. for a continuous range of frequencies
> $$
> F(\omega) = \int^{\infty}_{{-\infty}} f(t)\ e^{-i \omega t} dt
> $$

##### Inverse Equation
$$
f(t) = \frac{1}{2 \pi}  \int^{\infty}_{{-\infty}} F(\omega) \ e^{-i \omega t} d \omega
$$

> [!tip]- Derivation from [[Mathematics/SignalProcessing/Fourier Series]]
> Note that the $i$ gets factored in for consistency with the above derivation.
> $$
> \begin{aligned}
> f(t) = \\
> \mathbb{E}(t) + \mathbb{O}(t) = \\
> \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{E}_{m}\cos(mt)\ +\ \frac{1}{\pi} \sum^{\infty}_{m=0} \mathbb{O}_{m}\sin(mt) =
> \\
> \frac{1}{2} \left(
> \frac{1}{\pi} \int^{\infty}_{-\infty} \mathbb{E}_{m}\cos(mt) dt
> \ +
> \ \frac{1}{\pi} \int^{\infty}_{-\infty} \mathbb{O}_{m}\sin(mt)dt 
> \right)
> =
> \\
> \frac{1}{2} \left(
> \frac{1}{\pi} \int^{\infty}_{-\infty} \left( \mathbb{E}_{m}\cos(mt) 
> \ +
> i \ \mathbb{O}_{m}\sin(mt) \right) dt
> \right)
> =
> \\
> \frac{1}{2} \left(
> \frac{1}{\pi} \int^{\infty}_{-\infty} \left( F(\omega)\cos(mt) 
> \ +
> i \ F(\omega)\sin(mt) \right) dt
> \right)
> =
> \\
> \frac{1}{2} \left(
> \frac{1}{\pi} \int^{\infty}_{-\infty} F(\omega) e^{- i \omega t} dt
> \right)
> =\\
> \frac{1}{2 \pi}  \int^{\infty}_{{-\infty}} F(\omega) \ e^{-i \omega t} d \omega\
> \end{aligned}
> $$

> [!tip]- With respect to space 
> $$
> f(x) = \frac{1}{2\pi} \int^{\infty}_{-\infty} F(k) \exp(ikx) dk
> $$

## Notation
If original function lowercase, use above notation
* $f(t)$ for the function
* $F(\omega)$ for the transform
If the original function is uppercase:
* $E(t)$ for the function, arbitrarily
* For the transform
	* $\mathcal{F}\left(E(t)\right)$ 
	* $\tilde{E}(\omega)$

### Examples
> [!example]- Find $\mathcal{F}(\text{rect}(t))$
> $$
> \begin{align} \\
> F(\omega) = \int^{0.5}_{-0.5} \exp(-i \omega t) dt = \\
> \frac{1}{-i\omega}(\exp(-i \omega t))^{0.5}_{-0.5} = \\
> \frac{1}{-i \omega}\left( \exp\left( -\frac{i\omega}{2} \right) - \exp\left( \frac{i\omega}{2} \right) \right) =\\
> \frac{1}{\frac{\omega}{2}} \frac{\exp\left( \frac{i\omega}{2} \right) - \exp\left( -\frac{i\omega}{2} \right)}{2i}= \\
> \frac{\sin\left( \frac{w}{2} \right)}{\frac{\omega}{2}}  \equiv \\
> \text{sinc}\left( \frac{\omega}{2} \right)
> \end{align} \\
> $$
See [[sinc]] for more info

### Fourier Transform of the Complex Conjugate of a Function
$$
\mathcal{F}(f^*(t)) = F^*(\omega) = F^*(-\omega)
$$
### [[Scale Theorem]]

### [[Modulation Theorem]]

### Fourier Transform of the Sum of Two Functions
$$
\mathcal{F}(a \cdot f(t) + b \cdot g(t)) = a \mathcal{F}(f(t)) + b \mathcal{F}(g(t))
$$
### [[Shift Theorem]]

### [[2D Fourier Transform]]
