---
date: 2026-06-17
aliases:
  - Poles
---
The concept of a *Pole* of a [[Complex Number|Complex]] Function comes from [[Complex Analysis]]: [[Mathematics/Analysis/Complex Analysis/Pole|Pole]]. 

In [[Digital Signal Processing]], when we say *Pole*, we are typically referrring to a complex analysis pole of the [[Transfer Function]] $H(z)$, i.e. a root $p_0 \in \mathbb{C}$ where the denominator of $H(z)$ is zero. 

Each pole corresponds to a [[Fundamental Mode|fundamental mode]] of the [[Impulse Response]], with its location in the complex plane determining that mode's growth, decay, and oscillation. Concepts from [[Differential Equation|Differential Equations]] involving complex exponential solutions may be relevant here. Note also that poles only exist for [[Feedback]] loops. So essentially, the poles of a system correspond to the gains of the equivalent parallel feedback loops that comprise it; see [[#Equivalence to Parallel First-Order System]].

Poles literally *are* [[Eigenstuff#Eigenvalue|Eigenvalues]]. Poles are the $z$ for which the [[Transfer Function]] experiences a singularity. Eigenvalues are the $z$ for which their [[Matrix]] becomes [[Singular Matrix|Singular]] in $(zI - A)$. Poles are when $H$ blows up. Eigenvalues are when $(zI - A)$ blows up. They come from different mathematical angles, but are precisely the same concept.
# Example Systems

## Canonical Single-Pole System

The pole is at $z = p_0$, directly visible as the feedback gain. The denominator of the Transfer Function $1 - p_0\mathcal{R}$ has a single root at $p_0$.

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$x[n]$};
    \node [draw, circle, right=1cm of in] (sum) {$+$};
    \node [right=2.5cm of sum] (out) {$y[n]$};
    \coordinate [right=2cm of sum] (branch);
    \node [draw, rectangle, below=1.5cm of branch] (delay) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=1cm of delay] (gain) {$p_0$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (out);
    \draw [->] (branch) -- (delay);
    \draw [->] (delay) -- (gain.east);
    \draw [->] (gain.west) -| (sum);
\end{tikzpicture}
\end{document}
```

### Transfer Function
$$
(1 - p_0\mathcal{R})Y = X \implies H = \frac{Y}{X} = \frac{1}{1 - p_0\mathcal{R}}
$$

### Impulse Response
$$
y[n] = \begin{cases} p_0^n & n \geq 0 \\ 0 & \text{otherwise} \end{cases}
$$
The [[Impulse Response]] for this system is geometric, where the pole is just the gain $p_{0}$. 
#### Stability of the Impulse Response
The [[Stability]] of the system when disturbed by $\delta[n]$ is determined by the gain $p_{0}$
* $|p_0| < 1$: converges to zero
* $|p_0| = 1$: constant magnitude
* $|p_0| > 1$: diverges
#### Monotonicity of the Impulse Response
The [[Monotonic Function|Monotonicity]] of the system when disturbed by $\delta[n]$ is determined by the sign of $p_0$
* $p_0 \geq 0$: monotonic
* $p_0 < 0$: alternating sign each sample

## Second Order System
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$X$};
    \node [draw, circle, right=1cm of in] (sum) {$+$};
    \node [right=4cm of sum] (out) {$Y$};
    \coordinate [right=3.5cm of sum] (branch);
    \node [draw, rectangle, below=1.5cm of branch] (delay1) {$\mathcal{R}$};
    \node [draw, rectangle, below=1.5cm of delay1] (delay2) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=1cm of delay1] (gain1) {$1.6$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=1cm of delay2] (gain2) {$-0.63$};

    \draw [->] (in) -- (sum);
    \draw [->] (sum) -- (out);
    \draw [->] (branch) -- (delay1);
    \draw [->] (delay1) -- (gain1.east);
    \draw [->] (gain1.west) -| (sum);
    \draw [->] (delay1) -- (delay2);
    \draw [->] (delay2) -- (gain2.east);
    \draw [->] (gain2.west) -| (sum);
\end{tikzpicture}
\end{document}
```

$$
\begin{align}
Y &= X + 1.6\mathcal{R}Y - 0.63\mathcal{R}^2Y \\
Y - 1.6\mathcal{R}Y + 0.63\mathcal{R}^2Y &= X \\
(1 - 1.6\mathcal{R} + 0.63\mathcal{R}^2)Y &= X \\
H = \frac{Y}{X} &= \frac{1}{1 - 1.6\mathcal{R} + 0.63\mathcal{R}^2}
\end{align}
$$
The poles are the roots of $1 - 1.6\mathcal{R} + 0.63\mathcal{R}^2$, which are $p_0 = 0.7$ and $p_1 = 0.9$. Both are real, positive, and inside the unit circle, so the system is stable with monotonic decay.

Notice how the [[Transfer Function]] contains the reciprocal of a second order polynomial. Because it is a reciprocal, that tells us that it is a [[Feedback]] system. Because it is a second order polynomial, that tells us that the system is second order.
### Equivalence to Cascaded First-Order Systems
We can algebraically manipulate and factor the second-order system's operator form into a [[Cascaded System]].
$$
\begin{align}
(1 - 1.6\mathcal{R} + 0.63\mathcal{R}^2)Y &= X \\
(1-0.7\mathcal{R})(1-0.9\mathcal{R})Y &= X \\
H = \frac{Y}{X} &= \frac{1}{(1-0.7\mathcal{R})(1-0.9\mathcal{R})}
\end{align}
$$

The first equivalent first order system:


$$
(1-0.7\mathcal{R})Y_2 = X, \quad (1-0.9\mathcal{R})Y = Y_2
$$

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$X$};
    \node [draw, circle, right=0.5cm of in] (sum1) {$+$};
    \coordinate [right=1.5cm of sum1] (branch1);
    \node [right=2cm of sum1] (w) {$Y_2$};
    \node [draw, circle, right=0.5cm of w] (sum2) {$+$};
    \coordinate [right=1.5cm of sum2] (branch2);
    \node [right=2cm of sum2] (out) {$Y$};
    \node [draw, rectangle, below=1.2cm of branch1] (delay1) {$\mathcal{R}$};
    \node [draw, rectangle, below=1.2cm of branch2] (delay2) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.5cm of delay1] (gain1) {$0.7$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.5cm of delay2] (gain2) {$0.9$};

    \draw [->] (in) -- (sum1);
    \draw [->] (sum1) -- (w);
    \draw [->] (w) -- (sum2);
    \draw [->] (sum2) -- (out);
    \draw [->] (branch1) -- (delay1);
    \draw [->] (delay1) -- (gain1.east);
    \draw [->] (gain1.west) -| (sum1);
    \draw [->] (branch2) -- (delay2);
    \draw [->] (delay2) -- (gain2.east);
    \draw [->] (gain2.west) -| (sum2);
