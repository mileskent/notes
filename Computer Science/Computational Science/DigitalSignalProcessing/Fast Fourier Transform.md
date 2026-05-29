---
date: 2026-05-25
aliases:
  - FFT
---
The *Fast Fourier Transform* (FFT) is the de facto [[Computer Science/Data Structures/Algorithm|Algorithm]] for calculating the [[Discrete Fourier Transform]], that reduces the [[Time Complexity]] of the computation to $O(n \log n)$, whereas a regular matrix multiplication is $O(n^2)$. There are many different implementations of the FFT.

# Time Complexity
The [[Time Complexity]] of the FFT algorithm is $O(n  \log n)$, whereas the naive DFT algorithm is $O(n^2)$. 

> [!Tip]- Conceptual TLDR
> $O(n \log n)$  is a consequence of it being a Divide and Conquer algorithm, similar to the approach of [[Merge Sort]]; hence why the time complexity is the same order. 
>
> For example, if we compute a [[Discrete Fourier Transform|DFT]] with $N=1024$, we can reexpress the product of the DFT matrix and the input vector as the following
> $$
> X = W_{1024}\ \vec{x} = 
> \begin{bmatrix} 
> I_{512} & -D_{512}\\
> I_{512} & -D_{512}
> \end{bmatrix}
> \begin{bmatrix} 
> W_{512} & 0\\
> 0 & W_{512}
> \end{bmatrix}
> \begin{bmatrix} 
> \vec{x}_{\text{even}} \\
> \vec{x}_{\text{odd}}\\
> \end{bmatrix}
> $$
> * where $I$ is an [[Identity Matrix]]
> * where $D$ is the [[Diagonalization#Diagonal Matrix]] version of $W$
> * where $\vec{x}_{\text{even}}$ is the even indices of $\vec{x}$
> * where $\vec{x}_{\text{odd}}$ is the odd indices of $\vec{x}$
> 
> The principle of being able to do this rearrangement is because the DFT matrix has a lot of symmetry, which can then be exploited post-rearrangement, on account of the diagonal, and sparse forms.
> 
> The left block matrix has $O(N)$ [[Time Complexity]], and the right block matrix maintains the $O(N^2)$ but it is really $N^2 /\ 2$. For each half sized $W$ we can recursively apply this decomposition until the final base case right block is $O(1)$. This is the *Divide and Conquer* aspect of the algorithm. It takes $O(\log N)$ recurses to reach the base case. For each iteration, we have to compute the $O(N)$ left block times the $O(1)$ right block. Therefore, the time complexity is $O(N \log N)$.
> 
> For this specific example, $N=2^n$ is required. If you had a non power of 2, you could consider padding the input matrix, to force $N=2^n$. 

# Cooley-Tukey FFT
## Radix-2 FFT
Radix-2 FFT is a FFT implementation that requires $N$ is a power of $2$
### Radix-2 Decimation in Time FFT
For DIT, you split by the index (n) by parity. Hence "decimation in time".

$$
\begin{aligned}
X[k] &= \sum_{n=0}^{N-1} x[n]\cdot \omega_{N}^{nk}\\
X[k] &= 
\sum_{m=0}^{N/2-1} x[2m]\cdot \omega_{N}^{(2m)k} +
\sum_{m=0}^{N/2-1} x[2m+1]\cdot \omega_{N}^{(2m+1)k}\\
X[k] &= 
\underbrace{\sum_{m=0}^{N/2-1} x[2m]\cdot \omega_{N}^{(2m)k}}_{\text{even index DFT}} +
\omega_{N}^k \underbrace{\sum_{m=0}^{N/2-1} x[2m+1]\cdot \omega_{N}^{(2m)k}}_{\text{odd index DFT}}\\
X[k] &= X_{E}[k] + \omega^k_{N} \cdot X_{O}[k]
\end{aligned}
$$

You can apply the same even-odd splitting process to $X_{E}$ and $X_{O}$ recursively, until you hit a base case of a non loop sum.
### Radix-2 Decimation in Frequency FFT
For DIF, you split the frequencies (k) by parity. Hence "decimation in frequency".

# Good-Thomas FFT
Also known as the *Prime-Factor Algorithm* FFT, you break $N$ into factors that are strictly coprime, meaning that their GCD = 1. This one isn't as relevant to computation though, so we just mention it. Radix 2, is the main one for computation because computers love 2. 