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
The most common method for estimating parameters in a parametric model is the maximum [[Likelihood|likelihood]] method. Let $X_1,...,X_n$ be IID with PDF $f(x;\theta)$
>[!abstract] Definition
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
5. The MLE isapproximately the [[Bayesian Inference|Bayes estimator]]

In sufficiently complicated problems, these properties will no longer hold and the MLE will no longer be a good estimator. The properties hold only if the model satisfies certain regularity conditions. Theses are essentially smoothness conditions on $f(x;\theta)$. 

## Consistency
Consistency means that the MLE converges in probability to the true value. If $f$ and $g$ are PDF's define the [[Kullback Leibler Divergence]] between $f$ and $g$ to be 
$$D(f,g)=\int f(x)\log\left(\frac{f(x)}{g(x)}\right)dx$$
It can be shown that $D(f,g) \ge 0$ and $D(f,f)=0$. For any $\theta,\psi\in\Theta$ write $D(\theta,\psi)$ to mean $D(f(x;\theta),f(x;\psi))$ . We will assume that $\theta \ne\psi$ implies that $D(\theta,\psi)>0$. 

Let $\theta_*$ denote the true value of $\theta$. Maximizing $\mathcal l_n(\theta)$ is equivalent to maximizing 
$$M_n(\theta)=\frac{1}{n}\sum_i\log\frac{f(X_i;\theta)}{f(X_i;\theta_*)}$$
and $M(\theta)=-D(\theta_*, \theta)$. Suppose that $$\sup_{\theta\in\Theta}|M_n(\theta)-M(\theta)|\xrightarrow{P}0$$
and that for every $\epsilon>0$,
$$\sup_{\theta:|\theta-\theta_*|\ge\epsilon}M(\theta)<M(\theta_*)$$
Let $\hat{\theta}_n$ denote the MLE. Then $\hat{\theta}_n\xrightarrow P\theta_*$ 

## Equivariance
Let $\tau=g(\theta)$ be a one-to-one function of $\theta$. Let $\hat{\theta}_n$ be the MLE of $\theta$. Then $\hat{\tau}_n=g(\hat{\theta}_n)$ is the MLE of $\tau$ 

This is true because of the following proof
let $h=g^{-1}$ denote the inverse of $g$. Then $\hat{\theta}_n=h(\hat{\tau}_n)$. For any $\tau$, $L(\tau)=\prod_i f(x_i;h(\tau))=\prod_i f(x_i;\theta)=\mathcal L(\theta)$ where $\theta=h(\tau)$. Hence, for ana $\tau$, $\mathcal L_n(\tau)=\mathcal L(\theta)\le\mathcal L(\hat{\theta})=\mathcal L_n(\hat{\tau})$

## Asymptotic Normality
I turns out that $\hat{\theta}_n$ is approximately Normal and we can compute its variance analytically. To explore this, we first need a few definitions:
> [!abstract] Definition
> The score function is defined to be 
> $$s(X;\theta)=\frac{\partial\log f(X;\theta)}{\partial \theta}$$ 
> The Fisher information is defined to be 
> $$\begin{align}
> I_n(\theta)&=\mathbb V_{\theta}\left(\sum^n_{i=1}s(X_i;\theta)\right)\\
> &=\sum^n_{i=1}\mathbb V_{\theta} (s(X_i;\theta))
> \end{align}$$

The score indicates the steepness of the log-likelihood function and thereby the sensibility to small changes to the parameter values. as such teh 

For $n=1$ we will sometimes write $I(\theta)$ instead of $I_1(\theta)$. It can be shown that $\mathbb E_{\theta}(s(X;\theta))=0$. It then follows that $\mathbb V_{\theta}(s(X;\theta))=\mathbb E_{\theta}(s^2(X;\theta))$ In fact a further simplification of $I_n(\theta)$ is given in the next result.
>[!quote] Theorem
>$I_n(\theta) = nI(\theta)$ and 
>$$\begin{align}
> I(\theta)&=-\mathbb E_{\theta}\left(\frac{\partial^2\log f(X;\theta)}{\partial^2\theta^2}\right)\\
> &= -\int \left(\frac{\partial^2\log f(x;\theta)}{\partial^2\theta^2}\right)f(x;\theta)dx
> \end{align}$$

>[!Danger] Finish this part

## Optimality 
>[!danger] Finish this part


## The Delta Method 
Let $\tau=g(\theta)$ where $g$  is a smooth function. The maximum likelihood estimator of $\tau$ is $\hat{\tau} =g(\hat{\theta})$. Now we address the following question: what is the distribution of $\hat{\tau}$ 

>[!quote] Theorem (The Delta Method)
>If $\tau=g(\theta)$ where $g$ is differentiable and $g'(\theta)\ne 0$ then
>$$\frac{\sqrt{n}(\hat{\tau}_n-\tau)}{\hat{\text{se}}(\hat{\tau})}\rightsquigarrow N(0,1)$$
>where $\hat{\tau}_n=g(\hat{\theta}_n)$ and
>$$\hat{\text{se}}(\hat{tau}_n)=|g'(\hat{\tau})\hat{\text{se}}(\hat{tau}_n)$$
>Hence, if 
>$$C_n=\left(\hat{tau}_n-z_{\alpha/2}\hat{\text{se}}(\hat{tau}_n),\hat{tau}_n+z_{\alpha/2}\hat{\text{se}}(\hat{tau}_n)\right)$$ 
>then $\mathbb P_{\theta}(\tau\in C_n)\rightarrow 1-\alpha$ as $n\rightarrow \infty$

## Multiparameter Models
>[!Danger] Finish this part

## The Parametric Bootstrap
>[!Danger] Finish this part


