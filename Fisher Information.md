(https://towardsdatascience.com/an-intuitive-look-at-fisher-information-2720c40867d8)
([[1705.01064.pdf]])
Fisher Information provides a way to measure the amount of information that a random variable contains about some parameter $\theta$ (such as the true mean) of the random variable's assumed probability distribution.

In practice the true value of $\theta$ is not known and has to be inferred from the observed data. The first step typically entails the creation of a data summary. 

For example 
	assume a random variable $X|\theta$ a function of $X$ is now also dependent on $\theta$. More concretely assuming Random varaible $X$ describes an $n$-trial coin flip experiment and we observe for $n=10$, $x^n=(1,0,0,1,1,1,1,0,1,1)$ for which we calculate statistic $Y=\sum^n_{i=1}X_i$ as such $Y|\theta$  
# Definition
The Fisher information $I_X(\theta)$ of a random variable $X$ about $\theta$ is defined as 
$$I_X(\theta)=\begin{cases}
\sum_{x\in \mathcal X}\left(\frac{d}{d\theta}\log f(x|\theta)\right)^2p_\theta(x)\quad\text{if $X$ is discrete}\\

\int_{\mathcal X}\left(\frac{d}{d\theta}\log f(x|\theta)\right)^2p_\theta(x)dx\quad\text{ if $X$ is continuous}
\end{cases}$$
the derivative $\frac{d}{d\theta}\log f(x|\theta)$ is know as the [[Score Function|score function]], a function of $x$, and describes how sensitive the model is to changes in $\theta$ at a particular $\theta$. 

The Fisher information measures the overall sensitivity of the functional relationship $f$ to changes of $\theta$ by weighting the sensitivity at each potential outcome $x$ with respect to the chance defined by $p_\theta(x)=f(x|\theta)$. The weighting with respect to $p_\theta(x)$ implies that the Fisher information about $\theta$ is an expectation.

Similarly, Fisher information $I_{X^n}(\theta)$ within the random vector $X^n$ about $\theta$ is calculated by replacing $f(x|\theta)$ with $f(x^n|\theta)$, thus, $p_\theta(x)$ with $p_\theta(x^n)$ in the definition. Moreover, under the assumption that the random vector $X^n$  consists of $n$ IID trials of $X$ it can be shown that $I_{X^n}(\theta)=nI_X(\theta)$, which is why $I_X(\theta)$ is also know as the unit Fisher information. 

Intuitively, we cannot expect an arbitrary summary statistic $T$ to extract more information about $\theta$ than what is already provided by the raw data. Fisher information adheres to this rule, as it can be shown that 
$$I_{X^n}(\theta)\ge I_T(\theta)$$
with equality if and only if $T$ is a sufficient statistic for $\theta$

# Fisher Information in Frequentist Statistics
Recall that $\theta$ is unknown in practice and to infer its value we might:
1. provide a best guess in terms of a point estimate;
2. postulate its value and test whether this value aligns with the data
3. derive a confidence interval
In the frequentist framework, each of these inferential tools is related to the Fisher information and exploits the data generative interpretation of a Probability Mass Function. Recall that given a model $f(x^n|\theta)$ and a known $\theta$, we can view the resulting PMF $p_\theta(x^n)$  as a recipe that reveals how $\theta$ defines the chances with which $X^n$ takes on the potential outcomes $x^n$