\end{tikzpicture}
\end{document}
```


The second equivalent first order system. This is because of the commutative property.

$$
(1-0.9\mathcal{R})Y_1 = X, \quad (1-0.7\mathcal{R})Y = Y_1
$$

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]
    \node (in) {$X$};
    \node [draw, circle, right=0.5cm of in] (sum1) {$+$};
    \coordinate [right=1.5cm of sum1] (branch1);
    \node [right=2cm of sum1] (w) {$Y_1$};
    \node [draw, circle, right=0.5cm of w] (sum2) {$+$};
    \coordinate [right=1.5cm of sum2] (branch2);
    \node [right=2cm of sum2] (out) {$Y$};
    \node [draw, rectangle, below=1.2cm of branch1] (delay1) {$\mathcal{R}$};
    \node [draw, rectangle, below=1.2cm of branch2] (delay2) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.5cm of delay1] (gain1) {$0.9$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.5cm of delay2] (gain2) {$0.7$};

    \draw [->] (in) -- (sum1);
    \draw [->] (sum1) -- (w);
    \draw [->] (w) -- (sum2);
    \draw [->] (sum2) -- (out);
    \draw [->] (branch1) -- (delay1);
    \draw [->] (delay1) -- (gain1.east);
    \draw [->] (gain1.west) -| (sum1);
    \draw [->] (branch2) -- (delay2);
    \draw [->] (delay2) -- (gain2.east);
    \draw [->] (gain2.west) -| (sum2);
\end{tikzpicture}
\end{document}
```


