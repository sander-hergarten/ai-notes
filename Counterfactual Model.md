---
tags:
- math/statistics
- ruff-note
---
# Estimating the causal effect
Suppose we randomly assign subject to treatment and the $\mathbb P (X=0)>0$ and $\mathbb P(X=1)>0$. Then $\alpha=\theta$. Hence any consistent estimator of $\alpha$ is a consistent estimator of $\theta$. In particular, a consistent estimator is 
$$\begin{align}\hat{\theta}&=\hat{\mathbb E}(Y|X=1)-\hat{\mathbb E}(Y|X=0)\\&=\overline{Y}_1-\overline Y_0 \end{align}$$
where 
$$\overline Y_1=\frac{1}{n_1}\sum_{i:X_i=1}Y_i,\quad\overline Y_1=\frac{1}{n_0}\sum_{i:X_i=0}Y_i$$
and 
$$n_1=\sum^n_{i=1}X_i\quad n_0=\sum^n_{i=1}(1-X_i)$$

If $Z$ is a covariate, we define the conditional causal effect by
$$\theta_z=\mathbb E(C_1|Z=z)-\mathbb E(C_0|Z=z)$$
For example, if $Z$ denotes gender with values $Z\in[0,1]$, then $\theta_0$ is the causal effect among women and $\theta_1$ is the causal effect among men. In a randomized experiment $\theta_z=\mathbb E(Y|X=1,Z=z)-\mathbb E(Y|X=0, Z=z)$ and we can estimate the conditional effect using appropriate sample averages.
![[Pasted image 20230626185935.png]]

## Beyond Binary Treatments
Let us now generalize beyond the binary case. Suppose that $X\in\mathcal X$. For example, $X$ could be the dose of a drug in which case $X\in \mathbb R$. The counterfactual vector ($C_0,C_1$) now becomes the counterfactual process
$$\{C(x):\;x\in\mathcal X\}$$
where $C(x)$ is the outcome a subject would have if he received dose $x$. The observed response is given by the consistency relation
$$Y=C(X)$$
The causal regression function is $$\theta(x)=\mathbb E(C(x))$$
The regression function, which measures association, is $$r(x)=\mathbb E(Y|X=x)$$
In general $\theta(x)\ne r(x)$. However, when $X$ is randomly assigned, $\theta(x)=r(x)$

# Observational Studies and Confounding
A study in which treatment is not randomly assigned, is called an observational study.
> [!Danger] Finish this part


# Simpson's Paradox
Simpson's paradox is a puzzling phenomenon that is discussed in most statistics texts. Unfortunately it is explained incorrectly in most statistics texts. The reason is that it is nearly impossible to explain the paradox without using counterfactuals.

Let $X$ be a binary treatment variable, $Y$ a binary outcome and $Z$ a third binary variable such as gender. Suppose the joint distribution of $X,Y,Z$ is ![[Pasted image 20230626192225.png]]
The marginal distribution for $(X,Y)$ is 
![[Pasted image 20230626192342.png]]
Now using Bayes Theorem
$$\begin{align}\mathbb P(Y=1|X=1)-\mathbb P(Y=1|X=0)&= \frac{\mathbb P(Y=1,X=1)}{\mathbb P(X=1)}-\frac{\mathbb P(Y=1, X=0)}{\mathbb P(X=0)}\\ &= \frac{.25}{.50}-\frac{.30}{.50}=-0.1\end{align}$$
We might naively interpret this to mean that the treatment is bad for you since the outcome is $1$ less if $X=1$ 

we can calculate this among the genders; First among men:
$$\begin{align}\mathbb P(Y=1|X=1,Z=1)-\mathbb P(Y=1|X=0,Z=1)&= \frac{\mathbb P(Y=1,X=1,Z=1)}{\mathbb P(X=1,Z=1)}-\frac{\mathbb P(Y=1, X=0,Z=1)}{\mathbb P(X=0, Z=1)}\\ &= \frac{.15}{.3750}-\frac{.0375}{.1250}=0.1\end{align}$$
and for woman:
$$\begin{align}\mathbb P(Y=1|X=1,Z=0)-\mathbb P(Y=1|X=0,Z=0)&= \frac{\mathbb P(Y=1,X=1,Z=0)}{\mathbb P(X=1,Z=0)}-\frac{\mathbb P(Y=1, X=0,Z=0)}{\mathbb P(X=0, Z=0)}\\ &= \frac{.1}{.1250}-\frac{.2625}{.3750}=0.1\end{align}$$
To summarize, we seem to have the following information:
![[Pasted image 20230626194708.png]]
Clearly, something is amiss. The problem is with the set of English statements in the table. Our translation from math into english is specious 

The inequality $\mathbb P(Y=1|X=1)<\mathbb P(Y=1|X=0)$ does not mean that treatment is harmful

The phrase treatment is harmful should be written mathematically as $\mathbb P(C_1=1)<\mathbb P(C_0=1)$. the three mathematical statements in the table are not all contradictory. It is only the translation in English that is wrong.


