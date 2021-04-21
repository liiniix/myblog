<iframe width="560" height="315" src="https://www.youtube.com/embed/3MOahpLxj6A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
### Random Variables

$$X: \Omega \to \mathbb{R}$$
$$ \Omega: \text{ Sample space}$$
$$\mathbb{R}: \text{ Real Number}$$

**Notation: $P_X(x)$ or $Pr(X=x)$**

### Expectation

$$\mathbb{X}(X) = \sum_x xP_X(x)$$

Interpretation:
- Center of gravity of PMF
- Average in large number of repetation

Linearity Properties of Expectation:

$\alpha, \beta$ are constants:
- $ \mathbb{E}(\alpha) = \alpha $
- $ \mathbb{E}(\alpha X) = \alpha \mathbb{E}(X) $
- $ \mathbb{E} (\alpha X + \beta) = \alpha \mathbb{E}(X) + \beta $

### Variance

$$\mathbb{E}(g(X)) = \sum_x p(x)g(x)$$
$$\mathbb{E}(X^2) = \sum_x p(x)x^2$$

$$ Var(X) = \mathbb{E} (X-\mathbb{E}(X))^2 = \mathbb{E} (X^2 -2X\mathbb{E}(X) + \mathbb{E}(X)^2) = \mathbb{E}(X^2) - \mathbb{E}(X)^2$$

Properties of Variance:
- $Var(X) \ge 0$
- $ Var(\alpha X + \beta) = \alpha^2Var(X)$

### Law of total expectation/Law of Iterated Expectations
$$\mathbb{E}\[X\] = \mathbb{E}\[\mathbb{E}\[X\|Y\]\] = \mathbb{E}\[X|A_1\]P(A_1) + \dots + \mathbb{E}\[X\|A_n\]P(A_n)$$

<iframe width="560" height="315" src="https://www.youtube.com/embed/P7a4bjE6Crk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Conditional expectation
Given the value of $y$ for r.v $Y$:
    $$\mathbb{E}\[X\|Y=y\] =\sum_x xp_{X\|Y}(x\|y)$$

$$ \mathbb{E}\[ \mathbb{E}\[    X\|Y   \]  \] = \sum_y \mathbb{E}\[X\|Y=y\] P_Y(y) = \mathbb{E}\[X\] $$