The factored form $(1-0.7\mathcal{R})(1-0.9\mathcal{R})$ makes the poles explicit. Each factor contributes one pole, and each subsystem's feedback gain is its pole.

Based on the [[Transfer Function]], we can tell that the system is either combination of cascading these feedback, first order systems.
### Equivalence to Feed-Forward Infinite-Order System

No denominator polynomial, so formally no poles. The poles are encoded in the convergence of the geometric series: the base of each series ($0.7$, $0.9$) is the pole, and the series only converges when the pole is inside the unit circle.

$$
\begin{align}
H &= \frac{1}{(1-0.7\mathcal{R})(1-0.9\mathcal{R})} \\
&= \frac{1}{1-0.7\mathcal{R}} \cdot \frac{1}{1-0.9\mathcal{R}} \\
&= \left(\sum_{n=0}^{\infty} 0.7^n \mathcal{R}^n\right) \cdot \left(\sum_{n=0}^{\infty} 0.9^n \mathcal{R}^n\right) \\
&= (1 + 0.7\mathcal{R} + 0.7^2\mathcal{R}^2 + \cdots) \cdot (1 + 0.9\mathcal{R} + 0.9^2\mathcal{R}^2 + \cdots)\\
&= (1 + 0.9\mathcal{R} + 0.9^2\mathcal{R}^2 + \cdots) \cdot (1 + 0.7\mathcal{R} + 0.7^2\mathcal{R}^2 + \cdots) 
\end{align}
$$
For the [[Transfer Function]] $H = (1 + 0.9\mathcal{R} + 0.9^2\mathcal{R}^2 + \cdots) \cdot (1 + 0.7\mathcal{R} + 0.7^2\mathcal{R}^2 + \cdots)$, we can tell that the signal first goes through an infinite-feed forward system with gains of the exponentials of 0.7, before going through the same thing but with 0.9. 
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.6, transform shape]

    \def\rowsep{0.6cm}

    % Input
    \node (in) {$X$};
    \coordinate [right=0.3cm of in] (branch);

    % Center row: 0.7², R²
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.6cm of branch] (g2) {$0.7^2$};
    \node [draw, rectangle, right=0.5cm of g2.east] (r2) {$\mathcal{R}^2$};
    \node [draw, circle, right=0.5cm of r2] (sum) {$+$};
    % Above center: 0.7, R
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of g2] (g1) {$0.7$};
    \node [draw, rectangle, right=0.5cm of g1.east] (r1) {$\mathcal{R}$};

    % Top: 1
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of g1] (g0) {$1$};

    % Below center: 0.7³, R³
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, below=\rowsep of g2] (g3) {$0.7^3$};
    \node [draw, rectangle, right=0.5cm of g3.east] (r3) {$\mathcal{R}^3$};

    % Continuation (left)
    \coordinate [below=0.5cm of g3] (belowg3);
    \node (dots) at (branch |- belowg3) {$\cdots$};

    % X to all gains
    \draw (in) -- (branch);
    \draw [->] (branch) |- (g0.west);
    \draw [->] (branch) |- (g1.west);
    \draw [->] (branch) -- (g2.west);
    \draw [->] (branch) |- (g3.west);
    \draw [->] (branch) -- (dots);

    % Gains to delays
    \draw [->] (g1.east) -- (r1);
    \draw [->] (g2.east) -- (r2);
    \draw [->] (g3.east) -- (r3);

    % To first sum
    \coordinate [left=0.4cm of sum] (junc);
    \draw [->] (g0.east) -- (g0.east -| junc) -- (sum);
    \draw [->] (r1) -- (r1 -| junc) -- (sum);
    \draw [->] (r2) -- (sum);
    \draw [->] (r3) -- (r3 -| junc) -- (sum);
    \node (dotsr) at (junc |- belowg3) {$\cdots$};
    \draw [->] (dotsr) -- (sum);

    % Second system (0.9 gains)
    \coordinate [right=0.3cm of sum] (branch2);

    % Center row: 0.9², R²
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.6cm of branch2] (h2) {$0.9^2$};
    \node [draw, rectangle, right=0.5cm of h2.east] (s2) {$\mathcal{R}^2$};
    \node [draw, circle, right=0.5cm of s2] (sum2) {$+$};
    \node [right=0.5cm of sum2] (out) {$Y$};

    % Above center: 0.9, R
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of h2] (h1) {$0.9$};
    \node [draw, rectangle, right=0.5cm of h1.east] (s1) {$\mathcal{R}$};

    % Top: 1
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of h1] (h0) {$1$};

    % Below center: 0.9³, R³
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, below=\rowsep of h2] (h3) {$0.9^3$};
    \node [draw, rectangle, right=0.5cm of h3.east] (s3) {$\mathcal{R}^3$};

    % Continuation (left)
    \coordinate [below=0.5cm of h3] (belowh3);
    \node (dots2) at (branch2 |- belowh3) {$\cdots$};

    % First sum to all b-gains
    \draw (sum) -- (branch2);
    \draw [->] (branch2) |- (h0.west);
    \draw [->] (branch2) |- (h1.west);
    \draw [->] (branch2) -- (h2.west);
    \draw [->] (branch2) |- (h3.west);
    \draw [->] (branch2) -- (dots2);

    % b-gains to delays
    \draw [->] (h1.east) -- (s1);
    \draw [->] (h2.east) -- (s2);
    \draw [->] (h3.east) -- (s3);

    % To second sum
    \coordinate [left=0.4cm of sum2] (junc2);
    \draw [->] (h0.east) -- (h0.east -| junc2) -- (sum2);
    \draw [->] (s1) -- (s1 -| junc2) -- (sum2);
    \draw [->] (s2) -- (sum2);
    \draw [->] (s3) -- (s3 -| junc2) -- (sum2);
    \node (dotsr2) at (junc2 |- belowh3) {$\cdots$};
    \draw [->] (dotsr2) -- (sum2);

    % Output
    \draw [->] (sum2) -- (out);
