In previous classification tasks, data points were independent. Now we will be dealing with data points where they are dependent. Example is phoneme of speech in speech recognition task.

![]({{site.url}}/{{site.baseurl}}/assets/hmm/hmm.jpg)

Initial Distribution: $P(Y_t) = $ multinomial\\
Transition Distribution: $P(T_{t+1}\|Y_t) =$ multinomial\\
Emission Distribution: $P(X_t\|Y_t) =$ Gaussian(continuous)/multinomial(discrete)\\
Joint Distribution: $P(Y_{1...t}, X_{1...t}) = P(Y_1)\prod_{i=1}^{t-1} P(Y_{i+1}\|Y_i) \prod_{i=1}^t P(X_i\|Y_i)$