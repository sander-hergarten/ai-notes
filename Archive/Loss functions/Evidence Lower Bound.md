---
tags:
- math/statistics
- programming/machine-learning/loss-function
---
ELBO is the core of probabilistic inference algorithms such as [[Expectation Maximization]] and [[Variational Inference]]. 

In a latent variable model we assume that our observed data $x$ is a realization of some random variable $X$. We also assume the existence of another random variable $Z$ where $X$ and $Z$ are distributed according to a joint distribution $p(X, Z;\theta)$  where $\theta$  parameterises the distribution. Unfortunately our data is only a realization $X$, not $Z$ and therefore $Z$ remains unobserved (latent).

There are two predominant tasks that we may be interested in accomplishing:
1. Given some fixed value for $\theta$ compute the next distribution $p(Z\ |\ X;\theta)$ 
2. Given that $\theta$ is unkown, find the maximum likelihood estimate of $\theta$: $$\textbf{argmax}_{\theta}l(\theta)$$
where $l(\theta)$ is the log-likelihood function:$$l(\theta):=\log p(x;\theta) = \log \int_z p(x;z;\theta) dz$$
[[Variational Inference]] is used for Task 1 and [[Expectation Maximization]] is used for Task 2 Both of these algorithms rely on the ELBO.


What is evidence? The name given to the likelihood function evaluated at a fixed $\theta$:$$\textbf{evidence} := \log p(x;\theta)$$
This is called evidence since when the model $p$ and the parameters $\theta$ are accurate then we would expect that the probability of our observed data $x$ would be high. That means this quantity is evidence that we have chosen the right model for the data.

if we also know or assume that $Z$ follows some distribution dented by a probability $q$ and that $$p(x,z;\theta):=p(x|z;\theta)q(z)$$ then the evidence lower bound is a lower bound on the evidence that makes use of the know or assumed $q$. Specifically:$$\log p(x;\theta)\ge E_{Z\sim q}\left[\log\frac{p(x, Z;\theta)}{q(Z)}\right]$$ ELBO is the right hand side of the above inequality:$$ELBO:=E_{Z\sim q}\left[\log\frac{p(x, Z;\theta)}{q(Z)}\right]$$
It turns out that the gap between the ecidence and the evidence lower bound is precisely the [[Kullback Leibler Divergence]] between $p(z | x;\theta)$ and $q(z)$