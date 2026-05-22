---
date: 2026-05-21
---
**Sampling** is the process of converting an [[Computer Science/Computational Science/DigitalSignalProcessing/Signal#Analog Signal]] into a [[Computer Science/Computational Science/DigitalSignalProcessing/Signal#Discrete-Time Signal]] by only measuring / *sampling* its amplitude at discrete intervals of time.
* Each instance of measurement is called a *sample*
* *Sampling Period* $T_{s}$ is constant amount of time between samples, and is the reciprocal of the sampling frequency
* *Sampling Frequency* $f_{s}$ is the constant frequency of samples, and is the reciprocal of the sampling period

# Sifting Property
You can also use the delta function to "sift" out the output of a signal at a given $n_{0}$

$$
\sum_{n=-\infty}^{\infty} x[n]\ \delta[n-n_{0}] = x[n_{0}]
$$