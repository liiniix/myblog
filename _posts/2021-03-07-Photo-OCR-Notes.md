# Support Vector Machines
## Large Margin Classification
### Optimization Objective
* We will redefine cost function.\\
For $ y=1 $ , ![states]({{site.url}}/{{site.baseurl}}/assets/coursera_ml/cost1.png)\\
For $ y=0 $ , ![states]({{site.url}}/{{site.baseurl}}/assets/coursera_ml/cost0.png)

$$ C \sum_{i=0}^m y^{(i)} cost_1(\theta^T x) + (1-y^{(i)}) cost_0(\theta^T x) + \frac{1}{2} \sum_{j=1}^m \theta_j^2$$

* We can shortnote previous equation with $ CA + B $
* SVM doesn't give output in probability, it gives 0 or 1 instead.
$$ h_\theta = 1 \text{ if } \theta^Tx \ge 0 , 0 \text{ otherwise} $$

### Large Margin Classification

- If y = 1, we want $\theta^Tx \ge 1$
- if y = 0, we want $\theta^Tx \le -1$
- We get a very interesting decision boundary when we satisfy previous two constraints. The decision boundary will be the one that have largest distance from both classes.
- SVM is also called large margin classifier.

### Kernels
- To classify classes not separable linearly, we have to use nonlinear decision boundary: 
predict 1 if $\theta_0 + \theta_1x_1 + \theta_2x2 + \theta_3x_1x_2 + \theta_4x_1^2 ...  \ge 0$
- We are producing new features using our base features, in this case we are producing polynomial features with base features $x_1, x_2$.
- This is called polynomial kernel.

- Now see gaussian kernel, we are given some landmarks $l^{(1)}, l^{(2)}, l^{(3)}$. We have to capture different features based on proximity to the landmarks.
$ similarity(x, l^{(1)}) = e^{-\frac{||x-l^{(1)}||}{2\sigma^2}} = k(l^{(1)}, x)$
Similarly with other landmarks.

### SVMs in practice
- 'No kernel' means linear kernel
- In order to SVM work well, perform feature scaling
- Kernels should satisfy "Mercer's Theorem"
- Several other kernels like polynomial kernel, string, chi-square, histogram intersection kernel etc.
- If number of features is larger than training examples, use logistic regression or SVM without kernel.
- If number of feature is small and number of training examples is intermediate, use SVM with Gaussian kernel. 

# Sliding Window
<hr>
First component of Photo OCR phipeline is text detection. But text has different spect ratio in different photos.

> Spect Ratio: Height Width ratio

What Sliding Window algorithm says:
Take a predetermined size of rectangular patch, slide it over by a little bit throughout the image. Shift parameter size is called `step size` or `stride`. Then the image patch will go to the classifier.

In our Photo OCR case, we do the same as sliding window algorithm, make a heatmap like representaion to exploid the region with texts.

Second component of Photo OCR pipeline is character segmentation. We can use supervised classifier to detect whether there is a split between two characters.

Artificial Data Systhesis
<hr>

* Take characters from different fonts and attach these in any random background, maybe with affine, rotate, shear.

* Systhesize data with distortion

Ceiling Analysis: What part to emphasize
<hr>
Photo OCR pipeline
`Image-->Text detection-->Character Segmentation-->Character recognition`

Which component worth most time?
In isolation, which part of the pipeline is most responsible for the overall accuracy of the pipeline?