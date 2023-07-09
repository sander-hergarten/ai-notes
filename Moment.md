---
tags:
- math/statistics
---
(https://gregorygundersen.com/blog/2020/04/11/moments/)
A moment is a quantitative measure that describes the shape of a functions graph. For a [[Distributions|distribution]] the collection of all the moments uniquely determine the distribution. In particular Moments typically quantify three parameters of distributions: location, shape and scale.

> [!Abstract] Definition
> The $k$th moment of a random variable $X$ is with a density function $f(x)$ is defined as:
> $$\mu_k =\mathbb{E}\left[X^k\right]=\int_{-\infty}^{\infty}x^kf(x)dx$$ 

# Types of Moments
The $k$th moment of a function $f(X)$ about a non-random value $c$ is:
$$\mathbb{E}\left[(X-c)^k\right] = \int_{-\infty}^{\infty}(x-c)^kf(x)dx$$
This definition allows for an important distinction:
- **Raw Moment:** a raw moment is moment about the origin $(c=0)$ 
- **Central Moment:** a central moment is a moment about the distributions mean ($c=\mathbb{E}[X]$)

If a random variable $X$ has mean $\mu_x$ then its $k$th central moment is:
$$m_k=\mathbb{E}\left[\left(X-\mu_x\right)^k\right]=\int_{-\infty}^{\infty}(x-\mu_x)^kf(x)\ dx$$
Central moments allow us to quantify properties of distributions in ways that are location invariant.  For example, we may be interested in comparing the variability in height of adults versus children. Obviously, adults are taller than children on average, but we want to measure which group has greater variability while disregarding the absolute heights of people in each group. Central moments allow us to perform such calculations. ^62a7fc

The $k$th **Standardized Moment** is typically defined as the $k$th central moment normlized by the standard deviation raised to the $k$th power,
$$\bar{m}_k = \frac{m_k}{\sigma_k}=\mathbb{E}\left[\left(\frac{X-\mu_x}{\sigma_x}\right)^k\right]$$
where $m_k$ is defined as described [[Moment#^62a7fc|here]], and $\sigma_k$ is the $k$th power of the standard deviation of $X$,
$$\sigma_k=\sigma^k_x=\left(\sqrt{\mathbb{E}\left[\left(X-\mu_x\right)^2\right]}\right)^k$$
Note that the standardized moment is only well defined for distributions whose first two moments exist and whose second moment is non-zero. Standardization makes the moment both location and scale invariant.

**Sample Moment** 
A sample moment is an unbiased estimator of its respective raw, central, or standardized moment.

> [!Info] Notation
> $X$ is a random variable and lowercase $x_n$ is used to denote the $n$th realisation from $N$ samples.


#### Parameters and Statistics
Given a statistical model, parameters summerize data for an entire population, while statistics summarize data from a sample of the population. We compute the former exactly using a statistical model and estimate it from data using the latter. For example, if we assume that $X \sim \mathcal{N}(\mu_x,\sigma_x^2)$, then the first raw moment is $\mathbb{E}[X]=\mu_x$

## Total Mass
Since $x^0=1$ for any number $x$, the zeroth raw central, and standardized moments are all 
$$\mu_0=m_0=\bar{m}_0=\int_{-\infty}^{\infty}(...)^0f(x)dx=\int_{-\infty}^{\infty}f(x)dx$$
In other words the zeroth moment captures the fact that probability distributions are normalized quantities, that they always sum to one regardless of their location, scale, or shape. 

Another way to think about this is that the probability that a t least one of the events in a sample space will occur is 1. Thus, the zeroth moment captures Kolmogorov's [[Probability Axioms|second probability axiom]]

## Mean
The first raw moment, the expectation $X$, is 
$$\mu_1=\mu_x=\mathbb{E}[X]=\int_{-\infty}^{\infty}xf(x)dx$$
We can think about the first moment in a few ways. Typically, the expectation of $X$ is introduced to students as the long-run average of $X$. For example if $X$ is the outcome of a roll of a fair six sided die, then its expectation is 
$$\mathbb{E}[X] =1\cdot\frac{1}{6}+2\cdot\frac{1}{6}+3\cdot\frac{1}{6}+4\cdot\frac{1}{6}+5\cdot\frac{1}{6}+6\cdot\frac{1}{6}=3.5$$
If we repeatedly roll a die many times, the finite average of the die rolls will slowly converge to the expected value, hence the name expectation. Another way to think about the first moment is that it is the center of mass of a probability distribution. 

It is also useful to think like this: The first moment tells us how far away from the origin the center of mass is. This is also why centering moments works.

## Variance
Typically people are interested in the second central moment, rather than the second raw moment. This is called the variance of a random variable $X$, denoted $\mathbb{V}[X]$,
$$m_2=\mathbb{V}[X]=\int_{-\infty}^{\infty}(x-\mu_x)^2f(x)\ dx$$
The second central moment increases quadratically as mass gets further away from the distributions mean. in other word, variance captures how spread out a distribution is or its scale parameter. Points that are further away from the mean than others are penalized disproportionally.

## Skewness
Skewness easures the relative size of the tow tails of a distribution.
$$\bar{m}_3=\mathbb{S}[X] = \mathbb{E}[Z^3]=\mathbb E\left[\left(\frac{X-\mu_x}{\sigma_x}\right)^3\right]$$
where $Z$ is the standard score or $z$-score:
$$Z = \frac{X-\mu_x}{\sigma_x}$$
To see how this equation quantifies the relative size of the two tails, consider: any data point less than a standard deviation from the mean results in a standard score less than 1. This is then raised to the third power, making the absolute value of the cubed standard score even smaller. Since the cubic function preserves  sign, if both tails are balanced the skewness is zero. Otherwise, the skewness is positive for longer right tails and negative for longer left tails.

## Kurtosis
While skewness is a measure of  the relative size of the two tails and is positive or negative depending on which tail is larger, kurtosis is a measure of the combined size of the tails relative to the whole distribution. There are a few different ways of measuring this, but the typical metric is the fourth standardised moment:
$$\bar{m}_4 = \mathbb K[X] = \frac{\mu_4}{\sigma_4} = \mathbb E\left[\left(\frac{X-\mu}{\sigma}\right)^3\right]$$
## Generalising and higher moments
With higher moments the logic is the same as with skewness and kurtosis. Odd-powered standardized moments quantity relative tailedness and even-powered standadized moments quatinify total tailedness.

# Moment Generating Functions
A random variables moment-generating function is and alternative specification of its distribution. Consider the moment generating function(MGF) of a random variable $X$,
$$M_X(t)=\mathbb E[X^ke^{tX}]$$
and therefore
$$\frac{d^k}{dt^k}M_X(t)=\mathbb E\left[\frac{d^k}{dt^k}e^{tX}\right]=\mathbb E[X^ke^{tX}]$$
and therefore
$$\frac{d^k}{dt^k}M_X(t)\Bigg|_{t=0}=\mathbb E[X^k]$$In words, the $k$th derivative evaluated at the origin is the $k$th moment. this is nice. wWe can compute moments from the MGF by taking derivatives. This also means that the MGF's [[Taylor Series]] expansion,
$$\mathbb E[e^{tX}]=\mathbb E\left[\sum^{\infty}_{k=0}\frac{1}{k!}t^kX^k\right]=\sum^{\infty}_{k=0}\frac{1}{k!}t^k\mathbb E[X^k]$$
is really an infinite sum of weighted raw moments. MGFs are important for a lot of reasons, but perhaps the biggest is the uniqueness theorem:
>[!Info] Uniqueness Theorem
>Let X and Y be two random variables with cumulative distirbution functions $F_X(x)$ and $F_Y(y)$. If the MGFs exist for $X$ and $Y$ and if $M_X(t)=M_Y(t)$ for all $t$ near $0$, then $F_X(z)=F_Y(z)$ for all $z\in\mathbb R$

The big idea is that MGFs give us an another way to uniquely characterize the distribution of $X$. This is especially helpful since probability density functions and cumulative distribution functions can be hard to work with, and many times it is easier to shift a calculation to the realm of MGFs

