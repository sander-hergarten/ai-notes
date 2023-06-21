Statistical inference or "learning" as it is called in computer science, is the process of using data to infer the distribution that generated the data. The basic statistical inference problem is this:
> We observe $X_1,...,X_n\sim F$. We want to infer (or estimate or learn) $F$, or some feature of $F$ such as its mean

# Parametric and Nonparametric Models
A statistical model is a set of distributions (or a set of densities) $\mathfrak{F}$. A parametric model is a set $\mathfrak F$ that can be parameterized by a finite number of parameters. For example, if we assume that the data comes from a Normal distribution then the model is 
$$\mathfrak F =\left\{f(X;\mu,\sigma)=\frac{1}{\sigma\sqrt{\pi}}\exp\left\{-\frac{1}{2\sigma^2}(x-\mu)^2\right\},\mu\in\mathbb R,\sigma >0\right\}$$
This is a two parameter model. This density has parameters $\mu,\sigma$ and describes a random variable $X$ where $x$ is a value of that.

All parametric models take the form 
$$\mathfrak{F} =\{f(x;\;\theta):\theta\in\Theta$$
Where $\Theta$ is called the parameter space and $\theta$ an element or vector of elements making up the parameters. Parameters are called nuisance parameters if they are components of $\theta$ we are not interested in.

A non-parametric model cannot be parameterized by a finite number of parameters. For example $\mathfrak F_{\text{ALL}} =\{\text{all CDF's}\}$ is non-parametric.

In general any function of the distribution $F$ is called a statistical function.

Suppose we observe pairs of data$$(X_1,Y_1),...,(X_n,Y_n)$$ $X$ is called a predictor or regressor or feature or independent variable. $Y$ is called the outcome or the response variable or the dependent variable. We call $r(x)=\mathbb E(Y|X=x)$the regression function.  regression models are sometimes written as $Y=f(X)+\epsilon$ where $\mathbb E(\epsilon)=0$ 
>[!note] Notation
> ![[Pasted image 20230620124026.png]]


# Fundamental Concepts in Inference
The two dominant approaches to statistical inference are called frequentist inference and Bayesian inference.

Many inferential problems are one of three types:
1. estimation
2. confidence 
3. hypothesis testing

## Point Estimation
Point estimation aims to provide a single "best guess" of some quantity of interest. This could be a parameter in a parametric model, a CDF $F$, a PDF $f$, a regression function $r$, or a prediction for a future value $Y$ of some random variable.
> [!note] 
> By convention, we denote a point estimate of the fixed unkown quantity $\theta$ by $\hat{\theta}$. Since this estimation depends on the data $\hat{\theta}$ is a random variable

Formally, let $X_1,...,X_n$ be $n$ IID data point/s from some distribution $F$. A point estimation  $\hat{\theta}_n$  is some function of $X_1,...,X_n$:
$$\hat{\theta}_n=g(X_1,...,X_n)$$
### Bias
We define 
$$\text{bias}(\hat{\theta}_n)=\mathbb E_{\theta}(\hat{\theta}_n)-\theta$$
We say that $\hat{\theta}_n$ is unbiased it the bias is $0$. 

### Consistency
A point estimator $\hat{\theta}_n$ is  consistent if $\hat{\theta}_n\xrightarrow{p}\theta$ [[Convergence of Random Variables#Types of Convergence|(converges in probability)]] and is a reasonable requirement for estimators. 

### Standard Error
The distribution of $\hat{\theta}_n$ is called the sampling distribution and the standard deviation of this distribution if called the standard error denoted by $\text{se}$. The estimated standard error is denoted by $\hat{\text{se}}$

### Mean Square Error
MSE can asses the quality of a point estimate and is defined:
$$\text{MSE}=\mathbb E_{\theta}(\hat{\theta}_n-\theta)^2$$
where $\mathbb E_{\theta}(\cdot)$ is defined [[Models, Statistical Inference and Learning#^14c926]] with respect to the distribution that generated the data. It does not mean we are averaging over a density for $\theta$.
![[Pasted image 20230620131328.png]] ^14c926

>[!quote] Theorem
>The MSE can be written as 
>$$\text{MSE}=\text{bias}(\hat{\theta}_n)^2+\mathbb V_{\theta}(\hat{\theta}_n)$$

If bias$\rightarrow0$ and se$\rightarrow0$ as $n\rightarrow\infty$ then $\hat{\theta}_n$ is consistent.

Many estimators have approximately a Normal distribution
>[!abstract]
>An estimator is asymptotically Normal if 
>$$\frac{\hat{\theta}_n-\theta}{\text{se}}\rightsquigarrow N(0, 1)$$

## Confidence Sets
A $1-\alpha$ confidence interval traps a parameter $\theta$ with probability $1-\sigma$. It is.an interval $(a,b)=C_n$ where $a=a(X_1,...,X_n)$ and $b=b(X_1,...,X_n)$ are functions. These functions fulfil the following condition:
$$\mathbb P_{\theta}(\theta\in C_n)\ge1-\alpha,\quad \text{for all $\theta\in \Theta$}$$we call $1-\alpha$ the coverage of the confidence interval for which common value $\alpha =0.05$. two important notes:
1. $C_n$ is random and $\theta$ is fixed
2. If $\theta$ is a vector then we us a confidence set instead of an interval.
> [!warning] 
> There is much confusion ab out how to interpret
a confidence interval. A confidence interval is not a probability
statement about  $\theta$ since \theta is a fixed quantity, not a random
variable. Some texts interpret confidence intervals as follows: 
if I repeat the experiment over and over, the interval will contain
the parameter 95 percent of the time. This is correct but useless
since we rarely repeat the same experiment over and over. A
better interpretation is this:
> >[!quote] Interpretation
> >On day 1, you collect data and construct a $95\%$ confidence interval for a parameter $\theta_1$. 
> >On Day 2, you collect new data and construct $95\%$ confidence interval for an unrelated parameter $\theta_2$. 
> >On Day 4 , you collect new data and construct a $95\%$ confidence interval for an unrelated parameter $\theta_3$.
> >You continue this way constructing confidence intervals for a sequence of unrelated parameters. Then $95\%$ interval will trap hte true parameter value. 

A mentioned earlier, point estimators often have a limiting Normal distribution, meaning that we can construct approximate confidence intervals

>[!quote] Theorem (Normal-based Confidence Interval) 
>Suppose that $\hat{\theta}_n\approx N(\theta,\hat{\text{se}}^2)$. Let $\Phi$ be the CDF of a standard Normal and let $z_{\alpha/2} =phi^{-1}(1-(\alpha/2))a$, that is $\mathbb P(Z>z_\alpha/2)$ and $\mathbb P(-z_{\alpha/2}<Z<z_{alpha/2})=1-\alpha$ where $Z\sim N(0,1)$ Let
>$$C_n=(\hat{\theta}_n-z_{\alpha/2}\hat{\text{se}},\ \hat{\theta}_n +z_{a/2}\hat{\text{se}}) $$
>then 
>$$\mathbb P_{\theta}(\theta\in C_n)\rightarrow1-\alpha$$

## Hypothesis Testing
When we have data and a hypothesis, called a null hypothesis we can test if the data provides sufficient evidence to reject the null hypothesis.





