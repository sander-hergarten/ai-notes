Suppose that $X$ is a binary treatment variable where $X=1$ means "treated" and $X=0$ means "not treated". We are using the word "treatment" in a very broad sense: treatment might refer to a medication or something like smoking. An alternative to "treated/not treated" is "exposed/not exposed".


Let $Y$ be a some outcome variable such as presence or absence of disease. To distinguish the statement "$X$ is associated $Y$" form the statement "$X$ causes $Y$" we need to enrich our probabilistic vocabulary. We will decompose the response $Y$ into a more fine grained object.

We introduce two new random variables $(C_0,C_1)$ called potential outcomes, with the following outcomes:
- $C_0$ is the outcome if the subject is not treated ($X=0$)
- $C_1$ is the outcome if the subject is treated $(X=1)$. 

$$Y=\begin{cases}C_0\quad \text{if $X=0$}\\ C_1\quad\text{if $X=1$}\end{cases}$$

We can express the relationship between $Y$ and $(C_0,C_1)$ more briefly by
$$Y=C_X$$
This equation is called the consistency relationship

When $X=0$ we dont observe $C_1$ in which case we say that $C_1$ is a counterfactual since it is the outcome you would have had if. counter to the fact, you had been treated.

## Causal Effects
Define the average causal effect or average treatment effect to be 
$$\theta=\mathbb E(C_1)-\mathbb E(C_0)$$
the parameter $\theta$ has the following interpretation: $\theta$ is the mean if everyone were treated $(X=1)$ minus the mean if everyone were not treated ($X=0$). There are other ways of measuring the causal effect. For example, if $C_0$ and $C_1$ are binary, we define the causal odds ratio
$$\frac{\mathbb P(C_1=1)}{\mathbb P(C_1=0)}\div\frac{\mathbb P(C_0=1)}{\mathbb P(C_0=0)}$$

The main ideas will be the same whatever causal effect we use.

## Association
Define the association to be 
$$\alpha =\mathbb E(Y|X=1)-\mathbb E(Y|X=0)$$
there are multiple forms such as the odds ratio for this as well


> [!Warning] Association is not equal to Causation
> in general $\theta\ne\alpha$

The reason for this is that $(C_0, C_1)$ was not independent of $X$. That is, treatment assignment was not independent of person type.

## Estimating the causal effect
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

## Observational Studies and Confounding
A study in which treatment is not randomly assigned, is called an observational study.

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


