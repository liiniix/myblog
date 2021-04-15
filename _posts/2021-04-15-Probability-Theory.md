### Random Variable

| Discrete($X$) | Continuous($Y$) |
|---|---|
|Prob Mass Func/p.m.f.($f_X$)|Prob Distribution Func/p.d.f.($f_Y$)|
| $f_X:\Omega \to \mathbb{R}_{\ge 0} $, $\Omega $ means sample space| $f_Y:\Omega \to \mathbb{R}_{\ge 0} $ |
| $\sum_{x \in \Omega} f_X = 1$ | $\int_{\Omega} f_Y(y)dy = 1 $|

Ex:
$X$ is the random variable, 
$$
X = \begin{cases}
        1 \text{, with prob } 1/3\\
        -1 \text{, with prob } 1/3\\
        0 \text{, with prob } 1/3\\
    \end{cases}
$$

### Independence

$f_X$ is the p.m.f:

$f_X(0)=f_X(1)=F_X(-1) = 1/3$

Ex:
$f_Y(Y)=1$ for all $y \in \[0,1\]$ p.d.f. of uniform random variable $\[0,1\]$

### Prob of event
$P(A) = \sum_{X\in A} f_X(X) = \int_A f_Y(Y)dy$

### Expectation
$\mathbb{E} \[X\] = \sum_\Omega Xf_X(X)$

$\mathbb{E} \[Y\] = \int_\Omega Yf_Y(Y)dy$

Two random variables $X_1, X_2$ are independent if $P(X_1\in A , X_2 \in B) = P(X_1\in A)P(X_2 \in B)$ for all event A and B.

#### Mutually Independence
#### Pairwise Independence

### Normal Distribution
Continuous random variable has normal distribution $N(\mu, \sigma)$ if $f(X) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ for $(-\infty, \infty)$

Ex: $P_n - P_{n-1} = N(0, 1)$  ??
(Stock price difference in normally distributed)

Not a good model.

Instead we want the relative differnce to be normally distributed.

$\frac{P_n - P_{n-1}}{P_n} \sim \mathcal{N}(0, 1)$

(Q) What does the distribution of price look like?

Log-normal random variable $Y$ such that $log(Y)$ is normally distributed.

(Thm) (Change of variable)
Suppose $X, Y$ are random vars such that $P(X\le x) = P(Y \le h(x)), \forall x$. Then $f_X(X) = f_Y(h(x)h'(x)$

$X$: log-normal distribution

$Y$: normal distribution with $\mu, \sigma$

$P(X\le x) = P(Y \le log(x))$

$f_X(X) = f_Y(log(X))\frac{1}{x} = \frac{1}{x\sigma\sqrt{2\pi}}e^{-\frac{(log(x)-\mu)^2}{2\sigma^2}}$ ($x>0$)

### Poission Dist
### Exponential Dist
These are called **exponential family of distribution**.

### Moment Generating Function
Given a random var. What we want to study:

- Study statistics, k-th moment of random var, $\mathbb{E}\[X^k\]$, moment fenerating function which is studying all the moment in one function.
- Study long-term/large-scale behaviour.
$$\begin{cases}
    \text{Law of large number}\\
    \text{central limit theorem}
\end{cases}
$$

Moment generating function:
$M_X(t) = \mathbb{E}\[e^{tX}\]$

> Not necessarily exist

$$\frac{d^k}{dt^k} M_x(t) = \mathbb{E}\[X^k\]$$

### Law of large numbers
**Thm: Weak law of large numbers:**

Let $X_1,\dots,X_n$ be independent random variables with identical distribution(iid), mean be $\mu$, and variance be $\sigma^2$.

$ X = \frac{1}{n}(X_1+\dots+X_n) $

Then $\forall \epsilon > 0, P(\|X-\mu\|\ge \epsilon) \to 0$ as $n \to \infty$

**Ex: Casino: Playing blackjack:**

Under optimal strategy $\approx 48\%$ chance of winning.

From the casino's point of view, they are taking enormous value n. So casio's winning big money.

**Mean of $X$ is $\mu$ and variance of $X$ is $\frac{\sigma^2}{n}$**

### Central Limit Theorem
**THM:**

$X_1, X_2, \dots, X_n$ be iid random var with mean $\mu$ and var $\sigma^2$.

$Y_n = \frac{1}{\sqrt{n}}\sum_{i=1}^n (X_i-\mu)$

Then the dist of $Y_n$ converges to that of $\mathbb{N}(0, \sigma^2)$