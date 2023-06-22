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

# Maximum Likelihood
The most common method for estimating parameters in a parametric model is the maximum likelihood method. Let $X_1,...,X_n$ be IID with PDF $f(x;\theta)$
>[!abstract] Definition
>The likelihood function is defined by 
>$$\mathcal L_n(\theta)=\prod^n_{i=1}f(X_i;\theta)$$
>The log-likelihood function is defined by $\mathcal l_n(\theta)=\log\mathcal L_n(\theta)$
> ---
>The maximum likelihood estimator MLE, denoted by $\hat{\theta}_n$, is the value of $\theta$ that maximizes $\mathcal L _n(\theta)$

the likelihood function is just the joint density of the data except that we treat it as a function of the parameter $\theta$. Thus $\theta$. Thus $\mathcal{L}_n:\Theta\rightarrow[0,\infty)$. The likelihood function is not a density function: in general, it is **not** true that $\mathcal L_n(\theta)$ integrates to 1. 

The maximum of $\mathcal{l}_n(\theta)$ occurs at the same place as  the maximum of $\mathcal L_n(\theta)$, so maximizing the log- likelihood lead s to the same answer. Often it is easier to work with the log-likelihood. 

when multiplying $\mathcal L_n(\theta)$ by any positive constant $c$ then this will not change the MLE. Hence we can often be sloppy about dropping constants in the likelihood function.

# Properties of Maximum Likelihood Estimators
The main properties of the MLE are:
1. I is consistent: $\hat{\theta}_n\xrightarrow{P}\theta_*$ where $\theta_*$ denotes the true values of the parameter $\theta$
2. It is equivariant: if $\hat{\theta}_n$ is the MLE of $\theta$ then $g(\hat{\theta}_n)$ is the MLE of $g(\theta)$
3. it is asymptotically Normal:$\sqrt{n}(\\hat{\theta}-\theta_*/\hat{\text{se}}\rightsquigarrow N(0, 1))$ where $\hat{\text{se}}$ can be computed analytically;
4. It is asymptotically optimal or efficient: roughly, this means that among all well behaved estimators, the MLE has the smallest variance, at leas for large samples.
5. The MLE isapproximately the [[Bayes estimator]]

In sufficiently complicated problems, these properties will no longer hold and the MLE will no longer be a good estimator. The properties hold only if the model satisfies certain regularity conditions. Theses are essentially smoothness conditions on $f(x;\theta)$. 

## Consistency
Consistency means that the MLE converges in probability to the true value. If $f$ and $g$ are PDF's define the [[Kullback Leibler Divergence]] between $f$ and $g$ to be 
$$D(f,g)=\int f(x)\log\left(\frac{f(x)}{g(x)}\right)dx$$
It can be shown that $D(f,g) \ge 0$ and $D(f,f)=0$. For any $\theta,\psi\in\Theta$ write $D(\theta,\psi)$ to mean $D(f(x;\theta),f(x;\psi))$ . We will assume that $\theta \ne\psi$ implies that $D(\theta,\psi)>0$. 

Let $\theta_*$ denote the true value of $\theta$. Maximizing $\mathcal l_n(\theta)$ is equivalent to maximizing 
$$M_n(\theta)=\frac{1}{n}\sum_i\log$$





