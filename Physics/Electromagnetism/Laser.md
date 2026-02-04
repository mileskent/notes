---
date: 2025-02-03
---
A laser is a medium that stores energy, surroudned by two mirrors. A partially reflecting output mirror lets some light out.
![[Pasted image 20250402150921.png|400]]

* Laser has "modes"/frequencies
* See [[Light]]
* [[Light Delay]]
* Emits [[Plane Wave]]s

## Gain
$$
G \equiv \exp(\sigma(N_{2} - N_{1}) L )
$$
$g, \alpha$ are gain and absorption coefficients
$$
N_{2} < N_{1} \rightarrow \alpha \equiv (N_{1}-N_{2}) \sigma
\quad\quad
N_{2} > N_{1} \rightarrow g \equiv (N_{2}-N_{1}) \sigma
$$
### Inversion
$$
N_{2} > N_{1}
\quad
\equiv
\quad
\Delta N < 0
$$
![[Pasted image 20250402151249.png|400]]
![[Pasted image 20250402151447.png|400]]
### N-Level System
$\Delta N = N_{1} - N_{2}$, so $\Delta N < 0 \iff$ inversion
###### 2 Level System
$$
\Delta N = \frac{N}{1 + 2I_{\text{pump}}/I_{\text{sat}}}
$$
$\Delta N$ is always positive and it is impossible to achieve an inversion.
###### 3 Level System
$$
\Delta N = N \frac{1-I_{\text{pump}}/I_{\text{sat}}}{1+I_{\text{pump}}/I_{\text{sat}}}
$$
when $I_{\text{pump}} > I_{\text{sat}}$,  $\Delta N < 0$ and inversion occurs!
###### 4 Level System
$$
\Delta N = -N \frac{I_{\text{pump}}/I_{\text{sat}}}{1+I_{\text{pump}}/I_{\text{sat}}}
$$
$\Delta N$ is always negative, so inversion is always occuring!
### Saturation Intensity
$$
I_{\text{saturation}} = \frac{\hbar\omega}{\sigma \tau} = \frac{A}{B}
$$

### Boltzmann Population Factors
$$
N_{i} \propto \exp\left( -\frac{E_{i}}{k_{B}T} \right)
$$
* $N_{i}$ is the number/population density of molecules in state $i$, i.e. the number of molecules per cubic centimeter
* $T$ is the tempurature
* $k_{B} = 1.38 \times 10^{-23}$ is Boltzmann's constant

### Maxwell-Boltzmann Distribution
$$
\frac{N_{2}}{N_{1}} = \exp\left( -\frac{E_{2}}{k_{B}T} \right) / \exp\left( -\frac{E_{1}}{k_{B}T} \right) = \exp\left[ -\frac{\Delta E}{k_{B}T}\right]
$$
* where $\Delta E = E_{2} - E_{1} = h\nu$
	* $h \nu$ is the frequency of a photon for the transition
* In the absence of light and collisions (low T), molecules tend to fall to and remain in the lowest energy state available
* Light an collision can nexcite molecules into higher-energy states. The higher T is, the more this happens
## See also
[[Stimulated Emission]]