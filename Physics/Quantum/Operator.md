---
date: 2025-02-03
---
Functions that take [[Wave]] functions as inputs. 
An operator is generally indicated with a hat.
* Using operators: $E = K + V$ you can derive the [[Schrödinger Wave Equation]], as it is equivalent

### Measured Values
In any measurement of the observable for an operator $\hat{A}$, the only values that can ever be observed are the *eigenvalues*
*Eigenvalues* satisfy
$$
\hat{A} \Psi = a \Psi
$$
where $a$ is a constant and the value that's measured.
### Operators
##### Hamiltonian
For example the [[Schrödinger Wave Equation|Time Independent Schrödinger Wave Equation]] using operators:
$$
\hat{H} \psi = E \psi
\quad\quad
\text{where }
\hat{H} = - \frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V = \hat{K} + V
$$
$\hat{H}$ is called the *Hamiltonian*, which is an **operator** yielding the total energy (kinetic + potential)
Also $\langle E \rangle = \langle \psi\ |\ \hat{H}\ |\ \psi \rangle$


##### The kinetic-energy operator
$$
\hat{K} = - \frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2}
$$

##### The potential-energy operator
just multiplication by $V(x)$

##### The position operator
just multiplication by $x$

##### The momentum operator
$$
\hat{p} = i \hbar \frac{\partial}{\partial x}
$$
The expectation value of the momentum
$$
\langle p \rangle = \langle \Psi|\hat{p}|\Psi\rangle = -i \hbar \int^{\infty}_{-\infty} \frac{\partial\Psi(x, t)}{\partial x}\ dx
$$

##### Angular Momentum Operator
$$
\hat{L}_{z} = \hat{x}\ \hat{p}_{y} - \hat{y}\ \hat{p}_{x}
$$
Possible values of $\hat{L}$ are functions of $l$ such that $L = \sqrt{l(l+1)  }\ \hbar$
Disagrees with [[Bohr Model]] angular momentum. Implies [[Electron]] motion is more like a vibration than it is a planetary orbit.
Also note that $L_{z} = m_{l} \hbar$, and the $x$ and $y$ components are not observable, as they are not calculable, even though they exist. See [[Schrödinger Wave Equation for Hydrogen Atom#Quantum Numbers|Quantum Numbers]]. Except for $l = 0$, when $L = 0$ so the x and y components are 0.

##### Total energy operator
$$
\hat{E} = i \hbar \frac{\partial}{\partial x}
$$
The expectation value of the energy
$$
\langle E \rangle = \langle \psi|\hat{E}|\psi\rangle = i \hbar \int \Psi^* \frac{\partial\Psi}{\partial x}\ dx
$$