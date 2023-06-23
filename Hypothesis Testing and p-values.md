# Intuition
Suppose we want to know if a certain chemical causes causes cancer. We take some rats and randomly divide them into two groups. we expose one group to the chemical and then we compare the cancer rate in the two groups. Consider the following two hypotheses

#### The Null Hypothesis
The cancer rate is the same in the two groups

#### The Alternative Hypothesis
The cancer rate is not the same in the two groups

If exposed group has a much higher rate of cancer than the unexposed group then we will reject the null hypothesis and conclude that the evidence favours the alternative hypothesis; in other words we will conclude that there is evidence that the chemical causes cancer.

# Formal
Suppose we partition the parameter space $\Theta$ into two disjoint sets $\theta_0$ and $\theta_1$ and that we wish to test:
$$H_0:\theta\in\Theta_0\quad\text{versus}\quad H_1:\theta\in\Theta_1$$
we call $H_0$ the null-hypothesis and $H_1$ the alternative hypothesis. 

Let $X$ be a random variable and let $\mathcal X$ be the range of $X$. We test a hypothesis by finding an appropriate subset of outcomes $R\subset\mathcal X$ called the rejection region. If $X\in R$ we reject the null hypothesis, otherwise, we do not reject the null hypothesis

Usually the rejection region $R$ is of the form 
$$R=\left\{x:\;T(x)>c\right\}$$where $T$ is a test statistic and $c$ is a critical value. The problem in hypothesis testing is to find an appropriate test statistic $T$ and an appropriate cutoff value $c$.

>[!warning]
>There is a tendency to use hypothesis testing methods even when they are not appropriate. Often, estimation and confidence intervals are better tools.

## Type I and Type II error
Rejecting $H_0$ when $H_0$ is true is called a type I error. Rejecting $H_1$ when $H_1$ is true is called a type II error.

## Power Function
The power function of a test with rejection region $R$ is defined by 
$$\beta(\theta)=\mathbb P_{\theta}(X\in R)$$
the size of a test is defined to be 
$$\alpha=\sup_{\theta\in\Theta_0}\beta(\theta)$$
A test is said to have level $\alpha$ if its size is less than or equal to $\alpha$

## Simple and Composite Hypothesis
A hypothesis of the form $\theta=\theta_0$ is called a simple hypothesis. A hypothesis of the form $\theta>\theta_0$ or $\theta<\theta_0$ is called a composite hypothesis. 

## One and Two Sided Test
This is a two sided test:
$$H_0:\theta=\theta_0\quad\text{versus}\quad H_1:\theta\ne\theta_0$$
These are one sided tests:
$$H_0:\theta\le\theta_0\quad\text{versus}\quad H_1:\theta>\theta_0$$
$$H_0:\theta\ge\theta_0\quad\text{versus}\quad H_1:\theta>\theta_0$$
Most tests are two sided

>[!danger] Finish this chapter

