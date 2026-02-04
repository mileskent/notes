---
date: 2025-02-03
---
A combinations of [[Atom|atoms]]. An important question then is: why do molecules form from atoms?

Actually solving the [[Schrödinger Wave Equation]] for molecules is hard to do analytically. Therefore, we use approximation methods to analyze the quantum interactions on more of a vibe basis, i.e. they are numerical computer-based methods.
### Molecular Potential
$$
V = V(\underbrace{\vec{r}_{1}, \dots, \vec{r}_{N}}_{\text{Electron Positions}}, \underbrace{\vec{r}_{1}', \dots, \vec{r}_{N}'}_{\text{Nuclei Positions}})
$$
### Molecular Wave Function
$$
\Psi = \Psi(\underbrace{\vec{r}_{1}, \dots, \vec{r}_{N}}_{\text{Electron Positions}}, \underbrace{\vec{r}_{1}', \dots, \vec{r}_{N}'}_{\text{Nuclei Positions}})
$$
### Why Molecules Form
Spherically symmetrical atoms are totally neutral, and therefore do not form molecules. 
* This symmetry is described by having a full [[Atom#Closed Shells and Subshells|electron shell]]. 
* The noble gases are symmetrical in this way, and indeed do not form molecules. 
* Most atoms are not spherically symmetrical, see the first figure in [[Atom]]
##### Dipole Force
Even though both atoms are neutral in a sense, they experience an induced attraction, kind of like the simplest case of [[Electrostatics|induced polarity in Electrostatics]].
![[Pasted image 20250402125405.png|200]]
##### Ionic Bond
An electropositive atom gives up an electron to an electronegative one. In short, due to [[Spin]] [[Electron|electrons]] can attract each other [[Electromagnetism|magnetically]].
> [!Example] Example: $\text{NaCl}$ ionic bond
> $$
> \text{NaCl}
> \quad\quad \text{Na} \rightarrow 1s^22s^22p^63s^1
> \quad\quad \text{Cl} \rightarrow 1s^22s^22p^63s^23p^5
> $$
> Sodium gives up its 3s electron to become $\text{Na}^+$ while chlorine easily grabs the electron to become $\text{Cl}^-$
> ![[Pasted image 20250402130448.png|300]]
##### Covalent Bond
Two electronegative atoms share one or more electrons.
* Diatomic molecules formed by identilcal electronegative atoms tend to be covalent
* Larger molecules tend to have covalent bonds
> [!Example] Example: Crystaline Carbon, i.e. Diamond 
![[Pasted image 20250402131501.png|300]]

##### Van der Waals Bond
Adjacent sheets of atoms weakly bonded due to nonuniform charge distributions. 
* One layer of atoms can slide over the next layer with little friction.
* Occurs to an extent in all molecules.
> [!Example] Van der Waals Bonded Carbon, i.e. Graphite
![[Pasted image 20250402132118.png|300]]
##### Hydrogen Bond
If a hydrogen atom is covalently bonded to an electronegative atom (such as oxygen), it can simultaneously bond pseudo-covalently to another molecule. The electron's ability to bond to multiple other atoms is due to [[Probability Distribution Functions|probalistic]] [[Quantum Mechanics|quantum effects]].
* Stronger than Van der Waals
* Weaker than Covalent, Ionic
##### Metallic Bond
In metals, whose outermost electrons are very weakly bound, these valence electrons are essentially free and may be shared by many atoms.
![[Pasted image 20250402133740.png|300]]

### Vibrating Molecule
> [!Example] Vibrating $\text{CO}_{2}$ Molecule
![[NiGw3Z-984456266.gif]]
* Electrons vibrate about the nuclei -> $[10^{14}, 10^{17}]\ \text{Hz}$
* Nuclei in molecules vibrate about each other -> $[10^{11}, 10^{13}]\ \text{Hz}$
* Nuclei in molecules rotate -> $[10^{9}, 10^{10}]\ \text{Hz}$
* Different bonds have different vibrational frequencies
 ![[Pasted image 20250402140122.png|400]]

### Total Molecular Energy
$$
E = \underbrace{\left( n + \frac{1}{2} \right) \hbar \omega}_{\text{Vibrational Energy}} +\underbrace{\frac{\hbar^2l(l+1)}{2I}}_{\text{Rotational Energy}}
\quad\quad \text{with Selection Rules: } \Delta n = \pm 1, \Delta l = \pm 1
$$
Most transitions end up being forbidden by the selection rules
![[Pasted image 20250402141423.png|300]]
> [!Example]- Diatomic Molecule Rotational Energy
> For a diatomic molecule, it can be thought of as two atoms held together with a massless, rigid rod.
> $$
> K = \frac{L^2}{2I} = \frac{\hbar^2l(l+1)}{2I}
> $$
> where L is quantized
> $$
> L = \sqrt{ l(l + 1) } \ \hbar \quad \quad \text{where } l \in \mathbb{Z}^+
> $$
> and has a *selection rule* for rotational transitions:
> $$
> \Delta l = \pm 1
> $$
> So for transitions for states $l + 1$ to $l$, emitted photons will have energies of the different between those of the respective states
> $$
> E_{\text{photon}} = \frac{\hbar^2}{2I}\left((l+1)(l+2) - l(l + 1)\right) = \frac{\hbar^2}{2I}\left(l + 1\right)
> $$
> so emitted energy will be equally spaced, even though rotational kinetic energy is quadratically spaced

> [!Example]- Diatomic Vibrational Energy
Near a minimum, all curved are approximately quadratic -> Simple Harmonic Oscillator.
> * Works for not only Diatomic molecules, but also more complicated ones.
> ![[Pasted image 20250402135212.png|300]]
> $$
> E_{\text{vibration}} = \left( n + \frac{1}{2} \right) \hbar\ \omega
> $$
> where n is the *vibrational quantum number*
> * not the same as the [[Quantum Number|principle quantum number]] n
> * not the same as the [[#Molecular Potential|molecular potential]] n
> ![[Pasted image 20250402135329.png|300]]
> Molecular vibrations correspond almost perfectly to quantum mechanical simple harmonic oscillators. Energy levels are equally separated
>> [!tip] Vibrational Transition Selection Rule
>>$$
>>  \Delta n = \pm 1
>>  $$
>> * Emission -> molecule can drop one level, emitted a [[Planck's Radiation Law|quantum of energy]]
>> * Absorption -> molecule can jump one level, absorbing a [[Planck's Radiation Law|quantum of energy]]
>> * The only spectral line is $\omega$, and its *overtones*, which are integer multiples of $\omega$ and are weaker, just like musical overtones
>
>> [!tip]- Molecular Potential Energy Curve for Diatomic Molecule
>> This curve is derived from the [[Born-Oppenheimer Approximation]]
>> ![[Pasted image 20250402134756.png|250]]
>> The potential depends on the charge distributions of the atoms involved, but there is always an *equilibrium separation* between two atoms in a stable molecule.
>> The energy required to separate the two atoms completely is the *binding energy*, roughly equal to the depth of the potential well.
>> Vibrations can occur in this molecule, and if they are large enough they can break the molecule apart. Collisions with photons or other molecules can cause this.
>
>> [!tip]- Molecular Potential Approximation
>> $$
>> V \approx \frac{A}{r^n} - \frac{B}{r^m}
>> $$
>> where A, B, n, m are positive
>> ![[Pasted image 20250402135127.png|400]]


### Band Structure
![[Pasted image 20250402143050.png|400]]

### Perimeter Free-Electron Orbital Model
* For large planar molecules
* Particle in a 1D box
* $\psi_{0}(x) = \frac{1}{\sqrt{ L }}$
![[Pasted image 20250402143302.png|300]]

