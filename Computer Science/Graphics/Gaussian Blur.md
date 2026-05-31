---
date: 2026-05-31
---
A gaussian blur is a blur where the value of every pixel is the weighted average of all pixels within one of the particular pixel, where the weight is greater, the closer you are to the center.

$$
B= \sum \left(G \odot P\right) = \text{Tr}( G^T P )
$$
* where $P$ is the *patch* around the current pixel
* where $G$ is the *Gaussian Kernel Matrix*
* The first expression is us the sum of the [[Hadamard Product|Elementwise Product]] approach. The second expression is the equivalent [[Linear Algebra]] approach.

# Gaussian Kernel Matrix
$$
\begin{align}
G_{i,j} &= \frac{1}{V \tau} \cdot \exp\left( -\frac{i^2+j^2}{2V}\right)\\
G_3 &= \frac{1}{16} \begin{bmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \\ 1 & 2 & 1 \end{bmatrix}
\end{align}
$$