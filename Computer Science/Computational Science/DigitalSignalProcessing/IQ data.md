---
date: 2026-02-14
---
In [[Signal Processing]], an *IQ signal* refers result of decomposing a [[Carrier Wave]] into in-phase and quadrature signals. *IQ data* refers to information about how to modulate the amplitudes of the I and Q components of the signal over time.
# Motivation
When we recieve a signal, we receive a single codomain value. This is a problem because for sinusoids, there can be multiple x values per y value. This is bad because we cannot determine the phase of the incoming wave, which means that we lose the information that is holds. In the case of radar, the doppler of the target.

Solution: Measure the cosine and sine at the same time. This eliminates the ambiguity.

# IQ Sample
Though RF input, is an [[Analog Signal]], IQ data, by virtue of being discrete, is inherently a result of [[Sampling]]. Hence, each datum is a sample. 

$$
x[n] = I[n] + j \cdot Q[n]
$$

# IQ Modulation
The [[Carrier Wave]] signal $s(t)$ is WLOG a cosine, can be decomposed into an IQ signal. Use the [[Cosine Sum Identity]].

$$
\begin{align*}
s(t)
&= A(t) \cos (2 \pi f t + \phi(t))\\
&= A(t) \cos(\phi(t)) \cos(2\pi f t) - A(t) \sin(\phi (t)) \sin(2 \pi f t)\\
&= I(t) \cos(2\pi f t) - Q(t) \sin(2 \pi f t)\\
\end{align*}
$$

$$
\begin{gathered}
I(t) = A(t) \cos(\phi t)\\
Q(t) = A(t) \sin(\phi t)\\
\end{gathered}
$$

Note how the signal is now the sum of a In-Phase cosine and a Quadrature sine, where the sine and cosine have no phase shift, because all of the phase information of the original wave is encoded in the I and Q amplitudes. By modulating the amplitudes of the cosine and sine wave through the I and Q amplitudes, we can replicate the original signal.

## Complex Phasor
Based on this conclusion we can also infer that the signal is analogous to a phasor in the [[Complex Number|Complex Plane]].

$$
s(t) \cong I(t) + j Q(t)
$$

![[Phase_shifter_using_IQ_modulator.gif|400]]

# IQ Demodulatation
The previous section, [[#IQ Modulation]], explains how a carrier wave can be encoded by IQ data. This section explains how the receiver extracts the IQ data from the carrier wave. Use the [[Double Cosine Product to Sum Identity]].
$$
\begin{align*}
s(t) &= A(t) \cos (2 \pi f t + \phi(t))\\
s(t)\cos (2 \pi f t) &= A(t) \cos (2 \pi f t + \phi(t)) \cdot \cos (2 \pi f t)\\
 s(t)\cos (2 \pi f t)&= \frac{1}{2}A(t) \cos (2 \pi f t + \phi(t) - 2\pi f t) + \cos (2 \pi f t + \phi(t) + 2\pi f t)\\
 s(t)\cos (2 \pi f t)&= \underbrace{\frac{1}{2}A(t) \cos (\phi(t))}_{\text{Baseband } I(t)} + \underbrace{\cos (4 \pi f t + \phi(t))}_{\text{High Frequency Band}}\\
\end{align*}
$$
$$
\begin{align*}
s(t) &= A(t) \cos (2 \pi f t + \phi(t))\\
s(t)\sin (2 \pi f t) &= A(t) \cos (2 \pi f t + \phi(t)) \cdot \sin (2 \pi f t)\\
s(t)\sin (2 \pi f t) &= \frac{1}{2}A(t) (\sin (2 \pi f t + \phi(t) + 2\pi f t) - \sin (2 \pi f t + \phi(t) - 2\pi f t))\\
s(t)\sin (2 \pi f t) &= \underbrace{-\frac{1}{2}A(t) \sin (\phi(t))}_{\text{Baseband } Q(t)} + \underbrace{\frac{1}{2}A(t) \sin (4 \pi f t + \phi(t))}_{\text{High Frequency Band}}\\
\end{align*}
$$

$f_{\text{Baseband}} \ll f_{\text{HF Band}}$, which implies that if we apply a low pass filter on the entire carrier wave, the result will be just the Baseband wave. In the context of radar, the frequency of the baseband wave comes from the doppler shift, and the frequency of the high frequency band comes from the sum of the doppler shift and the carrier frequency. The carrier frequency is orders of magnitude larger than the doppler.

A lowpass filter is in fact the final step to unlocking the IQ data from the carrier wave.

$$
\begin{aligned}
I(t) &= 2 \cdot \text{lowpass}\left( s(t) \cdot \cos(2\pi f t) \right) \\
Q(t) &= -2 \cdot \text{lowpass}\left( s(t) \cdot \sin(2\pi f t) \right)
\end{aligned}
$$
