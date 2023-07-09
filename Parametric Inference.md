---
tags:
- math/statistics
---
All parametric models take the form 
$$\mathfrak{F} =\{f(x;\;\theta):\theta\in\Theta\}$$
Where $\Theta\subset \mathbb R^k$ is called the parameter space and $\theta=(\theta_1,...,\theta_k)$ an element or vector of elements making up the parameters. 

The problem of inference then reduces to the problem of estimating the parameter $\theta$

Using parametric inference requires knowing that the distribution that generated the data is in some parametric model. 

# Parameter of Interest
Parameters are called nuisance parameters if they are components of $\theta$ we are not interested in and parameters of interest if we are. The parameter of interest can be a complicated function of $\theta$.

For example:
Let $X_1,...,X_n\sim N(\mu,\sigma^2)$ The parameter is $\theta = (\mu, \sigma)$ is $\Theta=\{(\mu,\sigma):\;\mu\in\mathbb R,\;\sigma>0\}$. Suppose we are interested in $\tau$, the fraction who score above 1. Let $Z$ denote a standard Normal random variable $\frac{X-\mu}{\sigma}$ ![[Pasted image 20230621211944.png]]
The parameter of interest is $\tau=T(\mu,\sigma)=1-\Phi((1-\mu)/\sigma)$

# The Method of Moments
This method  for generating parametric estimators results in non-optimal, but easy to compute, estimators. They are also useful as starting values for other methods that require iterative numerical routines.

Suppose that the parameter $\theta=(\theta_1,...,\theta_k)$ has $k$ components. For $1\le j\le k$, define the $j^{th}$ [[Moment]]
$$\alpha_j\equiv a_j(\theta)=\mathbb E_{\theta}(X^j)=\int x^j dF_{\theta}(x)$$
and the $j^{th}$ sample moment
> [!abstract] Definition 
> The method of moments estimator $\hat{\theta}_n$ is defined to be the value of $\theta$ such that 
> $$\begin{align}
> \alpha_1(\hat{\theta}_n) &= \hat{\alpha}_1 \\
> \alpha_2(\hat{\theta}_n) &= \hat{\alpha}_2 \\
> \vdots\quad& \vdots\quad\vdots \\
> \alpha_k(\hat{\theta}_n) &= \hat{\alpha}_k \\
> \end{align}$$

> [!quote] Theorem
> Let $\hat{\theta}_n$ denote the method of moments estimator. The following statements hold:
> 1. The estimate $\hat{\theta}_n$ exists with probability tending to 1.
> 2. The estimate is consistent: $\hat{\theta}_n\xrightarrow{P}\theta$ 
> 3. The estimate is asymptotically Normal: $$\sqrt{n}(\hat{\theta}_n-\theta\rightsquigarrow N(0,\Sigma)$$ where $$\Sigma = g\mathbb E_{\theta}(YY^T)g^T$$,
> $$Y=(X,X^2,...,X^k),g=(g_1,...,g_k)\text{ and } g_j=\partial\alpha^{-1}_j(\theta)/\partial\theta$$

The last statement can be used to find standard errors however using [[The Bootstrap]] is easier

# [[Maximum Likelihood Estimator|Maximum Likelihood]]
One of the most successful approaches to parametric inference is the Maximum Likelihood estimator