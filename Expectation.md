# Expectation of a Random Variable
The expectation (or mean) of a random variable $X$ is the average value of $X$. The formal definition is as follows.
>[!abstract] Definition 4.1
>The expected value, or mean, or first moment, of $X$ is defined to be:
>$$\mathbb E(X)=\int xdF(X) =\begin{cases}\sum_xxf(x)\quad &\text{if $X$ is discrete}\\ \int xf(x)dx\quad &\text{if $X$ is continuous} \end{cases}$$
>assuming that the sum (or integral) is well-defined. We use the following notation to denote the expected value of $X$:
>$$\mathbb E(X)=\mathbb EX=\int xdF(x)=\mu=\mu_x$$

The expectation is a one-number summary of the distribution. Think of $\mathbb E(X)$ as the average value you would obtain if you computed the numerical average $n^{-1}\sum^n_{i=1}X_i$ of a large number of IID draws $X_1,...,X_n$. The fact that $\mathbb E (X)\approx n^{-1}\sum^n_{i=1}X_i$ is actually more than a heuristic: it is a theorem called the law of large numbers that we will discuss later. The notation $\int xdF(x)$ deserves some comment. We use it merely as a convenient unifying notation so we don't have to write $\sum_x xf(x)$ for discrete ranodm variables and $\int xf(x)dx$ for continuous random variables but you should be aware that $\int x dF(x)$ has a precise meaning that is discussed in real analysis courses.

To ensure that $\mathbb E(X)$ is well defined, we say that $\mathbb E(X)$ exists if $\int_x|x|dF_X(x)<\infty$. Otherwise we say that the expectation does not exist.

Let $Y=r(X)$. How do we compute $\mathbb E(Y)$ one way is to find $f_Y(y)$ and then compute $\mathbb E(Y)=\int yf_Y(y)dy$. But there is an easier way.
>[!quote] Theorem 4.6 (The rule of the lazy statistician)
>Let $Y=r(X)$. Then
>$$\mathbb E(Y)=\mathbb(r(X))=\int r(x)dF_X(x)$$

This result makes intuitive sense. Think of playing a game where we draw $X$ at random and then I pay you $Y=r(X)$. Your average income is $r(x)$ times the chance that $X=x$, summed (or integrated) over all values of $x$. Here is a special case. Let $A$ be an event and let $r(x)=I_A(x)$ where $I_A(x)=1 if $x\in A$ and $I_A(x)=0$ if $x\notin A$. Then
$$\mathbb E(I_A(X))=\int I_A(x)f_X(x)dx=\int_Af_X(x)dx=\mathbb P(X\in A)$$
In other words, probability is a special case of expectation.

# Properties of Expectations
> [!quote] Theorem 4.10
> If $X_1,...,X_n$ are random variables and $a_1,...,a_n$ are constants, then 
> $$\mathbb E\left(\sum_ia_iX_i\right)=\sum_ia_i\mathbb E(X_i)$$ 

>[!quote] Theorem 4.12
>Let $X_1,...,X_n$ be independent random variables. Then,
>$$\mathbb E\left(\prod^n_{i=1}X_i\right)=\prod_i\mathbb{E}(X_i)$$

Notice that the summation rule does not require independence but the multiplication rule does

# Variance and Covariance
The variance measures the "spread" of a distribution

# Conditional Expectation
Suppose that $X$ and $Y$ are random variables. What is the mean of $X$ among those times when $Y=y$? The answer is that we compute the mean of $X$ as before, but we substitute $f_{X|Y}(x|y)$ for $f_X(x)$ in the definition of expectation
>[!abstract] Defintion
>The conditional expectation of $X$ given $Y=y$ is 
>$$\mathbb E(X|Y=y)=\begin{cases}\sum xf_{X|Y}(x|y)dx\quad &\text{discrete case}\\ \int xf_{X|Y}(x|y)dx\quad &\text{continuous case}\end{cases}$$
>If $r(x, y)$ is a function of $x$ and $y$ then 
>$$\mathbb E(r(X,Y)|Y=y)=\begin{cases}\sum r(x,y)f_{X|Y}(x|y)dx\quad &\text{discrete case}\\ \int r(x,y)f_{X|Y}(x|y)dx\quad &\text{continuous case}\end{cases}$$

Whereas,$\mathbb E(X)$ is a number, $\mathbb E(X|Y=y)$ is a function of $y$. Before we observe $Y$, we don't know the value of $\mathbb E(X|Y=y)$ so it is a random variable which we denote $\mathbb E (X|Y)$. 

In other words, $\mathbb E (X|Y)$ is the random variable whose value is $\mathbb E(X|Y=y)$ when $y=y$. Similarly, $\mathbb E(r(X,Y)|Y)$ is the random variable whose value is $\mathbb E(r(X, Y)| Y)$ is the random variable whose value is $\mathbb E(r(X,Y)|Y=y)$ when $y=y$. 


The rule of iterated epectations states the following:
For random variables $X$ and $Y$, assuming the expectations exit, we have that 
$$\mathbb E[\mathbb E(Y|X)]=\mathbb E(Y)\quad\text{and}\quad\mathbb E[\mathbb E(X|Y)]=\mathbb E(X)$$
More generally, for any function $r(x,y)$ we have
$$\mathbb E[\mathbb E(r(X,Y)|X)]=\mathbb E(r(X,Y)\quad \text{and}\quad\mathbb E[\mathbb E(r(X,Y)|X)]=\mathbb E(r(X,Y))$$

>[!abstract] Definition
>The conditional variance is defined as $$\mathbb V(Y|X=x)=\int(y=\mu(x))^2f(y|x)dy$$
>where $\mu(x)=\mathbb E(Y|X=x)$

For random variables $X$ and $Y$
$$\mathbb V(Y)=\mathbb{EV}(Y|X)+\mathbb{VE}(Y|X)$$
# Expectation as an Integral
The integral of a measurable function $r(X)$ is defined as follow. First suppose that $r$ is simple, meaning that it takes finitely many values $a_1,...,a_k$ over a partition $A_1,...,A_k$. Then $\int r(x)dF(x)=\sum^k_{i=1}a_i\mathbb P(r(X)\in A_i)$. 

The integral of a positive measurable function $r$ is a defined by $\int r(x)dF(x)=\lim_i\int r_i(x)dF(x)$ where $r_i$ is a sequence of simple functions such that $r_i(x)\le r(x)$ and $r_i(x)\rightarrow r(x)$ as $i \rightarrow \infty$. This does not depend on the particular sequence. The integral of a measurable function $r$ is defined to be $\int r(x)dF(x)=\int r^+(x)dF(x)-\int r^-(x)dF(x)$ assuming both intergrals are finite where $r^+(x)=\max\{r(x),0\}$ and $r^-(x)=-min\{r(x),0\}$

# Moment Generating Functions
>[!abstract] Definition 
>The moment generating function (mgf), or Laplace transform, of $X$ is defined by
>$$\psi_X(t)=\mathbb E(e^{tX})=\int e^{tx} dF(x)$$
>where t varies over the real numbers

The mgf is useful for several reasons. First it helps us compute the moments of a distribution. Second, it helps us find the distribution of sums of random variables. Third it is used to probe the central limit theorem.

