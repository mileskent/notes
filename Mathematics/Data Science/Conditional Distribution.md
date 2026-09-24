Given two jointly distributed random variables, the conditional [[Probability Mass Function|PMF]]/[[Probability Density Function|PDF]] of $X$ given $Y = y$ (where $f_Y(y) > 0$) is defined as:

$$f_{X|Y}(x|y) = \frac{f(x,y)}{f_Y(y)}$$

Similarly, the conditional distribution of $Y$ given $X = x$ is:

$$f_{Y|X}(y|x) = \frac{f(x,y)}{f_X(x)}$$

> **Finding Marginal from Conditional:** 
> 1. Find joint distribution: $f(x,y) = f_X(x) f(y|x)$
> 2. Integrate/Sum out $x$: $f_Y(y) = \int_{\mathbb{R}} f(x,y) \, dx$