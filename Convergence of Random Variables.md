---
tags:
- math/statistics
- ruff-note
alias:
- Large Sample Theory
- Limit Theory
- Asymptotic Theory
---
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
>Let $X_1,X_2,...$ be a sequence of [[Random Variables|random variables]] and let $X$ be another random variable. Let $F_n$ denote the CDF of $X_n$ and let $F$ denote the CDF of $X$.
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

![[Law of Large Numbers]]

Another important observation of convergence is in the [[Central Limit Theorem]] and the [[Delta Method]]





