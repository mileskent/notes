A bivariate random variable $(X, Y)$ models two random variables simultaneously when they are related. 

The joint [[Cumulative Density Function|CDF]] for all BRVs is

$$F(x, y) \equiv P(X \le x, Y \le y)$$ 
# Discrete Bivariate Random Variables
If $X$ and $Y$ are discrete RVs, $(X,Y)$ is a jointly discrete bivariate RV. 
* [[Probability Mass Function|PMF]]: $f(x,y) = P(X = x, Y = y)$ 
	* $0 \le f(x,y) \le 1$ 
	* $\sum_{x}\sum_{y} f(x,y) = 1$ 
	* $P((X,Y) \in A) = \sum\sum_{(x,y)\in A} f(x,y)$ 
# Continuous Bivariate Random Varibales
If $X$ and $Y$ are continuous RVs, $(X,Y)$ is a jointly continuous RV if there exists a joint probability density function (PDF) $f(x,y)$: 
- $f(x,y) \ge 0, \forall x,y$ 
- $\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} f(x,y) \, dx \, dy = 1$ 
- $P((X,Y) \in A) = \iint_{A} f(x,y) \, dx \, dy$ 
 
 $$f(x,y) = \frac{\partial^2}{\partial x \, \partial y} F(x,y)$$
