---
date: 2026-05-21
---
A signal is a way of carrying information from one place to another.

The [[Domain]] of a signal is almost always time. The [[Codomain]] is usually some kind of measure of amplitude, whether it be decibels, voltage, etc. An exception to the rule of thumb are inputs involving both space and time, such as sensor data from a satellite or a waymo or something, where the domain is spatiotemporal rather than just temporal, consisting of coordinates and time, and the codomain is some kind of multidimensional representation of color, usually RGBA, rather than a single scalar.

# Levels of Discretization
## Analog Signal
![[Analog Signal]]
## Discrete-Time Signal
![[Discrete-Time Signal]]


## Digital Signal
![[Digital Signal]]

# Signal Transformations
Signals can be scaled, shifted, and flipped. They are subject to all of the typical [[Linear Transformation]]s that maintain the validity of the [[Mathematics/SetTheory/Function|Function]]. That is, not rotations, as they can break the vertical line test.

# Signal Parity
Any signal can be *uniquely* decomposed into the sum of an [[Even Function|Even Signal]] and an [[Odd Function|Odd Signal]], by the [[Even-Odd Decomposition Property]].
## Even Signal
An even signal is a signal whose underlying function is an [[Even Function]]
## Odd Signal
An odd signal is a signal whose underlying function is an [[Odd Function]]

# Special Signals
## Discrete Delta Function
The [[Kronecker Delta Function]] but it is a [[#Discrete-Time Signal]]. 
### Impulse Representation
Because the delta function is 1 at its center, and 0 everywhere else, you can composed scaled delta functions to create a given signal.

For example, the following is a DT signal that goes: 1, 2, 3.

$$
x[n] = 1 \cdot \delta[n] + 2 \cdot \delta[n-1] + 3 \cdot \delta[n-2]
$$
### Sifting Property 
![[Sampling#Sifting Property]]
## Discrete Step Function
The [[Heaviside Step Function]] but it is a [[#Discrete-Time Signal]]. 

## Moving between the Step and Delta Functions
$$
\begin{align}
\delta[n] &= u[n] - u[n-1]\\
u[n] &= \sum_{k=-\infty}^{n} \delta[k]
\end{align}
$$

# Periodicity
A signal is **periodic** if it repeats its pattern exactly over and over again at regular, predictable intervals.

A discrete signal $x[n]$ is periodic iff
$$\exists N \in \mathbb{Z}^+,\ s.t.\ x[n + N] = x[n],\ \forall n \in \mathbb{Z}$$

This is important because a function in continuous-time can be periodic, but if that period is not an integer, then it is not neccessarily periodic in discrete-time! Alternatively, if a function's period is an integer, it will be period in both continuous, and discrete-time (assuming step = 1).