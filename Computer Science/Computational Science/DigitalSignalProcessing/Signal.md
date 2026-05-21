---
date: 2026-05-21
---
A signal is a way of carrying information from one place to another.

The [[Domain]] of a signal is almost always time. The [[Codomain]] is usually some kind of measure of amplitude, whether it be decibels, voltage, etc. An exception to the rule of thumb are inputs involving both space and time, such as sensor data from a satellite or a waymo or something, where the domain is spatiotemporal rather than just temporal, consisting of coordinates and time, and the codomain is some kind of multidimensional representation of color, usually RGBA, rather than a single scalar.

# Levels of Discretization
## Analog Signal
An **analog signal** is a [[Continuity|Continuous]] wave. It is typically denoted as $x(t)$, where $x$ is the function of the wave and $t$ is time.

![[Pasted image 20260521160253.png|300]]

An example of an analog signal is sound; imagine a guitar string vibrating at an 440 Hz A. Not only is the string a continuous wave, but the compression waves it imparts onto the air, the sound, are also continuous waves.

## Discrete-Time Signal
A **discrete-time signal** is the result of [[Sampling]] a subset of the domain of an [[#Analog Signal]], creating a new signal where the [[Domain]] is discrete, while the [[Codomain]] remains [[Continuity|Continuous]]. It is typically denoted as $x[n]$, where $x$ is the function of the signal, and $n$ is the index.

![[Pasted image 20260521160335.png|300]]

An example of a discrete-time signal is within the process of digitally recording a guitar. While a microphone can hear any pitch, it can not convey every instant of a sound to a computer. Therefore, a broker responsible for converting the analog signal of the microphone into something the computer can understand is required. A [[Analog-to-Digital Converter]] decides on a certain sampling rate at which to note what the microphone hears at that moment so that it can eventually send a finite amount of information to the computer. At a certain stage within the converter, the signal is represented with discrete time, but the codomain is still continuous.

## Digital Signal
A **digital signal** is the result of [[Quantization|Quantizing]] the values of the codomain of a [[#Discrete-Time Signal]], creating a new signal where both the [[Domain]] and [[Codomain]] are discrete. It is typically can be denoted as $x[n]$, where $x$ is the function of the signal, and $n$ is the index. It can also be denoted as $\hat{x}[n]$ or $x_{q}[n]$ to distinguish it from its discrete-time counterpart, and to show that it has been quantized.

![[Pasted image 20260521160426.png|300]]

An example of a digital signal would be the final steps of the [[Analog-to-Digital Converter]] before it sends the final digital signal to the computer; it has to represent that signal in binary. Any means of representing all continuous values with finite digits of precision will lead to loss, so regardless of if you choose [[IEEE 754 Double]]s, or some kind of integer, you will be performing some level [[Quantization]] to the signal. The result is a signal with both discrete time and amplitude.

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
You can also use the delta function to "sift" out the output of a signal at a given $n_{0}$

$$
\sum_{n=-\infty}^{\infty} x[n]\ \delta[n-n_{0}] = x[n_{0}]
$$
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
$$\exists N, n \in \mathbb{Z},\ s.t.\ x[n + N] = x[n]$$

This is important because a function in continuous-time can be periodic, but if that period is not an integer, then it is not neccessarily periodic in discrete-time! Alternatively, if a function's period is an integer, it will be period in both continuous, and discrete-time (assuming step = 1).