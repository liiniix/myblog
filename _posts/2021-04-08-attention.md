> Attention network gave rise to new class of networks called transformer networks.

#### Attention in Computer Vision
- Attends to important part of the image

#### Attention in NLP
- Machine translation, long sentence
- Language modelling with **transformer networks**: predicts next word, word missing recovering

## Comparison

|Challenges with RNNs | Transformer networks |
|---------------------|----------------------|
|Long range dependencies|Facilitate long range dependencies|
|Gradient vanishing and explosion | No gradient vanishing and explosion |
|Large # of training steps | Fewer training steps |
|Recurrence prevents parallel execution | No recurrence facilitate parallel execution |

### Big picture
Mimics database operation: retrieval of value $v_i$ for a query $q$ based on key $k_i$:

$attention(q, \mathbf{k}, \mathbf{v}) = \sum_i similarity(q,k_i) \times v_i$

![]({{site.url}}/{{site.baseurl}}/assets/attention/attention_picture.png)

Let's say, we a a database with keys and values. We have a query too. We first align the query with the keys and return the corresponding value.

Weighted combination of values according to highly similar key, query pairs.

#### Similarity calculation

![]({{site.url}}/{{site.baseurl}}/assets/attention/sim_calc.png)

$S_i = similarity(q, k_i)$, where $similarity(q, k_i)$ can be on of following functions:

- $q^Tk_i$, a dot product
- $q^Tk_i/\sqrt{d}$, a scaled dot product, $d$ is dimentionality of each key
- $q^TWk_i$, generalized dot product
- $W_q^Tq + W_k^Tk_i$, additive similarity

> But the thing is $S_i$ can be negative or very large value. We should use softmax of all $S_i$ to squash them into $\[0,1\]$ and scale them

### Transformer

![]({{site.url}}/{{site.baseurl}}/assets/attention/transformer_block_diagram.png)
Figure need to be improved

> Nx means carried out N times

#### Multi-head attention

> Figure need to be added

#### Masked multi-head attention

Let's say we have a machine translation model from english to french. We are producing French sentence word by word. Its OK to attend previous word but not OK otherwise. We have to change attention mechanishm so that it doesn't depend on future words ( nullifying links or other).

$$ attention(Q, K, V) = softmax(\frac{Q^TK}{\sqrt{d_k}})V $$
$$ maskedAttention(Q, K, V) = softmax(\frac{Q^TK+M}{\sqrt{d_k}})V $$

$M$ is mask matrix of 0's and $-\infty$

### Normalization layer
It reduce steps gradient descent needs.

Weights of each layer depends on weights of other layers. When gradient descent stabalizes some layer and then make a change in other layers, previously stablized layer becomes unstable, it needs further tuning.

Layer normalization enforces all layers' weights to be of mean 0 and standard deviation 1 no matter what. So all layers output are on same scale even though specific weight may vary. Thus reducing gradient descept steps.

### Positional embedding
This mechanism doesn't require positional sense of words, words can be shuffled and same result found. But this is not always we want. Positional encoding enforce some positional sense.

![]({{site.url}}/{{site.baseurl}}/assets/attention/pos_emb.png)

Positional embedding should be concatenated with word embedding.