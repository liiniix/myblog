### Applications
- Machine translation
- Information extraction
- Text summerization
- Dialogue system
- Basic problems
    - Tagging
        - Parts-of-Speech tagging
        - Named-Entity tagging
    - Parsing

### Why NLP is hard?
- Ambiguity in so many levels

### Language modeling problem

$$ \mathcal{V} = \text{ Finite vocabulary set} $$
$$ \mathcal{V} = \\{the, a, man, \dots\\}$$
$$ \mathcal{V}^{\dagger} = \text{ Finite set of all possible strings} $$
$$ \mathcal{V}^{\dagger} = \\{ \text{ the STOP}, \text{a STOP}, \text{the fan saw Beckham} \\} $$

We have to provide probability $p$ to all of the sentences in $\mathcal{V}^{\dagger}$ so that:
    $$ \forall x \in \mathcal{V}^{\dagger} \sum_{\mathcal{V}^{\dagger}} p(x) = 1, p(x) \ge 0 $$


#### Naive method
$$ N = \text{ # training sentences} $$
$$ c(x_1, x_2, x_3, \dots, x_n) = \text{# occourances of sentence $x_1,\dots, x_n$} $$
$$ p(x_1, x_2, \dots, x_n) = \frac{c(x_1, x_2, \dots, x_n)}{N} $$

#### Deficiencies
- Assigning probability 0 for a new sentence.
- No ability to generalize in new sentences

### First Order Markov Process
$$ P(X_1 = x_1, X_2 = x_2, \dots , X_n = x_n) = P(X_1 = x_1) \prod_{i = 2}^n P(X_i = x_i \| X_1 = x_1, \dots , X_{i-1} = x_{i-1}) $$
$$ = P(X_1 = x_1) \prod_{i = 2}^n P(X_i = x_i \| X_{i-1} = x_{i-1}) $$

### Trigram Example
$$p(\text{the dog barks STOP}) = q(\text{the|*, *})q(\text{dog | *, the})q(\text{barks | the, dog})q(\text{STOP | dog, barks})$$

### Maximum Liklihood Estimate
$$q(w_i \| w_{i-2}, w_{i-1}) = \frac{Count(w_{i-2}, w_{i-1}, w_i)}{Count(w_{i-2}, w_{i-1})}$$

$$ q(laughs \| the, dog) = \frac{Count(the, dog, laughs)}{Count(the, dog)} $$

**Problem:**
- For vocabulary size $N$, there are $N^3$ parameters
- Counts on numerator can be 0
- Counts on denominator can also be 0

### Evaluating language models: perplexity
We have $m$ sentences
$$s_1, s_2, \dots , s_m$$
We want to maximize $\prod_{i=1}^m p(s_i)$, or conveniently log probability: $log \prod_{i=1}^m p(s_i)$

$$ log \prod_{i=1}^m p(s_i) = \prod_{i=1}^m log p(s_i) $$

Finally:
    $$ \text{Perplexity } = 2^{-l}, \text{ where } l = \frac{1}{M} \sum_{i=1}^m logp(s_i) $$

### Estimation techniques
#### Linear interpolation

Trigram ML estimate: $$q_{ML}(w_i \| w_{i-2}, w_{i-1}) = \frac{Count(w_{i-2}, w_{i-1}, w_i)}{Count(w_{i-2}, w_{i-1})}$$

Bigram ML estimate: $$q_{ML}(w_i \| w_{i-1}) = \frac{Count(w_{i-1}, w_i)}{Count(w_{i-1})}$$

Unigram ML estimate: $$q_{ML}(w_i) = \frac{Count(w_i)}{Count()}$$

Weighted average of three:
$$q(w_i \| w_{i-2}, w_{i-1}) = \lambda_1 q_{ML}(w_i \| w_{i-2}, w_{i-1}) + \lambda_2 q_{ML}(w_i \| w_{i-1}) + \lambda_3 q_{ML}(w_i)$$
$$\lambda_1 + \lambda_2+ \lambda_3 = 1, \lambda_i \ge 0$$
#### Discounting method

$$Count^*(x) = Count(x) - .5$$


Define two sets:
$$\mathcal{A}(w_{i-1}) = \\{w: Counts(w_{i-1}, w) > 0\\}$$
$$\mathcal{B}(w_{i-1}) = \\{w: Counts(w_{i-1}, w) = 0\\}$$


Missing probability mass: $$\alpha(w_{i-1}) = 1 - \sum_w \frac{Count^*(w_{i-1}, w)}{Count(w_{i-1})}$$


$$
q_{BO} = \begin{cases}
\frac{Count^*(w_{i-1}, w)}{Count(w_{i-1})}, \text{ if }w\in \mathcal{A}(w_{i-1})\\
\end{cases}
$$


### Tagging Problem
#### Parts-of-Speech Tagging
Ambiguity is the problem. `Profit` can be a noun or verb. A word can take 2/3 POS.

#### Named Entity Recognition
Identify `company/location/person` from sentence.