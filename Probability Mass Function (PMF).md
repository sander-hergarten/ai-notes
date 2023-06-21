(https://www.probabilitycourse.com/chapter3/3_1_3_pmf.php)
If $X$ is a discrete random variable then its range $R_X$ id a countable set, so, we can list the elements in $R_X$. In other words  we can write:$$R_X=\{x_1, x_2, x_3, ...\}$$
Where:$$X\in R_X$$
>[!Note] Notation 
>While random variables are usually denoted in capital letters, for the range
> lowercase is used.

For a discrete random variable $X$, we are interested in knowing the probabilities of $X=x_k$. The event $A=\{X=x_k\}$ is defined as the set of outcomes $s$ in the sample space $S$ for which the corresponding value of $X$ is equal to $x_k$:$$A=\{s\in S|X(s)=x_k\}$$
The probabilities of events are formally shown by the probability mass function of $X$
> [!Abstract] Definition
> Let $X$ be a discrete random variable with range $R_X=\{x_1,x_2,x_3,...\}$ (finite or countably infinite). The function 
> $$f_X(x_k)=\mathbb P(X=x_k),\ \text{for } k = 1,2,3,...$$
> is called the probability mass function (PMF) of X.

^136e35

Thus the PMF is a probability measure that gibes us probabilities of the possible values for a random variable. While the above notation is the standard notation for the PMF of $X$, it might look confusing at first. The subscript $X$ here indicates that this is the PMF of the random variable $X$. Thus, for example, $P_X(1)$ shows the probability that $X=1$.

Thus $f_X(x)\ge 0$ for all $x\in \mathbb R$ and $\sum_if_X(x_i)=1$. The [[Cumulative Distribution Function|CDF]] of $X$ is related to $f_X$ by 
$$F_X(x)=\mathbb P(X\le x)=\sum_{x_i\le x}f_X(x_i)$$
Sometimes we write $f_X$ and $F_X$ simply as $f$ and $F$

> [!info]  
> Let $F$ be the CDF for a random variable $X$. Then:
> 1. $\mathbb P(X=x)=F(x)-F(x^-)$ where $F(x^-)=\lim_{y\uparrow x} F(y)$,
> 2. $\mathbb P(x<X\le y)= F(y)=F(x)$
> 3. $\mathbb P(X>x)=1-F(X)$
> 4. If $X$ is continuous then$$\mathbb P(a<X<b)=\mathbb P(a\le X <b)=\mathbb P(a<X\le b)=\mathbb P(a\le X\le b)$$
