# The Bayesian Philosophy
The frequentist (or classical) point of view is based on the following postulates:

1. Probability refers to limiting relative frequencies. Probabilities are objective properties of the real world.
2. Parameters are fixed (usually unknown) constants. Because they are not fluctuating, no probability statements can be made about parameters.
3. Statistical procedures should be designed to have well defined long run frequency properties. For example, a 95% confidence interval should trap the true value of the parameter with limiting frequency at least 95%.

There is another approach to inference called Bayesian inference. The Bayesian approach is based on the following postulates:
1. Probability describes degree of belief, not limiting frequency. As such, we can make probability statements about lots of things, not just data which are subject to random variation. For example, I might say that 'the probability that Albert Einstein drank a cup of tea on August 1 1948' is .35. This does not refer to any limiting frequency. It reflects my strength of belief that the proposition is true.
2. We can make probability statements about parameters, even though they are fixed constants.
3. We make inferences about a parameter $\theta$, by producing a probability distribution for $\theta$. Inferences, such as point estimates and interval estimates may then be extracted from this distribution.

Bayesian inference is a controversial approach because it inherently embraces a subjective notion of probability. In general Bayesian methods provide no guarantees on long run performance. The field of Statistics puts more emphasis on frequentist methods although Bayesian methods certainly have a presence.

Certain data mining and machine learning communities seem to embrace Bayesian methods very strongly. 

# The Bayesian Method
Bayesian inference is usually carried out in the following way:
1. We choose a probability density $f(\theta)$ called the prior distribution that expresses our degrees of beliefs about a parameter $\theta$ before we see any data.
2. We choose a statistical model $f(x|\theta)$ that reflects our beliefs about $x$ given $\theta$ here the notation changes from $f(x;\theta)$ to $f(x|\theta)$
3. After observing data $X_1,...,X_n$, we update our beliefs and form the posterior distribution $f(\theta|X_1,...,X_n)$
To understand 3. first suppose that $\theta$ is discrete and that there is a single, discrete observation $X$. We should use a capital letter now to denote the parameter since we are treating it like a random variable so let $\Theta$ denote the parameter. Now, in this discrete setting,
$$P(\Theta=\theta|X=x)=\frac{P(X=x,\Theta=\theta)}{P(X=x)}=\frac{P(X=x|\Theta=\theta)P(\Theta=\theta)}{\sum_{\theta}P(X=x|\Theta-\theta)P(\Theta=\theta)}$$
The version for continuous variables is obtained by using density functions:
$$f(\theta|x)=\frac{f(x|\theta)f(\theta)}{\int f(x|\theta)f(\theta)d\theta}$$
If we have $n$ IID observations $X_1,...,X_n$, we replace $f(x|\theta)$ with $f(x_1,...,x_n|\theta)=\prod^n_{i=1}f(x_i|\theta)$
>[!note] Notation
>Let us write $X^n$ to mean $(X_1,...,X_n)$ and $x^n$ to mean $(x_1,...,x_n)$.

If we have $n$ IID observations $X_1,...,X_n$, we replace $f(x|\theta)$ with $f(x_1,...,x_n|\theta)=\prod^n_{i=1}f(x_i|\theta)$. Let us write $X^n$ to mean $(X_1,...,X_n)$ and $x^n$ to mean $(x_1,...,x_n)$. Then:
$$f(\theta|x^n)=\frac{f(x^n|\theta)f(\theta)}{\int f(x^n|\theta)f(\theta)d\theta}=\frac{\mathcal L_n(\theta)f(\theta)}{\int\mathcal L_n(\theta)f(\theta)d\theta}\propto\mathcal L_n(\theta)f(\theta)$$
In the right hand side of the last equation, we threw away the denominator $\int\mathcal L_n(\theta)f(\theta)d\theta$ which is a constant that does not depend on $\theta$; we call this quantity the normalizing constant. We can summarize all this by writing:

