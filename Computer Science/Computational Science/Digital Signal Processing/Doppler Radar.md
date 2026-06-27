---
date: 2026-06-09
---
*Doppler radar* is a [[Radar]] system that exploits the [[Doppler Effect]] to measure the radial velocity of a target in addition to its range. When a target moves toward or away from the radar, the reflected signal is frequency-shifted relative to the transmitted [[Physics/Electromagnetism/Pulse|pulse]]:

$$
f_d = \frac{2v_r}{\lambda}
$$

where $f_d$ is the Doppler frequency shift, $v_r$ is the radial velocity of the target, and $\lambda$ is the wavelength of the transmitted signal. A target moving toward the radar produces a positive shift; moving away produces a negative shift.

# Pulse-Doppler Radar
A common implementation that transmits a train of pulses and computes the phase shift between successive returns from the same target. An [[Fast Fourier Transform|FFT]] across the pulse train converts phase progression into a Doppler frequency bin, allowing simultaneous range and velocity measurement.

# Applications
- Weather radar: maps precipitation velocity to detect rotation (tornadoes)
- Air traffic control: separates moving targets from stationary clutter
- Speed enforcement: measures vehicle radial velocity directly
