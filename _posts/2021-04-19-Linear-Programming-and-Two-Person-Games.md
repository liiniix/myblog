Why it is called Linear Programming?
We are optimizing a linear cost function subject to linear constraints.

$$ \text{min } c^Tx = c_1x_1 + \dots + c_nx_n $$
$$ c \text{ = cost vector} $$
$$ \text{constraints on x: } A_{m \times n} x_{n\times 1} = b , m < n$$
$$ x \ge 0, \text{ means } x_1 \ge 0, \dots, x_n \ge 0 $$
$$ \text{"This is called feasible set of x's"} $$

Two types of algo:
- Simplex method, older and well-established. $corner \to next\\_corner \to next\\_corner$

### Duality LP for $y_1,\dots,y_m$
twin problem
$$ \text{max } b^Ty \text{, b is from primal problem}$$ 
$$ A^Ty = c , \text{ c is constraint vector from primal problem}$$

> Weak duality, $b^Ty \le c^Tx$, for any $x, y$ feasible

> Strong duality/duality, $b^Ty^* = c^Tx$

In duality, $$\text{max min = min max}$$

### max flow = min cut

$$\text{any flow } \le \text{ capacity of any cut}$$

![]({{site.url}}/{{site.baseurl}}/assets/two_person/max_flow.jpg)

### Two person's game
Zero-sum: What x pays, goes to y