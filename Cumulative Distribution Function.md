(https://www.probabilitycourse.com/chapter3/3_2_1_cdf.php)
The Cumulative [[Distributions|Distribution]] Function of a random variable is another method to describe the distribution of random variables. The advantage of the CDF is that it can be defined for any kind of random variable (discrete, continuous, mixed).

> [!Abstract] Definition
> The CDF of random Variable $X$ is defined as:$$F_X(x)=P(X\le x), \text{ for all } x\in \mathbb{R}$$

In general, $X$ is a discrete random variable if it takes countably many values with range $R_X = \{x_1,x_2,x_3,...\}$ so that $x_1<x_2<x_3<...$ Here we assume that the range $R_X$ is bounded from below, i.e.,$x_1$ is the smallest value in $R_X$. if this is not the case then $F_X(x)$ approaches zero as $x\rightarrow -\infty$ rather than hitting zero. 

The following results shows that the CDF completely determines the distribution of a random variable.

>[!quote] Theorem 3.7 
>Let $X$ have CDF $F$ and let $Y$ have CDF $G$. If $F(x)=G(x)$ for all $x$ then $\mathbb P(X\in A)=\mathbb(Y\in A)$ for all $A$

>[!quote] Theorem 3.8
>A function $F$ mapping the real line to $[0,1]$ is a CDF for some probability measure $\mathbb P$ if and only if it satisfies the following three conditions
>1. $F$ is non-decreasing i.e. $x_1<x_2$ implies that $F(x_1)\le F(x_2)$ 
>2. $F$ is normalized $\lim_{x\rightarrow -\infty} F(X)=0$ and $\lim_{x\rightarrow \infty} F(x)=1$
