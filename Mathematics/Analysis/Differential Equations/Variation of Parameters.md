---
date: 2025-10-15
---

# Nonhomogenous Linear System
$$
\vec{x}' = A(t) \vec{x} + \vec{f}(t)
$$
Solution Form
$$
\vec{x}(t) = \vec{x}_{p}(t) + \vec{x}_{c}(t)
$$
where $\vec{x}_{p}$ is a particular solution to the original (nonhomogenous system)
where $\vec{x}_{c}$ are general solutions to the homogenous system of $\vec{x}_{c}' = A(t) \vec{x}_{c}$

Suppose that the solutions of the homogenous system are 
$$
\vec{x}_{c}(t) = C_{1} \vec{x}_{1}(t) + \dots + C_{n}\vec{x}_{n}(t)
$$
The following matrix is called a *fundamental matrix*
$$
M(t) = [\vec{x}_{1}(t)\ \dots\  \vec{x}_{n}(t)]
$$
Then
$$
\vec{x}_{c}(t) = M(t) \vec{C}
$$
Let $\vec{x}(t) = M(t) \vec{u}(t)$
Then $\vec{u}' = M(t)^{-1} \vec{f}(t)$
Integrate both sides to get $\vec{u}_{p} = \int M(t)^{-1} \vec{f}(t) dt$
Then $\vec{x}_{p} = M(t) \vec{u}_{p}(t)$ is a particular solution


## Example
$$
\vec{x}' = \begin{bmatrix}
1 & 1 \\
4 & 1
\end{bmatrix} \vec{x} + \begin{bmatrix}
-1 + 21t + e^{3t} \tan(t) \\
2 + 30t + 2e^{3t} \tan(t)
\end{bmatrix}
$$
Find $\vec{x}_{c}$ first, start with eigenstuff.
$$
\vec{x}_{c}(t) = C_{1} e^{-t} \begin{bmatrix}
-1 \\
2
\end{bmatrix}
+ C_{2} e^{3t} \begin{bmatrix}
1 \\
2
\end{bmatrix}
$$
Find fundamental matrix
$$
M(t) = \begin{bmatrix}
\vec{x}_1(t) & \vec{x}_2(t)
\end{bmatrix}
=
\begin{bmatrix}
-e^{-t} & e^{3t} \\
2e^{-t} & 2e^{3t}
\end{bmatrix}
$$
Set $\vec{x}(t) = M(t) \vec{u}(t)$, which implies $\vec{u}' = M(t)^{-1} \vec{f}(t)$
Evaluate $\vec{u}'$
$$
\vec{u}'(t) = \begin{bmatrix}
-e^{-t} & e^{3t} \\
2e^{-t} & 2e^{3t}
\end{bmatrix}^{-1} 
\begin{bmatrix}
-1 + 21t + e^{3t} \tan(t) \\
2 + 30t + 2e^{3t} \tan(t)
\end{bmatrix}
$$
Recall ![[Linear Algebra#$2 times 2$ Inverse Shortcut]]
$$
\vec{u}'(t) = \frac{1}{-4e^{2t}}\begin{bmatrix}
2e^{3t} & -e^{3t} \\
-2e^{-t} & -e^{-t}
\end{bmatrix}
\begin{bmatrix}
-1 + 21t + e^{3t} \tan(t) \\
2 + 30t + 2e^{3t} \tan(t)
\end{bmatrix}
$$
$$
\vec{u}'(t) = \begin{bmatrix}
(1-3t)e^t \\
18te^{-3t} + \tan(t)
\end{bmatrix}
$$
Integrate $\vec{u}'$:
$$
\vec{u}(t) = \begin{bmatrix}
(4-3t)e^t + C_{1} \\
(-2-6t)e^{-3t} - \ln(\cos(t)) + C_{2}
\end{bmatrix}
$$
Acquire $\vec{x}_{p}(t)$
$$
\vec{x}_{p}(t) = 
\begin{bmatrix}
-e^{-t} & e^{3t} \\
2e^{-t} & 2e^{3t}
\end{bmatrix}
\begin{bmatrix}
(4-3t)e^t + C_{1} \\
(-2-6t)e^{-3t} - \ln(\cos(t)) + C_{2}
\end{bmatrix}
 = 
 \begin{bmatrix}
 -6 - 3t - e^{3t} \ln(\cos(t)) \\
4-18t-2e^{3t}\ln(\cos(t))
\end{bmatrix}
$$
Final answer
$$
\vec{x}(t) = C_{1} e^{-t} \begin{bmatrix}
-1 \\
2
\end{bmatrix}
+ C_{2} e^{3t} \begin{bmatrix}
1 \\
2
\end{bmatrix} +  \begin{bmatrix}
 -6 - 3t - e^{3t} \ln(\cos(t)) \\
4-18t-2e^{3t}\ln(\cos(t))
\end{bmatrix}
$$

