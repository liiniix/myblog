Trigram model uses previous tree words as context: $q(w_i='model'\|w_{i-2}='any', w_{i-1}='statistical')$

But other information can be useful too: $q(w_i='model'\|w_{i-2}='any', w_{i-1}='statistical', author = 'Chomsky',...)$

## General setting
$$ x = \text{ input} $$
$$ y = \text{ level} $$
$$ \text{Aim to provide } p(y\|x) $$

## Language Modeling
$$ x = \text{ history } w_1...x_{i-1} $$
$$ y = \text{ next word } w_i $$
$$ f_k(x, y) = \text{ k-th fearure of } x, y $$
$$ \text{Example: } f_{N(u, v, w)} = \begin{cases}
1 \text{ if } x_{i-2} = u, x_{i-1} = v, x_i = w\\
0 \text{ otherwisw}
\end{cases}$$

## POS-tagging
$$ x = \text{ history } \<t_1,...,t_{i-1}, w_1,..., w_n, i\>$$
$$ y = \text{ tag } NN, Vi, Vt,... $$
$$ f_k(x, y) = \text{ feature} $$
$$ \text{Example: } f_2(x, y) = \begin{cases}
1 \text{ if $w_i$ ends with `ing` and $ y=VBG $}\\
0 \text{ otherwise}
\end{cases}$$

## Parameter Vector
- Given features $f_k(x, y)$, define a parameter vector $v$
- Then $(x, y)$ pairs will be mapped into a score $v\cdot f(x,y)$
- Each possible $y$ gets different score, $$v\cdot f(x, model) = 9, v\cdot f(x, is) = 1.5$$

$$p(y\|x; v) = \frac{e^{v\cdot f(x,y)}}{\sum_{y'\in Y} e^{v\cdot f(x,y')}}$$
$$logp(y\|x;v) = v\cdot f(x,y) - log\sum_{y'\in Y}e^{v\cdot f(x,y')}$$