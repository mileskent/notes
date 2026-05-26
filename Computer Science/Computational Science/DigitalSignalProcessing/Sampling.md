---
date: 2026-05-21
---
Sampling is the process of converting an [[Computer Science/Computational Science/DigitalSignalProcessing/Signal#Analog Signal]] into a [[Computer Science/Computational Science/DigitalSignalProcessing/Signal#Discrete-Time Signal]] by only measuring / *sampling* its amplitude at discrete intervals of time.
* Each instance of measurement is called a *sample*
* *Sampling Period* $T_{s}$ is constant amount of time between samples, and is the reciprocal of the sampling frequency
* *Sampling Frequency* $f_{s}$ is the constant frequency of samples, and is the reciprocal of the sampling period

# Sifting Property
You can also use the delta function to "sift" out the output of a signal at a given $n_{0}$ 

$$
x[n_{0}] = \sum_{n=-\infty}^{\infty} x[n]\ \delta[n-n_{0}]
$$

This can be used for either constructing or deconstructing a signal.

# Resampling
Resampling is the process of taking an existing [[Computer Science/Computational Science/DigitalSignalProcessing/Signal#Discrete-Time Signal]] and modifying it such that it has a different sampling frequency.

## Downsampling
Resampling where you throw away data in order to achieve the desired slower sampling frequency.

For example: halfing the frequency; you trash every other data point.

## Upsampling
Resampling is where you insert synthetic data between the data points of the original signal to emulate what a higher frequency signal would have been sampled as. 

For example, you can use some kind of interpolation algorithm to fill in the gaps. Typically you insert zeros between the original data points, and then apply a low-pass filter over the "zero-stuffed" signal which acts as the interpolation algorithm, smoothing out the overall signal, including those zeroes.
