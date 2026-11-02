---
date: 2026-11-02
aliases:
  - MOM
---
In Point Estimation, we want to estimate parameters $\theta$ of an unknown population distribution using sample data. To do this, we borrow the concept of moments from physics. 

In general, a moment is a weighted distance from an axis. The moment of force is torque, where the weight is force or literal weight. Imagine a flat seesaw at rest with weights distributed across it. The torque each weight applies is the product of x, the signed distance from the axis of rotation, and F, the force of the weight. The net torque, the sum of these individual torques.
$$
\tau = xF \quad \tau_{\text{net}} = \sum_{i} x_{i}F_{i}
$$
Furthermore, instead of only indexing each occurence of a torque, we can alternatively create a function $f(x)$ that gives the force at every $x$, which allows us to write $\tau_{\text{net}}$ as a discrete or continuous sum over a domain $D$.

$$
\begin{align}
\tau_{\text{net}} &= \sum_{x\in D}\ x \cdot f(x) 
\quad \text{or} \quad
\int_{D} x \cdot f(x)\ dx\\
&=\text{sum}\ x \cdot f(x)
\end{align}
$$

where the "sum" expression is shorthand for this summation regardless of whether $f(x)$ is discrete or continuous.

We can also reinterpret our $f(x)$ to be a [[Probability Mass Function|PMF]]/[[Probability Density Function|PDF]] instead of a force function. You will recognize the moment equation above as [[Expected Value]].

$$
E[X] = \text{sum}\ x f(x)
$$
We care about this $f(x)$ because it contains information about the hidden parameters of the population distribution that we are sampling from, including the parameter we want to estimate. 

We define the *kth* order moment as the following, where k > 1 is used for systems of equations with greater than one unknown, to provide additional valid equations until we have a well-determined system of equations.
$$
E[X^k] = \text{sum}\ x^k f(x)
$$

Yep. It's just literally just expected value. And when we use the higher degrees of k, it literally just adjusts the scale of the x axis (distance from the axis) from linear to quadratic to cubic to quartic, etc etc. Each new k value results in a new polynomially scaled version of the original distribution that gives a new equation that we can use to solve the system of equations that I am going to shortly introduce.

Notice how $E(X) =\text{fn}(\text{parameters})$
* $X \sim N \to E(X) = \mu$
* $X \sim \text{Pois} \to E(X) = \lambda$
* $X \sim \text{U}(a,b) \to E(X) = \frac{a+b}{2}$

Furthermore, we can also calculate sample moments, for k = 1 or above if needed.

$$
\begin{align}
X_{1..n} \sim^{\text{iid}} f(x;n) &\implies
\overline{X}^k = 
\frac{1}{n} \sum^n_{i=1} X^k_{i}\\
&\implies
\overline{X} = \frac{1}{n} \sum^n_{i=1} X_{i}
\end{align}
$$

Using the following idea, we can estimate our parameters in the following way.

$$
\overline{X} \approx E(X) = \text{fn}(\theta) \implies \overline{X} \approx \text{fn}(\theta)
$$

Or if more than k = 1 is needed, the following is also applicable

$$
\overline{X}^k \approx E(X^k) = \text{fn}(\theta) \implies \overline{X}^k \approx \text{fn}(\theta)
$$

Our system of equations is of the following form, where at least k = 1 is used, and where the range of k used is equal to the dimension of $\theta$

$$
\begin{matrix}
\overline{X}^k = \frac{1}{n} \sum^n_{i=1} X^k_{i} \approx E(X^k) = \text{sum}\ x^k f(x) = \text{fn}(\theta) \\
\implies
\overline{X}^k \approx\text{fn}(\theta),\ \overline{X}^k =\text{fn}(\hat\theta) \\
\end{matrix}
$$

# Examples
> [!Example]- $X \sim N$
> * Moment (k = 1): $E(X) = \mu$
> * T ito $\theta$: $\overline{X} \approx \mu$
>   $$\therefore\hat{\mu} = \overline{X}$$

> [!Example]- $X \sim \text{Pois}$
> * Moment (k = 1): $E(X) = \lambda$
> * T ito $\theta$: $\overline{X} \approx \lambda$
>   $$\therefore\hat{\lambda} = \overline{X}$$

> [!Example]- $X \sim \text{Exp}(\lambda)$
> * Moment (k = 1): $E(X) = \frac{1}{\lambda}$
> * T ito $\theta$: $\overline{X} \approx \frac{1}{\lambda}$
>   $$\therefore\hat{\lambda} = \frac{1}{\overline{X}}$$

> [!Example]- $X \sim U(0, \theta)$
> * Moment (k = 1): $E(X) = \frac{\theta}{2}$
> * T ito $\theta$: $\overline{X} \approx \frac{\theta}{2}$
>   $$\therefore\hat{\theta} = 2\overline{X}$$

> [!Example]- $X \sim U(a, b)$
> * Moment (k = 1): $E(X) = \frac{a + b}{2}$
> * Moment (k = 2): $E(X^2) = \frac{1}{3}(a^2 + ab + b^2)$
> * T ito $\theta$: $\overline{X} \approx \frac{a + b}{2}, \quad \overline{X^2} \approx \frac{1}{3}(a^2 + ab + b^2)$
>   $$\begin{align*}
>   a + b &\approx 2\overline{X} \\
>   (a+b)^2 - ab &\approx 3\overline{X^2} \\
>   (2\overline{X})^2 - ab &\approx 3\overline{X^2} \\
>   ab &\approx 4\overline{X}^2 - 3\overline{X^2} \\
>   t^2 - (2\overline{X})t + (4\overline{X}^2 - 3\overline{X^2}) &\approx 0 \\
>   t &\approx \frac{2\overline{X} \pm \sqrt{(-2\overline{X})^2 - 4(1)(4\overline{X}^2 - 3\overline{X^2})}}{2} \\
>   t &\approx \overline{X} \pm \sqrt{3\left(\overline{X^2} - \overline{X}^2\right)} \\
>   a \approx \overline{X} - \sqrt{3\left(\overline{X^2} - \overline{X}^2\right)}, &\quad b \approx \overline{X} + \sqrt{3\left(\overline{X^2} - \overline{X}^2\right)}
>   \end{align*}$$
>   $$\therefore\hat{a} = \overline{X} - \sqrt{3\left(\overline{X^2} - \overline{X}^2\right)}, \quad \hat{b} = \overline{X} + \sqrt{3\left(\overline{X^2} - \overline{X}^2\right)}$$
