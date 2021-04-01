<link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/KaTeX/0.1.1/katex.min.css">
<script src="//cdnjs.cloudflare.com/ajax/libs/KaTeX/0.1.1/katex.min.js"></script>

## Boosting
## Adaboost

- First make prediction on M1, some data are predicted fine, some are not right. For those data for which we are not right, make them higher in probability for next round, M2. Make less probability for those who ware rightly predicted in previous round.

- $ error(M_i) = \sum_{j=1}^d w_j \times err(X_j) $

- $ err(X_j) $ is misclassification error of tuple $X_j$. It is 1 if misclassified, 0 otherwise.

- $w_j$ is the weight or probability of choosing tuple $j$.

- If classifier $M_i$ exceeds misclassification error $.5$, we abandon that classifier.


<object data="{{site.url}}/{{site.baseurl}}/assets/adaboost/adaboost.pdf" width="1000" height="1000"  type='application/pdf'/>

- Weight of classifier $M_i$'s vote is $log(\frac{1-error(M_i)}{error(M_i)})$

## Random forest

- every classifier in ensamble is a decision tree.

- But all the attributes are not used to create these trees.

 - F is the number of attributes to be used in each tree, F < acailable attributes


## Improving accuracy of class imbalanced data
 - Class imbalance problem is closely related to cost sensitive learning: cost of error per class is not equal.
 - To improve class accuracy:
    * Oversampling
    * Undersampling
    * Treshold moving
    * Ensamble technique

- Problem suggested: 8.7, 8.14, 8.15