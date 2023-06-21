This part of probability is called:
- Large Sample Theory
- Limit Theory
- Asymptotic Theory

The basic question is this: what can we say about the limiting behavior of a sequence of random variables $X_1,X_2,X_3,...$? Since statistics and data mining are all about gathering data, we will naturally be interested in what happens as we gather more and more data.

In calculus we say that a sequence of real numbers $x_n$ converges to a limit $x$ if, for every $\epsilon>0$, $|x_n-x|<\epsilon$for all large $n$. In probability convergence is more subtle. 

There are two main ideas regarding Convergence:
1. The law of large numbers says that sample average $\overline{X}_n=n^{-1}\sum^n_{i=1}X_i$ converges in probability to the expectation $\mu=\mathbb E(X)$
2. The central limit theorem says that sample average has approximately a Normal distribution for large $n$. More precisely, $\sqrt{n}(\overline{X}_n-\mu)$ converges in distribution to a Normal(0, $\sigma^2$) distribution, where $\sigma^2=\mathbb V(X)$ 

# Types of Convergence
The two main types of convergence are defined as follows.
>[!abstract] Definition 6.1
>Let $X_1,X_2,...$ be a sequence of random variables and let $X$ be another random variable. Let $F_n$ denote the CDF of $X_n$ and let $F$ denote the CDF of $X$.
>1. X_n converges to $X$ in probability,  written $X_n\xrightarrow{P}X$ if, for every $\epsilon > 0$, $$\mathbb P(|X_n-X|>\epsilon)\rightarrow 0$$ as $n\rightarrow \infty$
>2. X_n Converges to $X$ in distribution written $X_n\rightsquigarrow X$, if, 
>3. $$\lim_{n\rightarrow\infty}F_n(t)=F(t)$$ 
> at all $t$ for which $F$ is continuous.

There is another type of convergence which we introduce mainly because it is useful for proving convergence in probability
>[!abstract] Definition
>$X_n$ converges to $X$ in quadratic mean(also called convergence in $L_2$), writteb $X_n\xrightarrow{qm}X$ if $$\mathbb E(X_n-X)^2\rightarrow 0$$ as $n\rightarrow \infty$

If $X$ is a point mass at $c$ (that is $\mathbb P(X=c)=1$) we write $X_n\xrightarrow{qm}c$ instead of $X\xrightarrow{qm}X$. Similarly, we write $X_n\xrightarrow{P}c$ and $X_n \rightsquigarrow c$. 

The next theorem gives the relationship between the types of convergence. 
>[!quote] Theorem
>The following relationships hold:
>1. $X_n\xrightarrow{qm}X$ implies that $X_n\xrightarrow{P}X$.
>2. $X_n \xrightarrow{P} X$ implies that $X_n\rightsquigarrow X$. 
>3. If $X_n\rightsquigarrow X$ and if $\mathbb P(X=c)=1$ for some real number $c$, then $X_n\xrightarrow{P} X$

In general, none of the reverse implications hold except the special case in (3)![[Pasted image 20230619200443.png]]
>[!warning]
>One might conjecture that if $X_n\xrightarrow{P}b$ then $\mathbb E(X_n)\rightarrow b$. this is not true

Here are a few convergence rules
![[Pasted image 20230619200811.png]]
# The Law of Large Numbers
This theorem says that the mean of a large sample is close to the mean of the distribution. 

Let $X_1,X_2,...$ be an IID sample and let $\mu=\mathbb E(X_1)$ and $\sigma^2=\mathbb V(X_1)$. Recall that the sample mean is defined as $\overline{X}_n=n^{-1}\sum^n_{i=1}X_i$ and that $\mathbb E(\overline{X}_n)=\mu$ and $\mathbb V(\overline{X}_n)=\sigma^2/n$ 
> [!quote] Theorem (The Weak Law of Large Numbers)
> If $X_1,...,X_n$ are IID, then $\overline{X}_n\xrightarrow{P}\mu$

Interpretation of WLLN: the distribution of $\overline{X}_n$ becomes more concentrated around $\mu$ as $n$ gets large