\end{tikzpicture}
\end{document}
```


For the [[Transfer Function]] $H = (1 + 0.7\mathcal{R} + 0.7^2\mathcal{R}^2 + \cdots) \cdot (1 + 0.9\mathcal{R} + 0.9^2\mathcal{R}^2 + \cdots)$, we can tell that the signal first goes through an infinite-feed forward system with gains of the exponentials of 0.9, before going through the same thing but with 0.7.
```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.6, transform shape]

    \def\rowsep{0.6cm}

    % Input
    \node (in) {$X$};
    \coordinate [right=0.3cm of in] (branch);

    % Center row: 0.9², R²
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.6cm of branch] (g2) {$0.9^2$};
    \node [draw, rectangle, right=0.5cm of g2.east] (r2) {$\mathcal{R}^2$};
    \node [draw, circle, right=0.5cm of r2] (sum) {$+$};
    % Above center: 0.9, R
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of g2] (g1) {$0.9$};
    \node [draw, rectangle, right=0.5cm of g1.east] (r1) {$\mathcal{R}$};

    % Top: 1
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of g1] (g0) {$1$};

    % Below center: 0.9³, R³
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, below=\rowsep of g2] (g3) {$0.9^3$};
    \node [draw, rectangle, right=0.5cm of g3.east] (r3) {$\mathcal{R}^3$};

    % Continuation (left)
    \coordinate [below=0.5cm of g3] (belowg3);
    \node (dots) at (branch |- belowg3) {$\cdots$};

    % X to all gains
    \draw (in) -- (branch);
    \draw [->] (branch) |- (g0.west);
    \draw [->] (branch) |- (g1.west);
    \draw [->] (branch) -- (g2.west);
    \draw [->] (branch) |- (g3.west);
    \draw [->] (branch) -- (dots);

    % Gains to delays
    \draw [->] (g1.east) -- (r1);
    \draw [->] (g2.east) -- (r2);
    \draw [->] (g3.east) -- (r3);

    % To first sum
    \coordinate [left=0.4cm of sum] (junc);
    \draw [->] (g0.east) -- (g0.east -| junc) -- (sum);
    \draw [->] (r1) -- (r1 -| junc) -- (sum);
    \draw [->] (r2) -- (sum);
    \draw [->] (r3) -- (r3 -| junc) -- (sum);
    \node (dotsr) at (junc |- belowg3) {$\cdots$};
    \draw [->] (dotsr) -- (sum);

    % Second system (0.7 gains)
    \coordinate [right=0.3cm of sum] (branch2);

    % Center row: 0.7², R²
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.6cm of branch2] (h2) {$0.7^2$};
    \node [draw, rectangle, right=0.5cm of h2.east] (s2) {$\mathcal{R}^2$};
    \node [draw, circle, right=0.5cm of s2] (sum2) {$+$};
    \node [right=0.5cm of sum2] (out) {$Y$};

    % Above center: 0.7, R
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of h2] (h1) {$0.7$};
    \node [draw, rectangle, right=0.5cm of h1.east] (s1) {$\mathcal{R}$};

    % Top: 1
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, above=\rowsep of h1] (h0) {$1$};

    % Below center: 0.7³, R³
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, below=\rowsep of h2] (h3) {$0.7^3$};
    \node [draw, rectangle, right=0.5cm of h3.east] (s3) {$\mathcal{R}^3$};

    % Continuation (left)
    \coordinate [below=0.5cm of h3] (belowh3);
    \node (dots2) at (branch2 |- belowh3) {$\cdots$};

    % First sum to all b-gains
    \draw (sum) -- (branch2);
    \draw [->] (branch2) |- (h0.west);
    \draw [->] (branch2) |- (h1.west);
    \draw [->] (branch2) -- (h2.west);
    \draw [->] (branch2) |- (h3.west);
    \draw [->] (branch2) -- (dots2);

    % b-gains to delays
    \draw [->] (h1.east) -- (s1);
    \draw [->] (h2.east) -- (s2);
    \draw [->] (h3.east) -- (s3);

    % To second sum
    \coordinate [left=0.4cm of sum2] (junc2);
    \draw [->] (h0.east) -- (h0.east -| junc2) -- (sum2);
    \draw [->] (s1) -- (s1 -| junc2) -- (sum2);
    \draw [->] (s2) -- (sum2);
    \draw [->] (s3) -- (s3 -| junc2) -- (sum2);
    \node (dotsr2) at (junc2 |- belowh3) {$\cdots$};
    \draw [->] (dotsr2) -- (sum2);

    % Output
    \draw [->] (sum2) -- (out);
