*Degrees of Freedom* is a property of a [[Statistic]] or [[Point Estimation|Point Estimator]] that describes how many variables are free to vary while maintaining the feature's validity.
* For statistic/PE $T$ that is a [[Linear Transformation]], dof = [[Nullity|nullity]](T)
# Example
For example, a **sample mean** is a linear function of its inputs, because it is a sum of the [[Random Variable|RV]]s, all divided by a scalar. This is a linear transformation, as well.
$$
\text{mean}(X_{1..n}) = \frac{\sum X_{1..n}}{n} = \overline{X}
$$

Due to this linearity, all of the inputs except for the last can be any value. If you allow the first $n-1$ RV to vary, then the $n^{\text{th}}$ RV is forced to a specific value.

$$
X_{n} = n\overline{X} - \sum X_{1..n-1}
$$
Therefore, for sample mean, $\text{dof} = n-1$
