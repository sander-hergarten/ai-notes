Roughly speaking, the statement "$X$ causes $Y$" means that changing the value of $X$ will change the distribution of $Y$. When $X$ causes $Y$, $X$ and $Y$ will be associated but the reverse is not in general, true. Association does not necessarily imply causation.

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

Two frameworks for discussing causation are:
- [[Counterfactual Model|The Counterfactual model]]
- [[Directed Graphs#Probability|The DAG model]]
