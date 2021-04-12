Autoencoders are another family of networks.
> Encoders take input in one language, output in another. But autoencoders take input and output in same thing but something intermediate.

Autoencoders are special type of feed forwar network that are used for `Compression`, `Denoising`, `Sparse representation`, `Data generation`.

Encoder: `f()`\\
Decodeer: `g()`\\
Autoencoder: `g(f())`

### Linear autoencoder
- `f` and `g` are linear and denoted by $W_f$ and $W_g$.
![]({{site.url}}/{{site.baseurl}}/assets/autoencoder/autoencoder_block.jpg)

#### Objective
$ \underset{w}{\mathrm{min}} \frac{1}{2}\sum_n \|\|W_gW_fx_n-x_n\|\|_2^2$

This objective is obtained by PCA.

### Nonlinear autoencoder
### Deep autoencoder
Multiple layers for encoder and decoder.
### Sparse Representation
Instead of lower dimensional encoding, we try to have higher dimensional sparse encoding.
### Denoising Autoencoder
### Probabilistic autoencoder

<img style="image-orientation:from-image;" src="{{site.url}}/{{site.baseurl}}/assets/autoencoder/prob_auto.jpg">

### Variational autoencoder
#### Generative network
The decoder `g` from probabilistic autoencoder is treated as generative model.

Objective:
$$ \underset{w}{\mathrm{max}} \sum_n log(Pr(x_n;W_f, W_g)) - c KL(Pr(h|x_n;W_f)\|\|N(h;0,1)) $$

We want distribution of `h` to be $N(h; 0, 1)$ as well as maximize overlap between the same distribution of probabilistic autoencoder: $N(h;x, \mu, \sigma^2)$.

### Variational Inference
We can quantify information a sentence or expression carries:

$$ I = -logP(x)  \text{, $x$ is an event}$$

Unlikely event carries more information.

Average of inormation is called entropy. Entropy = Expectation of information

$$ H = - \sum p(x)log(P(x)) $$

**KL Divergence**
$KL(p\|\|q)$ = measure of dissimilarity between two distribution, $p$, $q$. It is quite the following equation but not exact:
$$KL(p\|\|q) = -\sum q(x)log(q(x)) + \sum p(x)log(p(x))$$
It is KL divergence of $q$ wrt $p$.
So equation revised:
$$KL(p\|\|q) = -\sum p(x)log(q(x)) + \sum p(x)log(p(x)) = -\sum p(x)log\frac{q(x)}{p(x)}$$

Two inportant things of KL divergence:
- It is always $\ge 0$
- Not symmetric: $ KL(p\|\|q) \ne KL(q\|\|p) $. That's way it is called divergence not distance. Because distance should be symmetric, KL divergence is not.

![]({{site.url}}/{{site.baseurl}}/assets/autoencoder/var_infer.jpg)
Two approach for this intractable integral:
- Monte carlo
- Variational inference
Let's approximate p(z|x) as q(z) with known integral. This is done by: $min KL(q\|\|p) = - \sum q(x)log\frac{p(x)}{q(x)}$

Actually what we wanted is that: $ \min KL(q(z) \|\| p(z\|x)) = -\sum q(z)log(\frac{p(z\|x)}{q(z)}) = -\sum q(z) log(\frac{p(x,z)}{q(z)}) + log(p(x))$

Thus, $log(p(x)) = KL(q(z)\|\|p(z\|x)) + \sum q(z)log(\frac{p(x,z)}{q(z)})$

We have to maximize the right term of the function:

$$max \sum q(z)log(\frac{p(x,z)}{q(z)}) = E_{q(z)} log(P(x\|z) - KL(q(z)\|\|p(z))$$

### Variational Autoencoder
![]({{site.url}}/{{site.baseurl}}/assets/autoencoder/var_auto.jpg)