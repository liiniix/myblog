### Tagging Problem
#### Parts-of-Speech Tagging
Ambiguity is the problem. `Profit` can be a noun or verb. A word can take 2/3 POS.

#### Named Entity Recognition
Identify `company/location/person` from sentence.

### Two types of constraints
- Local: `can` is more likely to be a verb than a noun
- Contexual: noun is more likely to follow verb than a determiner
- Sometimes constaints can conflict: `The trash can is in the garbage`

## Supervised learning problem
### Settings
- Traing examples $x^{(i)}, y^{(i)}$ for $i = 0, \dots , m$
- Task is to learn a function $f: x \to y$
$$ x^{(1)} = \text{ The dog laughs} $$
$$ y^{(1)} = \text{ DT NN VB} $$

### Method 1: Conditional Model
- learn distribution $p(y\|x)$
- define $f(x) = \arg\max_y p(y\|x)$

### Method 2: Generative Model
- learn the distribution $p(x, y)$
- Often we have $p(x,y) = p(y) p(x\|y)$
- $$ f(x) = \arg\max_y p(y\|x) = \arg\max_y \frac{p(y)p(x\|y)}{p(x)} = \arg\max_y p(y)p(x\|y) $$

### Method 3: HMM
- learn the distribution $p(x_1,\dots,x_n,y_1,\dots,y_n)$
- $ \arg\max_{y_1,\dots,y_n} p(x_1,\dots,x_n,y_1,\dots,y_n)$

$$ V = \text{ set of vocabulary} $$
$$ S = \text{ set of tags} $$
<img style="image-orientation:from-image;" src="{{site.url}}/{{site.baseurl}}/assets/tagging/hmm.jpg">
$$ p(x_1\dots x_n, y_1\dots y_n) = \prod_{i=1}^{n+1} q(y_i\|y_{i-2}, y_{i-1}) \prod_{i=1}^n e(x_i\|y_i) $$

$$y_{n+1} = \text{STOP}$$

#### Parameter Estimation
### Pros and Cons
- very simple to train
- perform relatively well
- main difficulty is modeling $p(word\|tag)$