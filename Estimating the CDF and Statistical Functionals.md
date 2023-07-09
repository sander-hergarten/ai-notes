---
tags:
- math/statistics
alias: 
- Overview of Statistical CDF and Functional Estimation
- Empirical Distribution Function
- EDF
---
# The Empirical Distribution Function
Let $X_1,...,X_n \sim F$ be IID where $F$ is a distribution function on the real line. We will estimate $F$ with the empirical distribution function
>[!abstract] Definition
>The empirical distribution function $\hat{F}_n$ is the CDF that puts mass $1/n$ at each data point $X_i$. Formally
>$$\begin{align}\hat{F}_n(x)&=\frac{\sum_{i=1}^n I(X_i\le x)}{n}\\ &=\frac{\text{number of onservervations less than or equal to $x$}}{n}\end{align}$$
>where 
>$$I(X_i\le x)=\begin{cases}1\quad\text{if $X_i\le x$}\\0\quad\text{otherwise}\end{cases}$$

The following theorems give some properties of the EDF of $x$ 

At any fixed value of $x$
$$\mathbb E\left(\hat{F}_n(x)\right)=F(x)\quad\text{and}\quad\mathbb V\left(\hat{F}_n(x)\right)=\frac{F(x)(1-F(x))}{n}$$
Thus
$$\text{MSE}=\frac{F(x)(1-F(x))}{n}\rightarrow0$$
and hence $\hat{F}_n(x)\xrightarrow{P}F(x)$

> [!quote] Theorem (Glivenko-Cantelli Theorem)
> Let $X_1,...,X_n\sim F$. Then 
> $$\sup_x|\hat{F}_n(x)-F(x)|\xrightarrow{P}0$$

# Statistical Functionals
A statistical functional $T(F)$ is any function of $F$. Examples are the mean, the variance and the median
>[!abstract] Definition 
>The plug-in estimator of $\theta = T(F)$ is defined by:
>$$\hat{\theta}_n=T(\hat{F}_n)$$
>In other words, just plug in $\hat{F}_n$ for the unknown $F$.

A function of the form $\int r(x)dF(x)$ is called a linear functional. If $T(F)=\int r(x)dF(x)$ is a linear functional then the plug in estimator is:
$$T(\hat{F}_n)=\int r(x)d\hat{F}_n(x) =\frac{1}{n}\sum^n_{i=1}r(X_i)$$
In many cases it turns out that 
$$T(\hat{F}_n)\approx N(T(F), \hat{\text{se}}^2)$$
an approximate $1-\alpha$ confidence inerval for $T(F)$ is then 
$$T(\hat{F}_n)\pm z_{a/2}\hat{se}$$
we will call this the normal based interval. 
>[!failure]
>Do exercises

