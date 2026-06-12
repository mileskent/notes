---
date: 2026-06-09
---
*Monopulse radar* is a type of [[Radar]] that determines the angular position of a target from a single [[Pulse]] by comparing signals from multiple simultaneous [[Antenna|antenna]] beams. This allows precise angle measurement without requiring multiple pulses. The principle is analogous to how humans localize sound: by comparing the signals arriving at two ears, the left and right channels, the brain determines the direction of the source.

# Sum Channel
The *sum channel* ($\Sigma = L + R$) is the coherent sum of signals from the left ($L$) and right ($R$) halves of the [[Antenna|antenna]]. It provides maximum gain on [[Boresight|boresight]] and is used for range, [[Doppler Radar|Doppler]], and general detection processing.

# Difference Channel
The *difference channel* ($\Delta = L - R$) is the coherent difference between signals from the two halves of the [[Antenna|antenna]]. It has a null on [[Boresight|boresight]] and grows linearly with angular offset, making it sensitive to how far the target is from the beam center.

# Error Ratio
The *monopulse error ratio* is $\Delta / \Sigma$, the difference channel normalized by the sum channel. This ratio is proportional to the angular offset of the target and is independent of target return strength.

# Cross-Elevation and Elevation Error
Two difference channels are formed simultaneously, one for azimuth and one for elevation, providing 2D angular error in a single [[Pulse|pulse]].

# Calibration Rotation
Phase and amplitude imbalances between the sum and difference channels introduce a bias in the error ratio. Calibration rotation corrects for this by applying a known complex rotation to align the channels.

# Phase Coherence
The sum and difference channels must be phase-coherent, processed with the same local oscillator, for the error ratio to be valid.

# AFC
*Automatic Frequency Control* (AFC) adjusts the local oscillator to keep the [[Receiver]] locked onto the target's carrier frequency, maintaining phase coherence across [[Pulse|pulses]].
