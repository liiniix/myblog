## Matrix Multiplication
$$
\begin{bmatrix}
\alpha & (1-\alpha)
\end{bmatrix}
\begin{bmatrix}
\theta & (1-\theta)\\
\beta & (1-\beta)
\end{bmatrix} = y^T
$$

If $x^T\mathbf{G} = y^T$ and $\sum_i x_i = 1$ and $\sum_j \mathbf{G_{ij}} = 1, \forall i$, then $\sum_j y_j =1$.

Proof:

$$y_j = \sum_i x_i \mathbf{G_{ij}}$$
So,
$$\sum_j y_j = \sum_j \sum_i x_i \mathbf{G_{ij}}$$

$$= \sum_i \sum_j x_i \mathbf{G_{ij}}$$

$$= \sum_i x_i \sum_j \mathbf{G_{ij}}$$
$$ = 1 $$

> If we have a probability vector, and we multiply it with conditional probability matrix, we end up having a vector adding up 1

## Eigenvalue and Eigenvector
We have a matrix
$$
A =
\begin{bmatrix}
\theta & (1-\theta)\\
\beta & (1-\beta)
\end{bmatrix}
$$

I want to come up with $\mathbf{A}x = \lambda x$ which is equivalent to $x^T\mathbf{A} = \lambda x^T$

$\lambda$ is eigenvalue and $x^T$ is called left eigenvector and $x$ is called right eigenvector.

We can have $\lambda$ and $x$ by analyzing this: $(\mathbf{A} - \lambda I) = 0$

Null-space of $A-\lambda I$ will be $x$ and $det(A-\lambda I)$ will give $\lambda$.

Its proven that $\lambda = 1$ is always a case for $\lambda$ for any stocastic matrix.

For $\lambda = 1$, we have right eigenvector
$$ x = 
\begin{bmatrix}
1\\
1
\end{bmatrix}
$$
and right eigenvector,
$$ x = 
\begin{bmatrix}
\frac{\alpha}{\alpha + \beta} & \frac{\beta}{\alpha + \beta}
\end{bmatrix}
$$, this is a probability vector.

## Eigen(Value , Vector) in Google Matrix

We took our Google matrix $G$ and initian vector $\pi_0$

We multiplied it $m$ times, $\pi_0^T G^m = \pi_m^T$.

Let $x_i^TG = \lambda_i x_i^T$.
Assume $G_{N\times N}$ has $N$ dintinct eigenvalues.

Suppose $x_i$ form a basis. $\pi_0 = \sum_i^N c_ix_i$

Now
$$\pi_0^TG = \sum c_ix_i^TG = \sum c_i\lambda_ix_i^T = \pi_1^T$$

$$\pi_1^TG = \sum c_i\lambda_ix_i^TG = \sum c_i\lambda_i^2x_i^T$$

...

$$\pi_0^TG^m = \sum c_i\lambda_i^mx_i^T = c_1\lambda_1^mx_1T +c2\lambda_2^mx_2 + \dots$$


Let's order $\lambda$'s this way: $\lambda_1 > \lambda_2 > \lambda_3 \dots$

So previous term will be approximately equal to the first term.

## Decomposition
$$
A \begin{bmatrix}
x_1 & x_2 & \dots & x_m
\end{bmatrix} = 
\begin{bmatrix}
x_1 & x_2 & \dots & x_m
\end{bmatrix}
\begin{bmatrix}
\lambda_1 & 0 &\dots\\
0 & \lambda_2 & \dots\\
\dots\\
&\dots&\lambda_m
\end{bmatrix}
$$

$$ AX = X \Lambda$$

$$ A = X\Lambda X^{-1} $$

If $A=A^T$ ie is symmetric, $A=X\Lambda X^T$

Because $X$ is orthoginal, $X^{-1}=X^T$.

## Singular Value Decomposition
$A=X\Lambda X^T$ if $A=A^T$

$$ A = 
\begin{bmatrix}
x_1 & x_2 & \dots\\
\end{bmatrix}
\begin{bmatrix}
\lambda_1 & 0 &\dots\\
0 & \lambda_2 & \dots\\
\dots\\
&\dots&\lambda_m
\end{bmatrix}
\begin{bmatrix}
x_1^T\\
x_2^T\\
\dots\\
\end{bmatrix}
$$
$$
= \lambda_1x_1x^T_1 + \lambda_2x_2x_2^T+\dots
$$

## Vector norm
$x \in \mathcal{R}^{m\times 1}$

$ \|\|x\|\|_2 = \sqrt{x_1^2 + \dots + x_m^2} = \sqrt{x^Tx}$

If $Q$ is an $m\times m$ orthogonal matrix: $Q^T = Q^{-1}$: $\|\|Qx\|\|_2 = \sqrt{(Qx)^T(Qx)} = \sqrt{x^TQ^TQx} = \sqrt{x^Tx} = \|\|x\|\|_2$

So $Q$ rotates $x$, doesn't change its length.

## Singular Value Decomposition


$$ A = U\Sigma V^T$$

$A_{m\times n}$

$U_{m\times n}$, orthonormal columns

$\Sigma_{n\times n}$, diagonal with positive entries, singular values

$V_{n\times n}$, orthonormal columns and rows

### How to compute SVD
$A^TA = V\Sigma^2V^T$

$AA^T = U\Sigma^2U^T$

The nonzero singular values of A are the positive square roots of the nonzero eigenvalues of $A^TA$ or $AA^T$