---
date: 2026-05-27
aliases:
  - DFT
---
$$
X[k] = \sum_{n=0}^{N-1} x[n]\cdot \omega_{N}^{nk}\\
$$
* where $\omega_{N} = \exp\left( -\frac{2i\pi}{N} \right)$, called the "Twiddle Factor"
* where $N$ is the number of [[Sampling#Sample|samples]] in the [[Discrete-Time Signal|DT signal]] $x$
* where $k$ is the $k^\text{th}$ frequency bin, representing an area of frequencies in the frequency domain centered around $\frac{kf_{s}}{N}$, where $f_{s}$ is the [[Sampling#Sampling Frequency]]
* where $X$ is a [[Complex Number]]

# Matrix Discrete Fourier Transform
$$
\begin{bmatrix}
X[0] \\
X[1] \\
X[2] \\
\vdots \\
X[N-1]
\end{bmatrix}
=
\begin{bmatrix}
1 & 1 & 1 & \cdots & 1 \\
1 & \omega_N & \omega_N^2 & \cdots & \omega_N^{N-1} \\
1 & \omega_N^2 & \omega_N^4 & \cdots & \omega_N^{2(N-1)} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & \omega_N^{N-1} & \omega_N^{2(N-1)} & \cdots & \omega_N^{(N-1)^2}
\end{bmatrix}
\begin{bmatrix}
x[0] \\
x[1] \\
x[2] \\
\vdots \\
x[N-1]
\end{bmatrix}
$$

$$
\begin{align}
\text{Let } W &\in \mathbb{C}^{N \times N}\ s.t.\ W_{i,j} = \omega_{N}^{ij}\\
\mathbf{X} &= W \mathbf{x}
\end{align}
$$
* where $W$ is called the "DFT Matrix"
# Inverse Discrete Fourier Transform
$$
x[n] = \frac{1}{N}\sum_{k=0}^{N-1} X[k] \cdot \omega_{N}^{-nk}
$$
