---
date: 2026-06-10
aliases:
  - DDC
---
A *Digital Down Converter* (DDC) shifts a [[Discrete-Time Signal]] centered at some carrier frequency down to [[Baseband]], producing a complex [[IQ data|IQ]] output at a reduced [[Sampling#Sampling Frequency]]. It consists of three stages:
1. **Mixer**: multiplies the input by a complex sinusoid $e^{-j2\pi f_c n}$ from a Numerically Controlled Oscillator, shifting the center frequency to zero.
2. **Low-pass filter**: removes out-of-band content and images.
3. **Decimator**: reduces the sample rate to match the signal [[Computer Science/Computational Science/Digital Signal Processing/Bandwidth|Bandwidth]].