\end{tikzpicture}
\end{document}
```

In practice, if you wanted to compute an [[Infinite Impulse Response Filter|IIR]] system quickly on parallel hardware (e.g. [[CUDA]]), you could truncate this feed-forward representation at $N$ terms to approximate it. Because the [[Feed-Forward]] representation has no data dependencies between samples, it is very parallelizable. The pole magnitude determines how many terms you need: poles close to the unit circle require large $N$, while poles deep inside converge with small $N$. If a pole is outside the unit circle, the series diverges and this approach does not work.

### Equivalence to Parallel First-Order System
We can also algebraicly manipulate the starting [[Transfer Function]] to be a sum of two first order systems using [[Partial Fractions|Partial Fraction Decomposition]]. Whereas a product of systems is cascading, a sum of systems means that they are being summed together after running in parallel. 
$$
\begin{align}
H &= \frac{1}{(1-0.7\mathcal{R})(1-0.9\mathcal{R})} \\
&= \frac{A}{1-0.9\mathcal{R}} + \frac{B}{1-0.7\mathcal{R}} \\
1 &= A(1-0.7\mathcal{R}) + B(1-0.9\mathcal{R}) \\
0.9\mathcal{R} = 1: \quad 1 &= A\left(\frac{2}{9}\right) \implies A = \frac{9}{2} = 4.5 \\
0.7\mathcal{R} = 1: \quad 1 &= B\left(\frac{-2}{7}\right) \implies B = \frac{-7}{2} = -3.5 \\
H &= \frac{4.5}{1-0.9\mathcal{R}} - \frac{3.5}{1-0.7\mathcal{R}}
\end{align}
$$

Based on this new transfer function
* The summation of the expressions tells us that we have two parallel systems being summed together
* The polynomials in the denominator in both expressions tells us that both systems are [[Feedback]]
* The order of both polynomials being 1 tells us that the systems are first order systems

Inspecting the [[Block Diagram]], these features are visually apparent.

```tikz
\usetikzlibrary{positioning, shapes.geometric}
\begin{document}
\begin{tikzpicture}[>=latex, scale=0.7, transform shape]

    % Input
    \node (in) {$X$};
    \coordinate [right=0.2cm of in] (split);

    % === Top subblock (pole 0.9) ===
    \node [draw, circle, right=0.4cm of split, yshift=1.2cm] (sum1) {$+$};
    \coordinate [right=2cm of sum1] (branch1);
    \node [above=0.1cm of branch1] {$Y_1$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.4cm of branch1] (gainA1) {$4.5$};
    \node [draw, rectangle, below=0.7cm of branch1] (delay1) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.7cm of delay1] (gainP1) {$0.9$};

    % === Bottom subblock (pole 0.7) ===
    \node [draw, circle, right=0.4cm of split, yshift=-1.2cm] (sum2) {$+$};
    \coordinate [right=2cm of sum2] (branch2);
    \node [above=0.1cm of branch2] {$Y_2$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, right=0.4cm of branch2] (gainA2) {$-3.5$};
    \node [draw, rectangle, below=0.7cm of branch2] (delay2) {$\mathcal{R}$};
    \node [draw, isosceles triangle, isosceles triangle apex angle=60, shape border rotate=180, left=0.7cm of delay2] (gainP2) {$0.7$};

    % Output adder
    \node [draw, circle, right=0.4cm of gainA1, yshift=-1.2cm] (sumout) {$+$};
    \node [right=0.3cm of sumout] (out) {$Y$};

    % Input splitting
    \draw (in) -- (split);
    \draw [->] (split) |- (sum1);
    \draw [->] (split) |- (sum2);

    % Top subblock: main path with branch tee
    \draw [->] (sum1) -- (gainA1.west);
    \draw [->] (branch1) -- (delay1);
    \draw [->] (delay1) -- (gainP1.east);
    \draw [->] (gainP1.west) -| (sum1);

    % Bottom subblock: main path with branch tee
    \draw [->] (sum2) -- (gainA2.west);
    \draw [->] (branch2) -- (delay2);
    \draw [->] (delay2) -- (gainP2.east);
    \draw [->] (gainP2.west) -| (sum2);

    % Forward gains to output adder
    \draw [->] (gainA1.east) -- (gainA1.east -| sumout) -- (sumout);
    \draw [->] (gainA2.east) -- (gainA2.east -| sumout) -- (sumout);

    % Output
    \draw [->] (sumout) -- (out);
