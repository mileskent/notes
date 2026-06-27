---
date: 2026-05-25
aliases:
  - Window
---
Windowing is when you multiply a [[#Window Function]] by a [[Computer Science/Computational Science/Digital Signal Processing/Signal|Signal]] to extract a finite "window" of it.

# Window Function
A window function is the function you multiply by the function of the signal to yield a "window" of the signal.
## Rectangle Window
When you use [[rect]] as the window function, you get an exact subsection of the original signal. However, you also get [[Spectral Leakage]] due to the abrupt cutoff of the function. The other window functions solve this by tapering the product to zero by the edges.

## Hann Window
Hann window uses a raised cosine shape that tapers smoothly to exactly zero at the edges to reduce [[Spectral Leakage]].

$$
w[n] = 0.5\left( 1-\cos\left( \frac{2\pi n}{N - 1} \right) \right)
$$

## Hamming Window
The Hamming window is a slight modification of the [[#Hann Window]] optimized to minimize the height of the maximum side-lobe. Instead of tapering all the way to zero, it tapers to a small non-zero value.

$$
w[n] = 0.54 - 0.46 \cos\left(\frac{2\pi n}{N-1}\right)
$$

## Blackman Window
The Blackman Window is the smoother version of the [[#Hann Window]], achieving this smoother taper through an additional cosine term.
$$
w[n] = 0.42 - 0.5 \cos\left(\frac{2\pi n}{N-1}\right) + 0.08 \cos\left(\frac{4\pi n}{N-1}\right)
$$
