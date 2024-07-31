# Homework1

## Problem 1

For a uniform distribution, the expectation value is:
$$
\left< X \right> =\int_a^b{X\frac{1}{b-a}dX}=\frac{a+b}{2}=1
$$
The variance in this case is:
$$
\begin{align}
    \begin{split}
        V\left( X \right) &=\left< X^2 \right> -\left< X \right> ^2
\\
&=\int_a^b{X^2\frac{1}{b-a}dX}-\left< X \right> ^2
\\
&=\frac{1}{3}\left( a^2+ab+b^2 \right) -\left< X \right> ^2=0.16
    \end{split}
\end{align}
$$
So, we can calculate:
$$
\begin{align}
    \begin{split}
        \begin{cases}
	a+b=2\\
	b>a\\
	a^2+ab+b^2=3.48\\
\end{cases}\rightarrow \begin{cases}
	a=1-\frac{2\sqrt{3}}{5}\\
	b=1+\frac{2\sqrt{3}}{5}\\
\end{cases}
    \end{split}
\end{align}
$$




----

## Problem 2

$$
\begin{align}
    \begin{split}
        \phi \left( \lambda \right) =\left< e^{\lambda x} \right> &=\left< \sum_{n=0}^{\infty}{\frac{\left( \lambda X \right) ^n}{n!}} \right> 
\\
&=\sum_{n=0}^{\infty}{\frac{\lambda ^n}{n!}\left< X^n \right>}
    \end{split}
\end{align}
$$

For a variable with Gaussian distribution, the MGF could be calculated by:
$$
\begin{align}
    \begin{split}
        \phi \left( \lambda |\mu ,\sigma \right) =\frac{1}{\sqrt{2\pi \sigma ^2}}\int_{-\infty}^{\infty}{e^{\lambda x}e^{-\frac{\left( x-\mu \right)}{2\sigma ^2}}dx}
    \end{split}
\end{align}
$$
For the index term:
$$
\begin{align}
    \begin{split}
    -\frac{\left( x-\mu \right) ^2}{2\sigma ^2}+\lambda x&=-\frac{1}{2\sigma ^2}\left( x^2-2\mu x+\mu ^2 \right) +\lambda x
\\
&=-\frac{1}{2\sigma ^2}x^2+\frac{\mu}{\sigma ^2}x-\frac{\mu ^2}{2\sigma ^2}+\lambda x
\\
&=-\frac{1}{2\sigma ^2}x^2+\left( \frac{\mu}{\sigma ^2}+\lambda \right) x-\frac{\mu ^2}{2\sigma ^2}
\\
&=-\frac{1}{2\sigma ^2}\left[ x^2-\left( 2\mu +2\lambda \sigma ^2 \right) x+\left( \mu +\lambda \sigma ^2 \right) ^2 \right] +\frac{1}{2\sigma ^2}\left( \mu +\lambda \sigma ^2 \right) ^2-\frac{\mu ^2}{2\sigma ^2}
    \end{split}
\end{align}
$$
So, the final integral becomes:
$$
\begin{align}
    \begin{split}
        \phi \left( \lambda |\mu ,\sigma \right) &=\frac{1}{\sqrt{2\pi \sigma ^2}}\int_{-\infty}^{\infty}{e^{\lambda x}e^{-\frac{\left( x-\mu \right)}{2\sigma ^2}}dx}
\\
&=e^{\frac{1}{2\sigma ^2}\left( \mu +\lambda \sigma ^2 \right) ^2-\frac{\mu ^2}{2\sigma ^2}}=\exp \left( \mu \lambda +\frac{1}{2}\sigma ^2\lambda ^2 \right) 
    \end{split}
\end{align}
$$



## Problem 3



![1](D:\Munich\Study\Semester 4\From Data to Insights\Tutorial\Tutorial01\1.png)

![2](D:\Munich\Study\Semester 4\From Data to Insights\Tutorial\Tutorial01\2.png)

![3](D:\Munich\Study\Semester 4\From Data to Insights\Tutorial\Tutorial01\3.png)









## Problem 4

Suppose $\left< \hat{X} \right> =\mu , \left< \left( \hat{X}-\mu \right) ^2 \right> =\sigma ^2$, and $f\left(\hat{X}\right)$ is any function. Suppose $\hat{X}\approx \mu$, then we have:
$$
\begin{align}
    \begin{split}
        f\left( \hat{X} \right) &=f\left( \mu \right) +f'\left( \mu \right) \left( \hat{X}-\mu \right) +\frac{f''\left( \mu \right)}{2!}\left( \hat{X}-\mu \right) ^2+\dots +\frac{f^{\left( n \right)}\left( \mu \right)}{n!}\left( \hat{X}-\mu \right) ^n
\\
\left< f\left( \hat{X} \right) \right> &=f\left( \mu \right) +f'\left( \mu \right) \left< \left( \hat{X}-\mu \right) \right> +\frac{f''\left( \mu \right)}{2!}\left< \left( \hat{X}-\mu \right) ^2 \right> +\dots +\frac{f^{\left( n \right)}\left( \mu \right)}{n!}\left< \left( \hat{X}-\mu \right) ^n \right> 
    \end{split}
\end{align}
$$
For a non-linear function, all the derivatives can not be zero simultaneously. For a specific example, let's say $\hat{Y} = \hat{X^2}$, then, 
$$
\begin{equation}
    \left< \hat{Y} \right> =\mu ^2+0+\sigma ^2=\mu ^2+\sigma ^2
\end{equation}
$$










