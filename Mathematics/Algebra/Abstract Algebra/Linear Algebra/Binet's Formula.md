---
date: 2026-01-11
---
$$
F_{z} =\frac{\phi^z-\psi^z}{\sqrt{ 5 }}
$$
The [[Analytic Continuation]] of the [[Fibonacci Sequence]].

# Derivation
$$
\text{Let }
A = \begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}
$$
$$
\begin{bmatrix}
F_{z+1}\\
F_{z}
\end{bmatrix} = A^z \begin{bmatrix}
F_{1} \\
F_{0}
\end{bmatrix}
$$
See [[Diagonalization]]
$$
\begin{align}
A &= PDP^{-1} \\
\\
P &= \begin{bmatrix}
\psi & \phi\\
1 & 1
\end{bmatrix}\\
D &= \begin{bmatrix}
\psi & 0 \\
0 & \phi\\
\end{bmatrix}\\
P^{-1} &= \frac{1}{\sqrt{ 5 }}\begin{bmatrix}
-1 & \phi\\
1 & \psi
\end{bmatrix} \\
\text{where } \phi &= \frac{1 + \sqrt{ 5 }}{2}\\
\text{where } \psi &= \frac{1 - \sqrt{ 5 }}{2}
\end{align}
$$
$$
\begin{align}
A^z &= PD^z P^{-1} \\
&=
\frac{1}{\sqrt{ 5 }}
\begin{bmatrix}
\psi & \phi\\
1 & 1
\end{bmatrix}
\begin{bmatrix}
\psi & 0 \\
0 & \phi\\
\end{bmatrix}
\begin{bmatrix}
-1 & \phi\\
1 & \psi
\end{bmatrix} \\
&=
\frac{1}{\sqrt{ 5 }}
\begin{bmatrix}
\phi^{z+1} - \psi^{z+1} & \psi^{z} - \phi^{z} \\
\phi^{z} - \psi^{z} & 1 \\
\end{bmatrix} \\
\end{align}
$$
$$
\begin{align}
\begin{bmatrix}
F_{z+1}\\
F_{z}
\end{bmatrix} &= 
\frac{1}{\sqrt{ 5 }}
\begin{bmatrix}
\phi^{z+1} - \psi^{z+1} & \psi^{z} - \phi^{z} \\
\phi^{z} - \psi^{z} & 1 \\
\end{bmatrix}
\begin{bmatrix}
F_{1} \\
F_{0}
\end{bmatrix} \\
&=
\frac{1}{\sqrt{ 5 }}
\begin{bmatrix}
\phi^{z+1} - \psi^{z+1}\\
\phi^{z} - \psi^{z}\\
\end{bmatrix}
\end{align}
$$
$$
\begin{gathered}
\therefore \quad F_{z} = \frac{\phi^z - \psi^z}{\sqrt{ 5 }}\\
\text{QED}
\end{gathered}
$$