\end{tikzpicture}
\end{document}
```

Each term's denominator contributes one pole: $0.9$ from $\frac{4.5}{1-0.9\mathcal{R}}$ and $0.7$ from $\frac{-3.5}{1-0.7\mathcal{R}}$. The coefficients $4.5$ and $-3.5$ are the residues at each pole.

You can also intuit the behavior of the overall system based on the behavior of the subsystems: $y[n] = 4.5(0.9)^n-3.5(0.7)^n$; both systems are exponential decay, but one decays way faster than the other. The result is a system that briefly surges before falling off.

# Finding Poles
The key to simplifing a higher-order system is by identifying its *Poles*, i.e. complex roots of the denominator of the [[Transfer Function]]. Substituting $z^{-1}$ in for $\mathcal{R}$ may or may not be helpful. Factoring the denominator is the most straightforward approach. See some of the math in the [[#Example Systems]] section for example approaches.
## Example 1
We are given the [[Difference Equation]] of a system. We want to understand the long-term behavior of the [[Impulse Response]] of the system, and its poles.
$$
y[n] = -\frac{1}{4}y[n-1] + \frac{1}{8}y[n-2] + x[n-1] - \frac{1}{2}x[n-2]
$$

Start by rexpressing the difference equation in operator notation, and finding the [[Transfer Function]].
$$
\begin{align}
Y &= -\frac{1}{4}\mathcal{R}Y + \frac{1}{8}\mathcal{R}^2Y + \mathcal{R}X - \frac{1}{2}\mathcal{R}^2X \\
\left(1 + \frac{1}{4}\mathcal{R} - \frac{1}{8}\mathcal{R}^2\right)Y &= \left(\mathcal{R} - \frac{1}{2}\mathcal{R}^2\right)X \\
H = \frac{Y}{X} &= \frac{\mathcal{R} - \frac{1}{2}\mathcal{R}^2}{1 + \frac{1}{4}\mathcal{R} - \frac{1}{8}\mathcal{R}^2}
\end{align}
$$

We can factor both the numerator and denominator.

$$
\begin{align}
H &= \frac{\mathcal{R} - \frac{1}{2}\mathcal{R}^2}{1 + \frac{1}{4}\mathcal{R} - \frac{1}{8}\mathcal{R}^2} \\
&= \frac{\mathcal{R}\left(1 - \frac{1}{2}\mathcal{R}\right)}{\left(1 - \frac{1}{4}\mathcal{R}\right)\left(1 + \frac{1}{2}\mathcal{R}\right)}
\end{align}
$$

Inspecting the denominator, we can solve for the poles by finding the roots of each of the factors. 

> [!help]- How to find the poles from the factored Transfer function.
> 
> Find the first pole:
> $$
> \begin{align}
> \left( 1-\frac{1}{4} \mathcal{R}\right) &= 0\\
> \left( 1-\frac{1}{4} z^{-1}\right) &= 0\\
> z^{-1} &= 4\\
> z &= \frac{1}{4}\\
> \end{align}
> $$
> 
> Find the second pole:
> 
> $$
> \begin{align}
> \left(1 + \frac{1}{2}\mathcal{R}\right) &= 0 \\
> \left(1 + \frac{1}{2}z^{-1}\right) &= 0 \\
> z^{-1} &= -2 \\
> z &= -\frac{1}{2}
> \end{align}
> $$

You will find that we get $z = \frac{1}{4},-\frac{1}{2}$. Now, the shortcut is just to look at the poles, to determine the behavior, but we will do the long way to maximize context.

Factor out the $\mathcal{R}$ from the numerator and decompose the rest using [[Partial Fractions]]:

$$
\begin{align}
H &= \mathcal{R} \cdot \frac{1 - \frac{1}{2}\mathcal{R}}{\left(1 - \frac{1}{4}\mathcal{R}\right)\left(1 + \frac{1}{2}\mathcal{R}\right)} \\
&= \mathcal{R} \left(\frac{A}{1 - \frac{1}{4}\mathcal{R}} + \frac{B}{1 + \frac{1}{2}\mathcal{R}}\right) \\
1 - \frac{1}{2}\mathcal{R} &= A\left(1 + \frac{1}{2}\mathcal{R}\right) + B\left(1 - \frac{1}{4}\mathcal{R}\right) \\
\frac{1}{4}\mathcal{R} = 1: \quad -1 &= 3A \implies A = -\frac{1}{3} \\
-\frac{1}{2}\mathcal{R} = 1: \quad 2 &= \frac{3}{2}B \implies B = \frac{4}{3} \\
H &= \mathcal{R}\left(-\frac{1}{3} \cdot \frac{1}{1 - \frac{1}{4}\mathcal{R}} + \frac{4}{3} \cdot \frac{1}{1 + \frac{1}{2}\mathcal{R}}\right)
\end{align}
$$

Each $\frac{1}{1-p\mathcal{R}}$ is a first-order feedback system with impulse response $p^n$. The $\mathcal{R}$ in front delays everything by one sample. So the impulse response is

$$
h[n] = -\frac{1}{3}\left(\frac{1}{4}\right)^{n-1} + \frac{4}{3}\left(-\frac{1}{2}\right)^{n-1}, \quad n \geq 1
$$

with $h[0] = 0$. The two [[Fundamental Mode|fundamental modes]] are $\left(\frac{1}{4}\right)^n$ and $\left(-\frac{1}{2}\right)^n$. All of this was already known when we found the poles, but it is helpful to find the impulse response equation to kind of prove why it is the way it is. The $-\frac{1}{2}$ is the dominant exponential term. Because of this, the impulse response will exhibit alternating behavior. Both poles' magnitudes are less than 1, so the overall behavior is decay. 

# Complex Poles
So far, we have only considered scenarios in which $\mathrm{Im}(p)=0$. However, this ignores the infinitely large set of possible values that are solidly within the [[Complex Plane]], instead of just walking the [[Real Number]] line.
* Similar to complex solutions in [[Differential Equation|Differential Equations]]
	* Complex poles always come in conjugate pairs, corresponding to $z=re^{\pm j \Omega }$
	* The angle $\Omega$ determines oscillation
		* $\Omega = 0$: no oscillation (positive real pole, monotonic)
		* $\Omega = \pi$: half-turn each step (negative real pole, alternating sign)
		* $0 < \Omega < \pi$: oscillation with period $\frac{2\pi}{\Omega}$ samples
	* The magnitude $r$ determines exponential behavior
		* $r < 1$: exponential decay
		* $r = 1$: constant magnitude
		* $r > 1$: exponential growth
* You can still do [[Partial Fractions]]. It's exactly the same.
* The [[Impulse Response]] of a conjugate pair of poles combines into $r^n \cos(n\Omega)$, a sinusoid with an exponential envelope

## Example 1
Find the poles for the following [[Transfer Function]] 

$$
H = \frac{1}{1 - \mathcal{R} + \mathcal{R}^2}
$$

Substituting $z^{-1}$ for $\mathcal{R}$ and finding the roots of the denominator:

$$
\begin{align}
1 - z^{-1} + z^{-2} &= 0 \\
z^2 - z + 1 &= 0 \\
z &= \frac{1 \pm \sqrt{1-4}}{2} = \frac{1 \pm j\sqrt{3}}{2} \\
z &= e^{\pm j\pi/3}
\end{align}
$$

The poles are a conjugate pair at $r=1$, $\Omega = \pi/3$. Since $r=1$, the impulse response neither grows nor decays. Since $\Omega = \pi/3$, the oscillation has period $\frac{2\pi}{\pi/3} = 6$ samples.

$$
h[n] = \cos\left(\frac{n\pi}{3}\right), \quad n \geq 0
$$
