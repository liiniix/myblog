**Def: Collection of random variables indexed by time**

$ X_0, X_1, X_2,\dots $ (discrete time)

$\\{X_t\\}_{t\ge 0}$ (continusous time)

![]({{site.url}}/{{site.baseurl}}/assets/stochastic_process/dt_ct_sp.jpg)

Alternative definition: Probability distribution over a space of paths.

Ex:
- $f(t) = t$ with probability $1$
-   * $f(t) = t, \forall t)$ with probability $1/2$
    * $f(t) = -t, \forall t)$ with prob $1/2$
- For each $$ t,
  f(t) =
  \begin{cases}
    t \text{, with prob 1/2}\\
    -t \text{, with prob 1/2}
  \end{cases}
$$

![]({{site.url}}/{{site.baseurl}}/assets/stochastic_process/examples.jpg)

Three types of questions we mainly study here:
- What are the dependency n th sequnce of values?
- What is the long term behaviour? (law of large numbersm central limit theorem)
- What are the boundary events? ( How often something extreme happen)

## Simple Random Walk
DEF:
$ Y_i : \text{i. i. d. random variables taking either 1 or -1 with prob 1/2}$

> i.i.d means independent indentically distributed

For each t, $X_t = \sum_{i=1}^t Y_i, X_0 = 0$

$X_0, X_1, X_2,\dots $ is call simple random walk.

![]({{site.url}}/{{site.baseurl}}/assets/stochastic_process/srw.jpg)

If we apply central limit theorem here, variance $\frac{1}{t}$ and standard deviation $\frac{1}{\sqrt{t}}$