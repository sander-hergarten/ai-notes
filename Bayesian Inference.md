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
