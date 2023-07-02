>[!abstract] Definition 3.1
>A random variable is a mapping $X:\Omega\rightarrow\mathbb{R}$ taht assigns a real number $X(\omega)$ to each outcome $\omega$

At a certain point in most probability courses, the [[Sample Spaces and Events]] are rarely mentioned and we work directly with random variables. 

Given a random variable $X$ and a subset $A$ of the real line, define $X^{-1}(A)=\{\omega\in\Omega : X(\omega)\in A\}$ and let
$$\begin{align}
\mathbb{P}(X\in A) &=\mathbb{P}(X^{-1}(A))=\mathbb{P}(\{\omega\in\Omega;\ X(\omega)\in A\})\\
\mathbb{P}(X\in x) &=\mathbb{P}(X^{-1}(x))=\mathbb{P}(\{\omega\in\Omega;\ X(\omega)\in x\})
\end{align}
$$
$X$ denotes the random variable and $x$ denotes a possible value of $X$

## Distribution Functions and probability Functions
![[Cumulative Distribution Function]]

![[Probability Mass Function (PMF)]]

![[Probability Density Function]]



### Quartiles
It is also useful to define the inverse CDF (or quantile function)
>[!abstract] Definition 3.16
>Let $X$ be random variable with CDF $F$. The inverse CDF or quantile function is defined by $$F^{-1}(q)=\inf\left\{x:\enspace F(X)\le q \right\}$$ 
>for $q\in[0,1]$. If $F$ is strictly increasing and continuous then $F^{-1}(q)$ is the unique real number $x$ such that $F(x)=q$

We call $F^{-1}(1/4)$ the first quartile, $F^{-1}(1/2)$ the median(or second quartile) and $F^{-1}(3/4)$ the third quartile.

Two random variables $X$ and $Y$ are equal in distribution, written $X \stackrel{d}{=} Y$ if $F_X(x)=F_Y(x)$ for all $x$. This does not mean that $X$ and $Y$ are equal. Rather it means that all probability statements about $X$ and $Y$ will be the same.

## Bivariate Distributions
Given a pair of discrete random variables $X$ and $Y$, define the joint mass function by $f(x,y)=\mathbb P(X=x\text{ and }Y=y)$. From now on, we write $\mathbb P(X=x\text{ and }Y=y)$ as $\mathbb P(X=x, Y=y)$. we write $f$ as $f_{X,Y}$ when we want to be more explicit.

## Marginal Distributions
>[!abstract] Definition 3.23
>If $(X,Y)$ have joint distribution with mass function $f_{X,Y}$, then the marginal mass function for $X$ is defined by $$f_X(x)=\mathbb P(X=x)=\sum_y\mathbb P(X=x,Y=y)=\sum_y f(x,y)$$ 
>and the marginal mass function for Y is defined by $$f_Y(y)=\mathbb P(Y=y)=\sum_x\mathbb P(X=x,Y=y)=\sum_x f(x,y)$$ 
>
> For continuous random variables, the marginal densities are $$f_X(x)=\int f(x,y)dy,\quad\text{and}\quad f_Y(y)=\int f(x,y)dx$$
> The corresponding marginal distribution functions are denoted by $F_X$ and $F_Y$

## Independent Random Variables
>[!abstract] Definition 2.29
>Two random variables $X$ and $Y$ are independent if, for every $A$ and $B$,
>$$\mathbb P(X \in A,Y\in B) = \mathbb P(X\in A)\mathbb P(Y\in B)$$
>we write $X \perp \!\!\! \perp Y$ 

In principle, to check whether $X$ and $Y$ are independent we need to check the equation for all subsets $A$ and $B$. Fortunately, we have the following result which we state for continuous  random variables though it is true for discrete random variables too.

>[!quote] Theorem
>let $X$ and $Y$ have joint pdf$f_{X,Y}$. Then $X\perp \!\!\! \perp Y$ if and only if $f_{X,Y}(x,y) = f_X(x)f_Y(y)$ for all values $x$ and $y$

The following result is helpful for verifying independence.
>[!quote] Theorem
>Suppose that the range of $X$ and $Y$ is a (possibly infinite) rectangle. If $f(x,y)=g(x)h(y)$ for some functions $g$ and $h$ (not necessarily probability density functions) then $X$ and $Y$ are independent.


## Conditional Distributions 
If $X$ and $Y$ are discrete, then we can compute the conditional distribution of $X$ given that we have observed $Y=y$. Specifically, $\mathbb P(X=x|Y=y)=\mathbb P(X=x,Y=y)/\mathbb P(Y=y)$. This leads us to define the conditional mass function as follows:
>[!abstract] Definition
>The conditional probability mass function is 
>$$f_{X|Y}(x|y)=\mathbb P(X=x|Y=y)=\frac{\mathbb P(X=x,Y=y)}{\mathbb P(Y=y)}=\frac {f_{X,Y}(x,y)}{f_Y(y)}$$
>if $f_Y(y)>0$

