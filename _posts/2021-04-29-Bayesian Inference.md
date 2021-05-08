## Types of inference model

![]({{site.url}}/{{site.baseurl}}/assets/bayesian_inference/bayesian_model.jpg)

A system is sending signal $S$, in channel it is multiplied by $a$ and some random noise $W$ is added. We get $X$ in our end.

Two types:
- Hypothesis testing: unkown quantity is discrete values
- Estimation: unknown quantity is continuous values

![]({{site.url}}/{{site.baseurl}}/assets/bayesian_inference/cla_bay_infer.jpg)

**Hypothesis Testing**

$$P_{\theta \| X}(\theta \| x) = \frac{P_\theta(\theta)P_{X\|\theta}(x\|\theta)}{P_X(x)}$$

$$P_{\theta \| X}(\theta \| x) = \frac{P_\theta(\theta)f_{X\|\theta}(x\|\theta)}{f_X(x)}$$

**Estimation**

$$f_{\theta \| X}(\theta \| x) = \frac{f_\theta(\theta)f_{X\|\theta}(x\|\theta)}{f_X(x)}$$


This is how posterior distribution looks like:

![]({{site.url}}/{{site.baseurl}}/assets/bayesian_inference/dist.jpg)

We may choose best $\theta$ two ways:

- Maximum aposteriori probability(MAP) $$P_{\Theta\|X}(\theta^*\|x) = \arg\max_{\theta} P_{\Theta\|X}(\theta\|x)$$
- Conditional Expectation $E\[\Theta\|X\]$, We want to $\min E\[(\Theta -c)^2\|X\]$