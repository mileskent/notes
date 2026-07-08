---
date: 2026-05-25
aliases:
  - FFT
---
The *Fast Fourier Transform* (FFT) is the de facto [[Algorithm|Algorithm]] for calculating the [[Discrete Fourier Transform]], that reduces the [[Time Complexity]] of the computation to $O(n \log n)$, whereas a regular matrix multiplication is $O(n^2)$. There are many different implementations of the FFT.

# Time Complexity
The [[Time Complexity]] of the FFT algorithm is $O(n  \log n)$, whereas the naive DFT algorithm is $O(n^2)$. 

The TLDR on the intuition for the time complexity is that we can split up the original DFT into subproblems until we have $O(\log n)$ subproblems that each take $O(n)$ to compute. Hence the time complexity is $O(n \log n)$.
* $N^2 \leftarrow$ in the original expression, we iterate $N$ to sum, $N$ times
* $2 \cdot \left( \frac{N}{2} \right)^2 = \frac{N^2}{2} \leftarrow$ we iterate $N/2$ to sum, $N/2$ times, and we do that twice
* $4 \cdot \left( \frac{N}{4} \right)^2 = \frac{N^2}{4} \leftarrow$ the second level of recursion
* $N \cdot \left( \frac{N}{N} \right)^2 = \frac{N^2}{N} = N \leftarrow$ the last level of recursion

# Cooley-Tukey FFT
## Radix-2 FFT
Radix-2 FFT is a FFT implementation that requires $N$ is a power of $2$
### Radix-2 Decimation in Time FFT
For DIT, you split by the index (n) by parity. Hence "decimation in time".

Start with the initial DFT equation

$$
X[k] = \sum_{n=0}^{N-1} x[n]\cdot \omega_{N}^{nk}\\
$$

Split the odd and even indices into two different sums

$$
X[k] = 
\sum_{m=0}^{N/2-1} x[2m]\cdot \omega_{N}^{(2m)k} +
\sum_{m=0}^{N/2-1} x[2m+1]\cdot \omega_{N}^{(2m+1)k}\\
$$

Factor out a $\omega^k_{N}$ from the odd sum

$$
X[k] = 
\sum_{m=0}^{N/2-1} x[2m]\cdot \omega_{N}^{(2m)k} +
\omega_{N}^k \sum_{m=0}^{N/2-1} x[2m+1]\cdot \omega_{N}^{(2m)k}\\
$$

Rewrite the the subproblem DFTs as the odd indices subproblem and the even indices subproblem. Each of these subproblem DFTs are only half the length as the original problem, so while $k$ was originally valid beyond $\frac{N}{2}$ for $X[k]$, it must now be within the half range to accomodate $X_{O}[k]$ and $X_{E}[k]$.

$$
X[k] = X_{E}[k] + \omega^k_{N} \cdot X_{O}[k]\quad \text{for }0\leq k < \frac{N}{2}
$$

In order to calculate the full DFT, we have to get the values of $X[k]$ for $\frac{N}{2}\leq k<N$, which we can do this by shifting the result we just got.

$$
X\left[ k + \frac{N}{2} \right] = X_{E}\left[ k + \frac{N}{2} \right] + \omega^{k+N/2}_{N} \cdot X_{O}\left[ k+\frac{N}{2} \right]
$$

Simplify subproblem DFTs using periodicity rules: period of $\frac{N}{2}$ sample DFT is $\frac{N}{2}$

$$
X\left[ k + \frac{N}{2} \right] = X_{E}\left[ k\right] + \omega^{k+N/2}_{N} \cdot X_{O}\left[ k\right]
$$

Using $\omega_{N}^{k+N/2} = \omega^k_{N} \cdot \omega_{N}^{N/2} = -\omega^k_{N}$ , where $\omega_{N}^{N/2} = e^{-i \frac{2\pi}{N} \cdot N/2} =  e^{-\pi i} =-1$

$$
X\left[ k + \frac{N}{2} \right] = X_{E}[k] - \omega^k_{N} \cdot X_{O}[k]\quad \text{for } 0\leq k < \frac{N}{2}
$$

Therefore now we have the capability of calculating $X[k]$ for all relevant $k$ using the combination of these two, where the upper range $k$ use the bottom and the lower range use the top. The resulting process is called the *Butterfly Operation*, allowing us to convert an $N$-point DFT problem into two $N/2$-point DFT problems. 

$$
\begin{align}
X[k] &= X_{E}[k] + \omega^k_{N} \cdot X_{O}[k]\\\
X \left[ k + \frac{N}{2} \right] &= X_{E}[k] - \omega^k_{N} \cdot X_{O}[k]\\
& \text{for }0\leq k < \frac{N}{2}\\
\end{align}
$$
* $N^2 \leftarrow$ in the original expression, we iterate $N$ to sum, $N$ times
* $2 \cdot \left( \frac{N}{2} \right)^2 = \frac{N^2}{2} \leftarrow$ we iterate $N/2$ to sum, $N/2$ times, and we do that twice
* $4 \cdot \left( \frac{N}{4} \right)^2 = \frac{N^2}{4} \leftarrow$ the second level of recursion
* $N \cdot \left( \frac{N}{N} \right)^2 = \frac{N^2}{N} = N \leftarrow$ the last level of recursion

We have already shown the first level of recursion. If we keep on recursing until each subvector is of length 1, then it only cost $N$ to calculate that DFT subproblem. It takes $\log n$ recurses to get to the base case.
### Radix-2 Decimation in Frequency FFT
For DIF, you split the frequencies (k) by parity. Hence "decimation in frequency".

# Good-Thomas FFT
Also known as the *Prime-Factor Algorithm* FFT, you break $N$ into factors that are strictly coprime, meaning that their GCD = 1. This one isn't as relevant to computation though, so we just mention it. Radix 2, is the main one for computation because computers love 2. 

$$
\begin{gathered}
\end{gathered}
$$