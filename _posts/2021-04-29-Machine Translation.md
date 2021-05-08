### Noisy channel model

Let's say we are translating from l1 to l2.

$$ p(s2\|s1) = \frac{p((s2)p(s1\|s2))}{p(s1)} $$
$$ \arg\max_{s2} p(s2\|s1) = \arg\max_{s2} p(s2)p(s1\|s2) $$
$$ p(s2) = \text{  language model in l2} $$
$$ p(s1\|s2) = \text{  translation model} $$