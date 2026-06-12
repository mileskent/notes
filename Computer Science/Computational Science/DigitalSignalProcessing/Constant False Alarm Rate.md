---
date: 2026-06-09
aliases:
  - CFAR
  - CFAR Detection
---
*Constant False Alarm Rate* (CFAR) is a target detection scheme that adaptively sets a threshold to maintain a constant probability of false alarm regardless of the local noise level. For each cell, the threshold is proportional to the average of a ring neighborhood around that cell, where the deadzone immediately around the given cell contains "guard cells".

$$
\hat{P}_{noise}[k] = \text{avg}(\mathcal{R}(k)), \qquad \text{threshold}[k] = \alpha \cdot \hat{P}_{noise}[k]
$$

* where $\mathcal{R}(k)$ is the ring of reference cells surrounding bin $k$, excluding the guard cells immediately adjacent to the $k$th cell.
* $\alpha$ is chosen to achieve the desired false alarm rate.
* CFAR assumes the noise floor is locally flat, so it performs poorly in spectrally shaped or wideband environments where reference cells may contain signal energy. The [[Automatic Noise Floor Spectrum Estimation in the Presence of Signals]] was developed to address this limitation.
