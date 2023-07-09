---
tags:
- math/statistics
aliases:
- PDF
- pdf
- probability density function
---
The Probability Density Function gives the probability for a given continuous variable

For continuous random variables, the [[Cumulative Distribution Function|CDF]] is well defined. However, the [[Probability Mass Function (PMF)|PMF]] is not [[Probability Mass Function (PMF)#^136e35|defined]] for continuous variables. The PDF is the density of probability rather than the probability mass.  To get a feeling for PDF, consider a continuous random variable $X$ and define the function $f_X(x)$ as follows (wherever the limit exists): $$f_X(x)=\lim_{\Delta \to 0^+}\frac{P(x<X\le x+\Delta)}{\Delta}$$
The function $f_X(x)$ gives us the probability density at point $x$. It is the limit of the probability of the interval $(x,x+\Delta]$ divided by the length of the interval as the length of the interval goes to $0$. 

Formally
 >[!abstract] Definition 3.11
>A random variable $X$ is continuous if there exists a function $f_X$ such that $f_X(x)\ge 0$ for all $X$, $\int_{-\infty}^{\infty}f_X(x)dx=1$ and for every $a\le b$
>$$\mathbb P(a<X<b)=\int^b_a f_X(x)dx$$
>The function $f_X$ is called the probability density function (PDF). We have that 
>$$F_X(x)=\int_{-\infty}^x f_X(t)dt$$
>and $f_X(x)=F'_X(x)$ at all points $x$ at which $F_X$ is differentiable

\
Sometimes we shall write $\int f(x)dx$ or simply $\int f$  to mean $\int_{-\infty}^{\infty} f(x)dt$ 
> [!warning]
> Continuos random variables can lead to confusion. First note that if $X$ is continuous then $\mathbb P(X=x)=0$ for every $x$. Don't try to think of $f(x)$ as $\mathbb P(X=x)$. This only holds for discrete random variables. We get probabilities from a PDF by integrating. 


\
A PDF can be bigger than 1 (unlike a mass function). For example if $f(x)=5$ for $x\in [0,1/5]$ and $0$ otherwise, then $f(x)\ge 0$ otherwise, then $f(x)\ge 0$ and $\int f =1$ so this is a well defined PDF. PDF can be unbounded as long as $\int f=1$
