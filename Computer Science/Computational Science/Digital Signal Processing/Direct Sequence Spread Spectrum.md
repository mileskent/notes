---
date: 2026-06-09
aliases:
  - DSSS
---
*Direct Sequence Spread Spectrum* (DSSS) is a [[Spread Spectrum]] technique in which a narrowband [[Computer Science/Computational Science/Digital Signal Processing/Signal|Signal]] is spread over a wide [[Bandwidth]] by multiplying it with a high-rate [[Pseudo-Noise|PN sequence]]. Each data bit is replaced by an entire PN sequence, producing a wideband signal whose bandwidth is determined by the [[Chip]] rate rather than the data rate.

At the [[Receiver]], correlating against the same PN sequence despreads the signal, recovering the original data while suppressing interference and noise that are uncorrelated with the sequence.
