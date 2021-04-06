Dissimilarity is symmetric.
Dissimilarity of nominal data.

$ d(i, j) = \frac{p-m}{p} $

$ p = \text{total number of attributes} $

$ m = \text{total nnumber of similar attributes} $

$ sim(i, j) = 1 - d(i, j) $

- Every attributes should be normalized, standard range [0,1]

![]({{site.url}}/{{site.baseurl}}/assets/cluster_analysis/binary_attribute.png)

- Let's say we are counting similarity of two patients. Two patients have similar simptomps is more important than two patients have dissimilar simptomps. That's why $q$ is more important than $t$.

- For similarity, $q$ is important.

- For dissimilarity, $r, s$ are important.

- For symmetric data, dissimilarity between $i, j$: $ d(i, j) = \frac{r + s}{q+r+s+t} $
- For asymmetric data, dissimilarity between $i, j$: $ d(i, j) = \frac{r + s}{q+r+s} $, unmatched data is unimportant, thus ignored.
- Eucleadian distance, Manhattan distance, supremum distance (max of corresponding distance)

- Minkowski distance: $\sqrt[h]{\|x_{i1}-x_{j1}\|^h + ...}$

### For Ordinal

To mormalize rank of ordinal attribute:

$ z_{if} = \frac{r_{if}-1}{M_{if}-1} $

$ r_{if} = $ current rank

$ M_{if} = $ total ranks

### Mixed type

$ d(i, j) = \frac{\sum_{f=1}^P \delta_{ij}^{(f)} d_{ij}^{(f)}}{\sum_{f=1}^P \delta_{ij}^{(f)}} $

$ \delta $ is 0 if the measurement at that attribute is missing or assymteric binary.

![]({{site.url}}/{{site.baseurl}}/assets/cluster_analysis/multiple.png)


### Cosine similarity

$ sim(x, y) = \frac{x\cdot y}{\|x\|\|y\|} $

#### Tanimoto

Similar as cosine similarity except for all entry is binary:

$ S_T(A, B) = \frac{\|A\land B\|}{\|A \lor B\|} $

✅
⬜️
:x: