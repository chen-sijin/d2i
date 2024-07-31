## Problem 1

Let $\boldsymbol{X}=\left( X_1, X_2, \dots ,X_n \right) ^T$, then the mean value of this random vector is $\bar{\boldsymbol{X}}=\left( \bar{X}_1, \bar{X}_2, \dots ,\bar{X}_n \right) ^T$. The covariance matrix of $\boldsymbol{X}$ is calculated by:
$$
\boldsymbol{C}_X=\left< \left( X-\bar{X} \right) \left( X-\bar{X} \right) ^T \right>
$$
Let $\boldsymbol{M}$ be the constant matrix, then :
$$
\boldsymbol{Y}=\boldsymbol{M}\cdot \boldsymbol{X}
$$
Then, the covariance of $\boldsymbol{Y}$ is calculated by:
$$
\begin{align}
\begin{split}
\boldsymbol{C}_Y&=\left< \left( Y-\bar{Y} \right) \left( Y-\bar{Y} \right) ^T \right> 
\\
&=\left< \left( MX-M\bar{X} \right) \left( MX-M\bar{X} \right) ^T \right> 
\\
&=\left< M\left( X-\bar{X} \right) \left( X-\bar{X} \right) ^TM^T \right> 
\\
&=M\left< \left( X-\bar{X} \right) \left( X-\bar{X} \right) ^T \right> M^T
\\
&=MC_XM^T
\end{split}
\end{align}
$$




## Problem 2

-----

### Method 1

The logarithm of the PDF is :
$$
\ln p=-\frac{n}{2}\ln \left| 2\pi \boldsymbol{C} \right|-\frac{1}{2}\left[ \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) \right] 
$$


Then, the first order derivative w.r.t $\theta$ is :
$$
\begin{align}

\begin{split}

\frac{\partial \ln p}{\partial \theta _i}=&\frac{1}{2}\left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) \right] 
\\
&+\frac{1}{2}\left[ \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _{\boldsymbol{i}}} \right) \right] 

\end{split}
\end{align}
$$
 Then, the second derivative is :
$$
\begin{align}
\begin{split}
\frac{\partial ^2\ln p}{\partial \theta _i\partial \theta _j}&=\frac{1}{2}\left[ \left( \frac{\partial ^2\boldsymbol{\mu }}{\partial \theta _i\partial \theta _j} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) \right] 
\\
&-\frac{1}{2}\left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _j} \right) \right] 
\\
&-\frac{1}{2}\left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _j} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) \right] 
\\
&+\frac{1}{2}\left[ \left( \boldsymbol{x}-\boldsymbol{\mu }\left( \boldsymbol{\theta }_{true} \right) \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial ^2\boldsymbol{\mu }}{\partial \theta _i\partial \theta _j} \right) \right] 
\end{split}
\end{align}
$$
Then, the $i, j-th$​ element in Fisher Matrix is the expectation value of the above equation:
$$
F_{ij}=-\left< \frac{\partial ^2\ln p}{\partial \theta _i\partial \theta _j} \right> =0-\frac{1}{2}\left< \left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _j} \right) \right] \right> -\frac{1}{2}\left< \left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _j} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) \right] \right> +0
$$
Since this two terms are symmetric, we then have:
$$
F_{ij}=-\left< \frac{\partial ^2\ln p}{\partial \theta _i\partial \theta _j} \right> =-\left< \left[ \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _i} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }}{\partial \theta _j} \right) \right] \right> 
$$


-----

### Method 2

Some properties that would be used in calculating the gradient of matrix:

> $$
> x=\mathrm{tr}\left( x \right) 
> \\
> \mathrm{tr}\left( c_1\boldsymbol{A}+c_2\boldsymbol{B} \right) =c_1\mathrm{tr}\left( \boldsymbol{A} \right) +c_2\mathrm{tr}\left( \boldsymbol{B} \right) 
> \\
> \mathrm{tr}\left( \boldsymbol{A} \right) =\mathrm{tr}\left( \boldsymbol{A}^T \right) 
> \\
> \left< \boldsymbol{A},\boldsymbol{B} \right> =\mathrm{tr}\left( \boldsymbol{A}^T\boldsymbol{B} \right) 
> \\
> \mathrm{tr}\left( \boldsymbol{AB} \right) =\mathrm{tr}\left( \boldsymbol{BA} \right) 
> \\
> \mathrm{tr}\left( \boldsymbol{ABC} \right) =\mathrm{tr}\left( \boldsymbol{BCA} \right) =\mathrm{tr}\left( \boldsymbol{CAB} \right) 
> \\
> \mathrm{d}\left( \boldsymbol{F}\left( \boldsymbol{X} \right) \boldsymbol{G}\left( \boldsymbol{X} \right) \right) =\mathrm{d}\left( \boldsymbol{F}\left( \boldsymbol{X} \right) \right) \boldsymbol{G}\left( \boldsymbol{X} \right) +\boldsymbol{F}\left( \boldsymbol{X} \right) \mathrm{d}\left( \boldsymbol{G}\left( \boldsymbol{X} \right) \right) 
> \\
> \mathrm{d}{\boldsymbol{F}^T}_{p\times q}\left( \boldsymbol{X} \right) =\left( \mathrm{d}\boldsymbol{F}_{p\times q}\left( \boldsymbol{X} \right) \right) ^T
> $$
>
> 



> And the most important one:
>$$
> \mathrm{tr}\left( \mathrm{d}\boldsymbol{F}_{p\times q} \right) =\mathrm{tr}\left( \left( \frac{\mathrm{d}\boldsymbol{F}_{p\times q}}{\mathrm{d}\boldsymbol{X}} \right) ^T\mathrm{d}\boldsymbol{X} \right) 
> $$
> So, the derivative of the matrix is then the transpose of the left part. 

$$
\begin{align}
\begin{split}
\mathrm{tr}\left( \mathrm{d}\ln p \right) &=\mathrm{tr}\left( \frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] +\frac{1}{2}\left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) \right) 
\\
&=\mathrm{tr}\left( \frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] \right) +\mathrm{tr}\left( \frac{1}{2}\left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) \right) 
\\
&=\frac{1}{2}\mathrm{tr}\left( \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] ^T\cdot \left( \boldsymbol{C}^{-1} \right) ^T\cdot \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) \right) +\frac{1}{2}\mathrm{tr}\left( \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right) \right) 
\end{split}
\end{align}
$$

So, the gradient of $\ln p$ is :
$$
\frac{\mathrm{d}\ln p}{\mathrm{d}\boldsymbol{\theta }}=\frac{1}{2}\left( \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \left( \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right) \cdot \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] \right)
$$
then, take the second derivative of this :
$$
\begin{align}
\begin{split}
\mathrm{d}\left( \frac{\mathrm{d}\ln p}{\mathrm{d}\boldsymbol{\theta }} \right) &=\frac{1}{2}\mathrm{d}\left( \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T \right) \cdot \left[ \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right] \cdot \left[ \boldsymbol{X}-\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right] 
\\
&-\frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \left[ \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right] \cdot \mathrm{d}\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) 

\end{split}
\end{align}
$$
Then take the expectation value of this equation, the first term is $0$, so, we have:
$$
\begin{align}
\begin{split}
\left< \mathrm{d}\left( \frac{\mathrm{d}\ln p}{\mathrm{d}\boldsymbol{\theta }} \right) \right> &=\left< -\frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \left[ \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right] \cdot \mathrm{d}\boldsymbol{\mu }\left( \boldsymbol{\theta } \right) \right> 
\\
&=\left< -\frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \left[ \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right] \cdot \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }}\mathrm{d}\boldsymbol{\theta } \right> 
\end{split}
\end{align}
$$
Therefore:
$$
\left< \mathrm{d}\left( \frac{\mathrm{d}^2\ln p}{\mathrm{d}\boldsymbol{\theta }^2} \right) \right> =\left< -\frac{1}{2}\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \left[ \left( \boldsymbol{C}^{-1} \right) ^T+\boldsymbol{C}^{-1} \right] \cdot \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right> 
$$
Since the covariance matrix is symmetric, the final result is then:
$$
\left< \frac{\mathrm{d}^2\ln p}{\mathrm{d}\boldsymbol{\theta }^2}  \right> =-\left< \left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \boldsymbol{\theta }} \right>
$$
Then, we have:
$$
\boldsymbol{F}_{ij}=\left( \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \theta _i} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \frac{\partial \boldsymbol{\mu }\left( \boldsymbol{\theta } \right)}{\partial \theta _j}
$$


----

When $n=1=m$, 
$$
F=\left( \frac{\partial \mu}{\partial \theta} \right) ^2\frac{1}{\sigma ^2}
$$
So, higher value of F means that is contains more information. There are two explanations:

1. when the derivative is large, that means $\mu$ is sensitive to $\theta$, a small deviation from the true value could lead to a big difference. It depicts the robustness of $\boldsymbol{\mu}$ with respect to $\boldsymbol{\theta}$
2. when the $\sigma$ variance is small, that means the distribution is more localized around the mean value. It tells how accuracy the data is.



## Problem 3

Take the derivative of $\chi^2\left( a\right)$ :
$$
\begin{align}
\begin{split}
\chi ^2\left( a \right) &=\left[ \boldsymbol{x}-a\boldsymbol{v} \right] ^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] 
\\
\mathrm{d}\left( \chi ^2\left( a \right) \right) &=\left[ -\boldsymbol{v}\mathrm{d}a \right] ^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] +\left[ \boldsymbol{x}-a\boldsymbol{v} \right] ^T\boldsymbol{C}^{-1}\left[ -\boldsymbol{v}\mathrm{d}a \right] 
\\
&=\left\{ \left[ -\boldsymbol{v} \right] ^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] \mathrm{d}a+\left[ \boldsymbol{x}-a\boldsymbol{v} \right] ^T\boldsymbol{C}^{-1}\left[ -\boldsymbol{v} \right] \mathrm{d}a \right\} 
\\
&=-2\left[ \boldsymbol{v}^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] \right] da
\\
\frac{\mathrm{d}\left( \chi ^2\left( a \right) \right)}{\mathrm{d}a}&=-2\left[ \boldsymbol{v}^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] \right] 

\end{split}
\end{align}
$$
Since the transpose of a scalar is still itself, we can combine the two term in the third line.



To get the $a_{best}$ that makes the $\chi^2$ minimized, make the derivative $0$ :
$$
\begin{align}
\begin{split}
\frac{\mathrm{d}\left( \chi ^2\left( a \right) \right)}{\mathrm{d}a}&=-2\left[ \boldsymbol{v}^T\boldsymbol{C}^{-1}\left[ \boldsymbol{x}-a\boldsymbol{v} \right] \right] =0
\\
a&=\frac{\boldsymbol{v}^T\boldsymbol{C}^{-1}\boldsymbol{x}}{\boldsymbol{v}^T\boldsymbol{C}^{-1}\boldsymbol{v}}
\end{split}
\end{align}
$$


---

For a random variable $A_{best}$, its variance is :
$$
\begin{align}
\begin{split}
A_{best}&=\frac{\boldsymbol{X}^T\boldsymbol{C}^{-1}\boldsymbol{V}}{\boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V}}
\\
\mathrm{Cov}\left( A_{best} \right) &=\mathrm{Cov}\left( \frac{\boldsymbol{X}^T\boldsymbol{C}^{-1}\boldsymbol{V}}{\boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V}} \right) 
\\
&=\frac{1}{\left( \boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V} \right) ^2}\mathrm{Cov}\left( \boldsymbol{X}^T\boldsymbol{C}^{-1}\boldsymbol{V} \right) 
\\
&=\frac{1}{\left( \boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V} \right) ^2}\mathrm{Cov}\left( \boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{X} \right) 
\\
&=\frac{1}{\left( \boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V} \right) ^2}\left( \boldsymbol{V}^T\boldsymbol{C}^{-1} \right) \mathrm{Cov}\left( \boldsymbol{X} \right) \left( \boldsymbol{V}^T\boldsymbol{C}^{-1} \right) ^T
\\
&=\frac{1}{\left( \boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V} \right) ^2}\left( \boldsymbol{V}^T\boldsymbol{C}^{-1} \right) \boldsymbol{CC}^{-1}\boldsymbol{V}
\\
&=\frac{1}{\boldsymbol{V}^T\boldsymbol{C}^{-1}\boldsymbol{V}}
\end{split}
\end{align}
$$


So, the variance of $A_{best}$ is then $\mathrm{Var}\left( A_{best} \right) =\boldsymbol{V}^{-1}\boldsymbol{C}\left( \boldsymbol{V}^T \right) ^{-1}$ .



Fisher matrix for the gaussian distribution is :
$$
\boldsymbol{F}=\left( \frac{\partial \boldsymbol{\mu }\left( \vec{\theta} \right)}{\partial \vec{\theta}} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial \boldsymbol{\mu }\left( \vec{\theta} \right)}{\partial \vec{\theta}} \right) 
$$
Here, the variable is $a_{best}$, so the Fisher matrix becomes:
$$
\begin{align}
\begin{split}
\boldsymbol{F}&=\left( \frac{\partial a\boldsymbol{v}}{\partial a} \right) ^T\cdot \boldsymbol{C}^{-1}\cdot \left( \frac{\partial a\boldsymbol{v}}{\partial a} \right) 
\\
&=\boldsymbol{v}^T\cdot \boldsymbol{C}^{-1}\cdot \boldsymbol{v}
\end{split}
\end{align}
$$
So, the inverse of Fisher matrix is :
$$
\boldsymbol{F}^{-1}=\boldsymbol{V}^{-1}\cdot \boldsymbol{C}\cdot \left( \boldsymbol{V}^T \right) ^{-1}
$$
So, this is the same as the inverse of Fisher matrix. 



> Cramer-Rao-bound :
> $$
> \mathrm{var}\left( \hat{\theta} \right) \ge \frac{1}{F\left( \theta \right)}
> $$
> The precision of any unbiased estimation is at most the Fisher information matrix.



The estimator is statistically efficient, making the best use of the available information in estimating the parameter of interest. This is the best estimator.
