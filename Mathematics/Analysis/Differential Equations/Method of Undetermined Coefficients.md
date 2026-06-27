---
date: 2025-10-15
---

$$
ay'' + by'+cy = f(t)
$$
where $a, b, c$ are constants, $a \neq 0$, and $f(t)$ is a given function called the nonhomogenous term
The general solution structure is as follows:
$$
y(t) = y_{p}(t)+y_{c}(t)
$$
where $y_c(t)$ are solutions of the homogeneous equation:
$$
ay_{c}'' + by_{c}' + cy_{c} = 0
$$
where $y_p(t)$ is a particular solution of the nonhomogenous (original) equation:
$$
ay_{p}'' + by_{p}' + cy_{p} = f(t)
$$

Reminder: $c\lambda^2 + b\lambda + c = 0$ is the [[Characteristic Equation]] for the $y_c$ family of solutions

# Approach
**Step 1**: Find complementary solutions $y_c$
**Step 2:** Find particular solution $y_p$
Constructing a trial term:
$$
f(t) = P_{n}(t) e^{k t} \implies y_{p}(t) = t^s P_n(t) e^{k t}
$$
where $s$ is the number of terms in $y_c(t)$ that have $e^{kt}$, where $P_{n}(t)$ is a n-degree polynomial
If any term in the guess for $y_p$ is a solution to $y_c$, multiply by $t$. In other words, multiply by $t^s$
*If there are multiple terms, superposition applies.* What that means is you substitute one trial solution terms back into the original equation, at a time, in order to find the undetermined coefficients.
Note that trig functions are actually exponentials:
$$
\sin(t) = \frac{1}{2i} (e^{it} - e^{-it})
\quad\quad
\cos(t) = \frac{1}{2} (e^{it} + e^{-it})
$$
Also recall ![[Euler's Identity]]
Plug that term into the original equation to solve for undetermined coefficients.
**Step 3:** 
$$
y(t) = y_{p}(t)+y_{c}(t)
$$

# Example
$3y''+y'-2y = 10e^{4t},\ y(0) = -1,\ y'(0) = 3$
**Step 1**: Find complementary solutions $y_c$
$3y_{c}'' + y_{c}' - 2y_{c} = 0$
$3\lambda^2 + \lambda - 2 = 0 \implies \lambda = -1, \frac{2}{3} \implies y_{c} = C_{1}e^{-t}+C_{2}e^{2/3 t}$
**Step 2:** Find particular solution $y_p$
$10e^{4t} \implies y_{p}(t) = Ke^4t$
Plug in: $3(Ke^{4t})'' + (Ke^{4t})' -2 (Ke^{4t}) = 50Ke^{4t} = 10e^{4t} \implies K = \frac{1}{5}$
**Step 3:**
$$
y(t) = y_{p}(t) = y_{c}(t) = \frac{1}{5}e^{4t} + C_{1}e^{-t}+C_{2}e^{2/3 t}
$$
Now do the IVP. We have already concluded the method of undetermined coefficients.
After doing the IVP you get
$$
y(t) = \frac{1}{5}e^{4t} - \frac{9}{5}e^{-t}+\frac{3}{5}e^{2/3 t}
$$
