Decision theory is a formal theory for comparing statistical procedures. 

Consider $\theta\in\Theta$ where $\hat{\theta}$ is an estimator of $\theta$. In Decision theory, an estimator is sometimes called a decision rule and the possible values of the decision rule are called actions.

We shall measure the discrepancy  between $\theta$ and $\hat{\theta}$ using a loss function $L(\theta,\hat{\theta})$. Formally, $L:\theta\times\theta  \rightarrow\mathbb R$ 

To emphasize that $\hat{\theta}$ is a function of the data we write $\hat{\theta}$ as $\hat{\theta}(X)$. To assess an estimator, we evaluate the average loss or risk.
>[!abstract] Defintion
>The risk of an estimator $\hat{\theta}$ is $$R(\theta,\hat{\theta})=\mathbb E_{\theta}\left(L(\theta,\hat{\theta})\right)=\int L(\theta,\hat{\theta}(x))f(x;\theta)dx$$

when the loss function is squared error , the risk is just the mean squared error. 

# Comparing Risk Functions

To compare two estimators we can compare their risk functions. To do so, we need a one-number summary of the risk function. Two such summaries are the maximum risk 
$$\overline{R}(\hat\theta)=\sup_\theta R(\theta,\hat\theta)$$
and the Bayes' risk
$$r(\pi,\hat\theta)=\int R(\theta,\hat\theta)\pi(\theta)d\theta$$
where $\pi(\theta)$ is a prior for $\theta$


## Bayes' Estimators
A decision rule that minimizes the Bayes risk is called a Bayes rule. Formally, $\hat{\theta}$ is a bayes rule prior $\pi$ if 
$$R(\theta,\hat\theta)=\inf_\overline\theta r(\pi,\tilde\theta)$$
where the infimum is over all estimators $\tilde\theta$

Let $\pi$ be a prior. From Bayes' theorem, the posterior density is $$f(\theta|x)=\frac{f(x|\theta)\pi(\theta)}{m(x)} =\frac{f(x|\theta)\pi(\theta)}{\int f(x|\theta)\pi(\theta)d\theta}$$
where $m(x)$ is the marginal distribution of $X$. Define the posterior risk of an estimator $\hat\theta_n(x)$ by 
$$r(\hat\theta|x)=\int L(\theta,\hat\theta(x))f(\theta|x)d\theta$$
The Bayes' risk r(\pi,\hat\theta) satisfies
$$r(\pi,\hat\theta)=\int r(\hat\theta|x)m(x)dx$$
Let $\hat\theta(x)$ be the value of $\theta$ that minimizes $r(\hat\theta|x)$. Then $\hat\theta$ is the Bayes estimator

## Minimax Estimators
An estimator that minimizes the maximum risk is called a minimax rule. Formally, $\hat\theta$ is minimax if 
$$R(\theta,\hat\theta)=\inf_\overline\theta\sup_\theta R(\theta,\tilde\theta)$$
where the infimum is over all estimators $\tilde\theta$


The problem of finding minimax rules is complicated. The main message to take away is that bayes estimators with a constant risk functions are minimax. Formally:

Let $\hat\theta^\pi$ be the Bayes rule for some prior $\pi$:
$$r(\pi,\hat\theta^\pi) \le \inf_\hat\theta r(\pi,\hat\theta)$$
suppose that 
$$R(\theta,\hat\theta^\pi)\le r(\pi,\hat\theta^\pi)\quad \text{for all $\theta$}$$




> [!danger] Finish this part