> posterior is proportional to [[Likelihood]] times prior

you might wonder, doesn't it cause a problem to throw away the constant $\int\mathcal L_n(\theta)f(\theta)d\theta$? The answer is that we can always recover the constant since we know that $\int f(\theta|x_n)d\theta=1$. Hence, we often omit the constant until we really need it.

What do we do with the posterior? First, we can get a point estimate by summarizing the center of the posterior. Typically we use the mean or mode of the posterior. The posterior mean is
$$\overline{\theta}_n=\int\theta f(\theta|x^n)d\theta=\frac{\int\theta\mathcal L_n(\theta)f(\theta)}{\int\mathcal L_n(\theta)f(\theta)d\theta}$$
We can also obtain a Bayesian interval estimate. Define $a$ and $b$ by $\int^a_{-\infty}f(\theta|x^n)d\theta=\int^{\infty}_bf(\theta|x^n=\alpha/2$. Let $C=(a,b)$. Then $$\mathbb P(\theta\in C|x^n)=\int^b_af(\theta|x^n)d\theta=1-\alpha$$ 
so $C$ is a $1-\alpha$ posterior interval.

# Functions of Parameters
How do we make inferences about a function $\tau=g(\theta)$? 

This problem can be solved in a similar manor as:
Given the density $f_X$ for $X$, find the density for $Y=g(X)$.

The posterior CDF for $\tau$ is 
$$H(\tau|x^n)=\mathbb P(g(\theta)\le \tau=\int_Af(\theta|x^n)d\theta$$
where $A=\{\theta:\;g(\theta)\le\tau\}$. The posterior density is $h(\tau|x^n)=H'(\tau|x^n)$ 

# Simulation 
The posterior can often be approximated by simulation. Suppose we draw $\theta_1,...,\theta_B\sim p(\theta|x^n)$. Then a histogram of $\theta_1,...,\theta_B$ approximates the posterior density. An approximation to the posterior mean $\overline{\theta}_n=\mathbb E(\theta|x^n)$ is $B^{-1}\sum^B_{j=1}\theta_j$. The posterior $1-\alpha$ interval can be approximated by $(\theta_{\alpha/2},\theta_{1-\alpha/2})$ where $\theta_{\alpha/2}$ is the $\alpha/2$ sample quantile of $\theta_1,...,\theta_B$.

Once we have a sample $\theta_1, ..., \theta_B$ from (\theta|x^n), let $\tau_i=g(\theta_i)$. Then $\tau)1, ...,\tau_B$ is a sample from $f(\tau|x^n)$. This avoids the need to do any analytical calculations. 

# Large Sample Properties of Bayes' Procedures 
> [!quote] Theorem
> Under appropriate regularity conditions, we have that the posterior is approximately $N(\hat{\theta},\hat{\text{se}}^2)$ where $\hat{\theta}_n$ is the [[Parametric Inference#Maximum Likelihood|MLE]] and $\hat{se}=1/\sqrt{nI(\hat{\theta}_n)}$. Hence  $\overline{\theta}_n\approx\hat{\theta}_n$. 

# Flat Priors Improper Priors and "Noninformative" Priors

A big question in Bayesian inference is: where do you get the prior $f(\theta)$? One school of thought, called "subjectivism" says that the prior should reflect our subjective opinion about $\theta$ before the data are collected. This may be possible in some cases but seems impractical in complicated problems especially if there are many parameters. An alternative is to try to define some sort of "noninformative prior". An obvious candidate for noninformative prior is to use a "flat" prior $f(\theta) \propto constant$ 

unfettered use of flat priors raises some questions. Consider the $N(\theta, 1)$ example. Suppose we adopt a flat prior $f(\theta)\propto c$ where $c>0$ is a constant. Note that $\int f(\theta)d\theta=\infty$ so this is not a real probability density in the usual sense. We call such a prior an improper prior. Nonetheless, we can still

> [!danger] finish this part