For continuous distributions we use the same definitions. The interpretation differs: in the discrete case, $f_{X|Y}(x|y)$ is $\mathbb P(X=x|Y=y)$ but in the continuous case, we must integrate to get a probability
>[!abstract] Defintion
>For continuous random variables, the conditional probability density function is
>$$f_{X|Y}(x|y)=\frac{f_{X,Y}(x,y)}{f_Y(y)}$$
>assuming that $f_Y(y)>0$. Then,
>$$\mathbb P(X\in A|Y =y)=\int_Af_{X|Y}(x|y)dx$$

From the definition of the conditional density, we see that $f_{X,Y}(x,y)=f_{X|Y}(x|y)f_Y(y)=f_{Y|X}(y|x)f_X(x)$. this can sometimes be useful.

## Multivariate Distributions and IID Samples
Let $X=(X_1,...,X_n)$ where $X_1,...,X_n$ are random variables. we call $X$ a random vector. Let $f(x_1, ....)$ denote the PDF. It is possible to define their marginals, conditionals etc. much the same way as in the bivariate case. We say that $X_1, ...,X_n$ are independent if, for every $A_1, ..., A_n$ 
$$\mathbb P(X_1\in A_1,..., X_n \in A_n)=\prod_{i=1}^n\mathbb P(X_i\in A_i)$$
It suffices to check that $f(x_1,...,x_n)=\prod^n_{i=1}f_{X_i}(x_i)$. If $X_1,...,X_n$ are independent and each has the same marginal distribution with density $f$, we say that $X_1, ...,X_n$ are IID(independent and identically distributed). We shall write this as $X_1,...,X_n\sim f$ or in terms of the CDF $X_1,...,X_N\sim F$. This means that $X_1, ...,X_n$ are  independent draws from the same distribution. We also call $X_1,..., X_n$ a random sample from $F$

>[!warning] 
>It is traditional to write $X\sim F$ to indicate that $X$ has distribution $F$. This is unfortunate notation since the symbol $\sim$ is also used to denote an approximation. The notation $X\sim F$ is so pervasive that we are stuck with it. Read $X\sim F$ as "$X$ has distribution $F$"
>

## Transformations of Random Variables
Suppose that $X$ is a random variable with PDF $f_X$  and CDF $F_X$. Let $Y=r(X)$ be a function of $X$, for example, $Y=X^2$ or $Y=e^x$. We call $Y=r(X)$ a transformation of $X$. How do we compute the PDF and CDF of $Y$? In the discrete case, the answer is easy. The mass function of $Y$ is given by
$$f_Y(y)=\mathbb P(Y=y)=\mathbb P(r(X)=y)=\mathbb P(\{x;r(x)=y\})=\mathbb P(X\in r^{-1}(y))$$
The continuous case is harder. There are three steps for finding $f_Y$:

There are three steps for transfromations
1. For each $y$, find the set $A_y=\{x:\; r(x)\le y\}$
2. Find the CDF $$\begin{align}F_Y(y)&=\mathbb P(Y\le y)=\mathbb P(r(X)\le y)\\ &= \mathbb P(\{x;\; r(x)\le y\})=\int_{A_y}f_X(x)dx\end{align}$$
3. The PDF is $f_Y(y)=F'_Y(y)$

When $r$ is strictly monotone increasing or strictly monotone decreasing then $r$ has an inverse $s=r^{-1}$ and in this case one can show that $$f_Y(y)=f_X(s(y))\left|\frac{ds(y)}{dy}\right|$$
## Transformations of Several Random Variables
In some cases we are interested in transformation of several random variables. For example, if $X$ and $Y$ are given random variables, we might want to know the distribution of $X/Y$, $X+Y$, $\max\{X,Y\}$ or $\min\{X,Y\}$. Let $Z=r(X, Y)$ be the function of interest. The steps for finding $f_Z$ are the same as before:
1. For each $z$, find the set $A_z=\{(x, y):\; r(x, y)\le z\}$ 
2. Find the CDF $$\begin{align}
F_Z(z) &=\mathbb P(Z\le z)=\mathbb P(r(X,Y)\le z)\\ &=\mathbb P(\{(x,y);\; r(x,y)\le z\})=\int\int_{A_z}f_{X,Y}(x,y)\ dx\ dy \end{align}$$
3. Then $f_Z(z)=F'_Z(z)$ 

## Technical Appendix
Recall that a probability measure $\mathbb P$ is defined on a $\sigma$-field $\mathcal{A}$  of a sample space $\Omega$. A random variable $X$ is a measurable map $X\ :\ \Omega \rightarrow \mathbb R$. Measurable means that, for every $x$, $\{\omega:\; X(\omega)\le x\}\in\mathcal A$. 











