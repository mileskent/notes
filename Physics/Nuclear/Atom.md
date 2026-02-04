---
date: 2025-02-03
---
An atom consists of a nucleus of [[Proton|protons]] and generally [[Neutron|neutrons]], surrounded by an electromagnetically bound swarm of [[Electron|electrons]].
![[Pasted image 20250401161433.png]]

### Multi-Electron Atom
When multiple electrons ($N$) are present, the wave function will be a function of each electron's position $\vec{r_{i}}$
$$
\Psi = \Psi(\vec{r_{1}}, ..., \vec{r_{N}}, t)
$$
and the potential energy will be
$$
V = V(\vec{r_{1}}, ..., \vec{r_{N}}) = 
\underbrace{  - \sum_{i = 1}^N \frac{Ze^2}{4\pi \epsilon_{0} |\vec{r_{i}}|} }_{\text{Nucleus-Electron Attraction}}
+ 
\underbrace{\sum^N_{i = 1} \sum^{i - 1}_{j = 1} \frac{e^2}{4\pi\epsilon_{0} |\vec{r_{i}}-\vec{r_{j}}|}}_{\text{Mutual Electron Repulsion}}
$$
where $Ze$ is the *nuclear charge*

$$
\vec{J} = \sum [\vec{L_{1}} , \dots, \vec{L_{N}}] + \sum [\vec{S_{1}} , \dots, \vec{S_{N}}]
$$
Because $L, L_{z}, S, S_{z}$  are quantized, so is $J, J_{z}$
$$
J = \sqrt{ j(j+ 1) }\ \hbar
\quad\quad
J_{z} = m_{j} \hbar
$$

### Electronic Configuration
* Ground State
	* Hydrogen -> $1s$
	* Helium -> $1s^2$
		* Helium has two electrons in 1s state
	* Lithium -> $1s^22s$
		* Lithium has two electrons in the 1s state, and another in the 2s state

### Electronic Shells and Subshells
See [[Quantum Number#NL Shorthand|NL Shorthand]] for meaning of lowercase letters
![[Pasted image 20250401160712.png|400]]
### Subshell Filling Order
[[Electron|Electrons]] filling according to their energy, which does not strictly follow the value of $n$.
![[Pasted image 20250401161124.png|300]]
### Closed Shells and Subshells
* Spherically symmetric (closed-shell) electron probability distributions have the most compact electron distributions and so are also the most stable and most difficult to ionize. 
* Accordingly, electrons with one more electron than a closed shell have the opposite properties, i.e. it is volatile, easy to ionize, and easy to bond with in a [[Molecule]]

### Spin-Orbit Coupling
![[Pasted image 20250401161837.png|200]]
The orbit of the electron produces a magnetic field
$$
\vec{B}_{\text{atom}} \propto \vec{L}
$$
But the electron spin also prdocuts a magnetic field proptional to the spin. The spin's potential energy in the magnetic field of the electron orbit is
$$
V_{sl} \propto \vec{S} \cdot  \vec{L}
$$
Parallel -> Repulsion
Antiparallel -> Attraction
This energy dependence on the interaction of the electrons' spins and orbital angular momenta is called *spin-orbit coupling*. 
It yields *fine structure* in the energy levels and spectrum.

### Hyperfine Structure
The nucleus can also have spin: $I$
The total angular momentum including nuclear spin is designated by $F$
### See also
[[Quantum Number]]
[[Stimulated Emission]]