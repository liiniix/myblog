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