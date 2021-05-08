## Review of previous notations
$$p_X(x) = P(X=x), \text{ Marginal}$$
$$p_{X, Y}(x, y) = P(X=x, Y=y), \text{ Disjoint}$$
$$p_{X\|Y}(x\|y) = P(X=x\|Y=y), \text{ Conditional}$$
$$p_X(x) = \sum_y p_{X,Y}(x,y), \text{ Marginal}$$
$$p_{X\|Y}(x,y) = p_X(x)p_{Y\|X}(y\|x), \text{ Conditional}$$
$$p_{X,Y,Z}(x, y, z) = p_X(x)p_{Y\|X}(y\|x)p_{Z\|X, Y}(z\|x, y)$$

## Expectation
$$\mathbb{E}\[X\] = \sum_x xp_X(x)$$
$$\mathbb{E}\[g(X, Y)\] = \sum_x\sum_y g(x,y) p_{X,Y}(x, y)$$
$$\mathbb{E}\[\alpha X + \beta\] = \alpha\mathbb{E}\[X\] + \beta $$
$$\mathbb{E}\[X+Y+Z\] = \mathbb{E}\[X\] + \mathbb{E}\[Y\] + \mathbb{E}\[Z\] $$
$$\mathbb{E}\[XY\] = \mathbb{E}\[X\]\mathbb{E}\[Y\], \text{ in case of independence} $$
$$\mathbb{E}\[g(X)h(Y)\] = \mathbb{E}\[g(X)\]\mathbb{E}\[h(Y)\], \text{ in case of independence} $$


## Varience
$$Var(\alpha X) \alpha^2 Var(X)$$
$$Var(X + \alpha) = Var(X) $$
$$Var(X + Y) = Var(X) + Var(Y), \text{ X and Y are independent}$$


### Binomial Dist

$$p_X(k) = {n \choose k}p^k(1-p)^{n-k}$$

$$ E\[X\] = \sum_{k=0}^n k {n \choose k}p^k(1-p)^{n-k}$$

Or let's say each trial is a rondim variable $X_i$. 
$$X_i = \begin{cases}
1 \text{ if success in trial i}\\
0 \text{ otherwiae}
\end{cases}$$

$$E\[X_i\] = p$$
$$X = \sum X_i$$
$$E\[X\] = \sum E\[X_i\] = np$$
$$Var(X_i) = p(1-p)$$
$$Var(X) = np(1-p)$$

## Continuius RV
![]({{site.url}}/{{site.baseurl}}/assets/random_vars/con_rv.jpg)

$$E\[X\] = \int_{-\infty}^{+\infty} x f_X(x)dx $$
$$E\[g(X)\] = \int_{-\infty}^{+\infty} g(x) f_X(x) $$
$$Var(X) = E\[X-E\[X\]\]^2 = \int (x-E\[X\])^2 f_X(x)dx$$