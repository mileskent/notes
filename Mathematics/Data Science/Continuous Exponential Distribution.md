A kind of [[Continuous Distribution]] that models the time or space between independent events occurring at a constant average rate $\lambda$.
$$
X \sim \text{Exp}(\lambda) \quad \text{where}\ x \geq 0,\ \lambda>0
$$
* $f(x) = \lambda e^{-\lambda x}\quad\text{for } x\geq{0}$
* $E(X) =\frac{1}{\lambda}$
* $\text{Var}(X) = \frac{1}{\lambda}$
* $F_{X}(x)=\int^x_{0} f(t)\ dt = \int^x_{0} \lambda e^{-\lambda t}\ dt = 1-e^{-\lambda x}$