# The Central Limit Theorem
Suppose that $X_1,...,X_n$ are IID with mean $\mu$ and variance $\sigma$. The central limit theorem says that $\overline{X}_n=n^{-1}\sum_i X_i$ has a distribution which is approximately Normal with mean $\mu$ and variance $\sigma^2/n$. This is remarkable since nothing is assumed about the distribution of $X_i$, except the existence of the mean and variance.

>[!quote] Theorem (The Central Limit Theorem)
>Let $X_1,...,X_n$ be IID with mean $\mu$ and variance $\sigma^2$. Let $\overline{X}_n=n^{-1}\sum^n_{i=1} X_i$. Then $$Z_n\equiv\frac{\sqrt{n}(\overline{X}_n-\mu)}{\sigma}\rightsquigarrow Z$$ 
>where $Z\sim N(0,1)$. In other words,
>$$\lim_{n\rightarrow\infty}\mathbb P(Z_n\le z)=\Phi(Z)=\int^z_{-\infty}\frac{1}{\sqrt{2\pi}}e^{-x^2/2}dx$$ 

Interpretation: Probability statements about $\overline{X}_n$ can be approximated using a Normal distribution. It's the probability statement that we are approximating, not the random variable itself

In addition to $Z_n\rightsquigarrow N(0,1)$, there are several forms of notation to denote the fact that the distribution of $Z_n$ is converging to a Normal. They all mean the same thing:
![[Pasted image 20230619210409.png]]
![[Pasted image 20230619210520.png]]

We rarely know $\sigma$ but can estimate $\sigma^2$ from $X_1,...,X_n$ by 
$$S^2_n=\frac{1}{n-1}\sum^n_{i=1}(X_i-\overline{X}_n)^2$$
This raises the question if replacing $\sigma$ with $S_n$ keeps the central limit theorems truthness. The answer is Yes
>[!quote] Theorem
>Assume the same conditions as the CLT. Then,
>$$\frac{\sqrt{n}(\overline{X}_n-\mu)}{S_n}\rightsquigarrow N(0,1)$$

The accuracy of the normal approximation is given in the Berry-Essèen theorem.
>[!quote] Theorem (Berry-Essèen)
>Suppose that $\mathbb E|X_1|^3<\infty$. Then 
>$$\sup_z|\mathbb P(Z_n\le z)-\Phi(z)|\le\frac{33}{4}\frac{\mathbb E|X_1-\mu|^3}{\sqrt{n}\sigma^3}$$

There is also a multivariate version of the central limit theorem
>[!quote] Theorem (Multivariate central limit theorem)
>Let $X_1,...,X_n$ be IID random vectors where 
>$$X_i=\begin{bmatrix}
>X_{1i}\\
>X_{2i}\\
>\vdots \\
>X_{ki}
>\end{bmatrix}
>$$
>where mean
>$$\mu=\begin{bmatrix}\mu_1\\\mu_2\\\vdots\\\mu_k\end{bmatrix}=\begin{bmatrix}\mathbb E(X_{1i}\\\mathbb E(X_{2i})\\\vdots\\\mathbb E(X_{ki})\end{bmatrix}$$
>and variance matrix $\sum$. Let
>$$\overline{X}=\begin{bmatrix}\overline{X}_1\\ \overline{X}_2\\\vdots\\\overline{X}_k\end{bmatrix}$$
>where $\overline{X}_i=n^{-1}\sum^n_{i=1} X_{1i}$. Then,
>$$\sqrt{n}(\overline{X}-\mu)\rightsquigarrow N(0,\Sigma)$$

# The Delta Method
If $Y_n$ has a limiting Normal distribution then the delta method allows us to find the limiting distribution of $g(Y_n)$ where $g$ is any smooth function.

> [!quote] Theorem (The Delta Method)
> Suppose that $$\frac{\sqrt{n}(Y_n-\mu)}{\sigma}\rightsquigarrow N(0,1)$$
> and that $g$ is a differentiable function such that $g'(\mu)\ne 0$. Then
> $$\frac{\sqrt{n}(g(Y_n)-g(\mu))}{|g'(\mu|\sigma)}\rightsquigarrow N(0,1)$$

In other words,
$$Y_n\approx N\left(\mu,\frac{\sigma^2}{n}\right)\; \Longrightarrow\; g(Y_n)\approx N\left(g(\mu),(g'(\mu))^2\frac{\sigma^2}{n}\right)$$
# The Multivariate delta function
TODO
-----



